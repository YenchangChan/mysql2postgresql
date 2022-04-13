# mysql2postgresql
Convert mysql dump file to postgresql script.   
### How to build
If your go version is under `go1.17`, then use:
```
go get github.com/YenchangChan/mysql2postgresql
```
If your  go version is `go1.17+`, then use:
```
go install github.com/YenchangChan/mysql2postgresql@latest
```
### How to use
1. use mysqldump to dump database from mysql:
`mysqldump --compatible=postgresql --default-character-set=utf8 --hex-blob -r databasename.mysql -u root databasename`
> **Tips:** `--compatible=postgresql` doesn't work on mysql8.0, so you need to ensure mysql version is mysql5.7
2. convert the dump file to postgresql script:   
`mysql2postgresql -i databasename.mysql -o databasename.sql`
3. use the script with psql:   
`\i databasename.sql`

### Reference
[mysql-postgresql-converter](https://github.com/lanyrd/mysql-postgresql-converter)

