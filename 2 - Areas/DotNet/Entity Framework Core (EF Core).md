## List of migrations

```sh
dotnet ef migrations list

dotnet ef migrations list \
	--project src/MortgageAutomator.Server
```

The prefix has a timestamp which shows the sequence of the migrations:
```
20260624133804_InitialCreate
20260709182748_RemoveDrawProjectCompletionPercent
20260710031409_SoftDeleteConstructionBudgetLineItems
20260819155544_AddDrawRequests
```


## Generate SQL Script
`<from>` and `<to>` migrations are not specified:

```sh
dotnet ef migrations script --idempotent \
    --project src/MortgageAutomator.Server \
    --output migrations/002_AddDrawRequests.sql
```

`<from>` migration is specified:

```sh
dotnet ef migrations script 20260710031409_SoftDeleteConstructionBudgetLineItems \
  --idempotent \
  --project src/MortgageAutomator.Server \
  --output migrations/002_AddDrawRequests.sql
```

Run it on remote server
```sh
scp migrations/002_AddDrawRequests.sql my-remote:/tmp/
ssh my-remote
mysql -h abc.xyz.rds.amazonaws.com -u <user> -p \
  my_database < /tmp/002_AddDrawRequests.sql
```