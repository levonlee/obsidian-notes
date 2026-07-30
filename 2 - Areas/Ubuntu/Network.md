## `getent hosts xxx`
```
getent hosts clickhouse
```

- **`getent`** — retrieves entries from system databases managed through NSS, such as users, groups, services, and hosts.
- **`hosts`** — specifies the hosts database.
- **`clickhouse`** — the hostname to resolve.

```
172.31.66.73 clickhouse
```

Unlike `nslookup` or `dig`, `getent hosts` follows the same resolution configuration most applications use, including sources such as:
```
/etc/hosts
DNS
Docker or container network DNS
LDAP or other configured NSS sources
```
