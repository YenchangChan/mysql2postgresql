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

### release
You can get release program from [https://github.com/YenchangChan/mysql2postgresql/releases](https://github.com/YenchangChan/mysql2postgresql/releases)

### How to use
1. use mysqldump to dump database from mysql:
```
mysqldump --compatible=postgresql --default-character-set=utf8 --hex-blob -r databasename.mysql -u root databasename -p
```
**Note:** Option `--compatible=postgresql` doesn't work on mysql8.0+, so if your mysql version is greater than 8.0, you can use:
```
mysqldump --default-character-set=utf8 --hex-blob -r databasename.mysql -u root databasename -p
```
If you just wan't to dump scheme witout data, please add `-d` option:
```
mysqldump --default-character-set=utf8 --hex-blob -r databasename.mysql -u root databasename -d -p
```

2. convert the dump file to postgresql script:   
`mysql2postgresql -i databasename.mysql -o databasename.sql`
3. use the script with psql:   
`\i databasename.sql`

### Reference
[mysql-postgresql-converter](https://github.com/lanyrd/mysql-postgresql-converter)

