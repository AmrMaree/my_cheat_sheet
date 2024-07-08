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
Know the branch you are connected to
```
git branch
``` 

## Postgres commands in linux

Connect to database under specific user
```
psql -h host -d database -U user -p port_number -W
```
Start / Stop / Restart postgresql
```
sudo service postgresql start / stop / restart 
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

## MySQL commands in linux

Connect to database under specific user
```
mysql -u username -p
```
Start / Stop / Restart MySQL
```
sudo service mysql start / stop / restart 
```
Create new database
```
CREATE DATABASE database_name;
```
Delete a database
```
DROP DATABASE database_name;
```
Show all databases
```
SHOW DATABASES;
```
Use a specific database
```
USE database_name;
```
Show tables in a database
```
SHOW TABLES;
```
Show table structure
```
DESCRIBE table_name;
```
Exit MySQL
```
exit
```
## Sqlite commands in linux
Connect to database under specific user
```
sqlite3 database_name.db
```
Exit sqlite
```
.exit
```
