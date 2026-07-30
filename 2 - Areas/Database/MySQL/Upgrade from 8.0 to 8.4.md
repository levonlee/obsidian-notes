## Confirm versions
```sh
lsb_release -a
mysql -uroot -p -e "SELECT VERSION(), @@version_comment, @@datadir;"
mysql -uroot -p -e "SELECT user, host, plugin FROM mysql.user ORDER BY user, host;"
```

I encounter a problem: Ubuntu has to be upgraded from Ubuntu 20.04.5 LTS (focal) to Ubuntu 22.04 LTS, and then install MySQL 8.4 from the package manager.

## Best procedure
Run the upgrade on a production clone, restore/test the affected tables on MySQL 8.4, smoke test the app, and document that the warnings are accepted schema debt.

## Check all tables on MySQL 8.0
  What it checks:
  - whether tables are compatible with the current MySQL server version
  - old/incompatible data types or index formats
  - charset/collation changes that may require index rebuilds
  - old temporal column formats
  - deprecated/removed features
  - table/storage-engine warnings, like your Row size too large (> 8126) warnings

  What the output means:
  - OK: table passed
  - Table is already up to date: MySQL decided no deeper check was needed
  - Warning: not necessarily corrupt, but should be reviewed
  - Error: real problem; investigate before upgrading

Return only warning and error:
```sh
mysqlcheck -uroot -p --all-databases --check-upgrade 2>&1 \
    | awk '
      NF == 1 { table = $0; next }
      /Table is already up to date$/ { next }
      /[[:space:]]OK$/ { next }
      /^(Warning|Error)[[:space:]]*:/ {
        if (table != "") print table
        table = ""
        print
        next
      }
      {
        if (table != "") print table
        table = ""
        print
      }
    '
```

## Check if MySQL package is on hold
Check if these packages are on hold:
- mysql-server
- mysql-client
- mysql-community-server
- mysql-community-client
- libmysqlclient*
![[Package on hold]]

