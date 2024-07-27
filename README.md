# My Cheat Sheet

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
Grant access to user on database
```
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
```
Change password of user
```
ALTER USER 'root'@'localhost' IDENTIFIED BY 'NewPassword';
```
Know the port mysql is working on
```
SHOW GLOBAL VARIABLES LIKE 'PORT';
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
## Alembic commands
Create migration enviroment
```
alembic init alembic
```
Generating a base empty migration
```
alembic revision -m "message"
```
Autogenerating the migration
```
alembic revision --autogenerate -m "message"
```
Determine what the last migration applied to the database
```
alembic current
```
Shows every step from our initial empty migration to our current migration
```
alembic history
```
Upgrades the database
```
alembic upgrade head / [migration id] / +[number of steps]
```
Downgrade the database
```
alembic downgrade base / [migration id] / -[number of steps]
```
Marking a database migration as current
```
alembic stamp [migration id]
```
##
Generate random 32 bit hexadecimal number
```
openssl rand -hex 32
```