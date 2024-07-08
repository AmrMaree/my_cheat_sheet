# my_cheat_sheet

## Git commands I am using often
initialize local repository
```
git init
```
add files
```
git add .
```
commit files
```
git commit -m "commit description"
```
push files to github
```
git push origin <branch name>
```
Create new branch
```
git checkout -b "new_branch_name"
```

## Postgres commands in linux

Connect to database under specific user
```
psql -h host -d database -U user -p port_number -W
```
Switch connection to a new database
```
\c dbname
```
List availabe databases
```
\l
```
List available tables
```
\dt
```
Describe a table
```
\d table_name
```
List all users
```
\du
```
Exit psql
```
\q
```