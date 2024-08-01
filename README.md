# My Cheat Sheet

## Git commands I am using often
initialize local repository
```bash
git init
```
add files
```bash
git add .
```
commit files
```bash
git commit -m "commit description"
```
push files to github
```bash
git push origin "branch name"
```
Create new branch
```bash
git checkout -b "new_branch_name"
```
Know the branch you are connected to
```bash
git branch
``` 

## Postgres commands in linux
Connect to postgres user
```bash
sudo -u postgres psql
```
Change the password of user
```sql
ALTER USER user_name PASSWORD 'newpassword';
```
Connect to database under specific user
```bash
psql -h host -d database -U user -p port_number -W
```
Start / Stop / Restart postgresql
```bash
sudo service postgresql start / stop / restart 
```
Switch connection to a new database
```sql
\c dbname
```
List availabe databases
```sql
\l
```
List available tables
```sql
\dt
```
Describe a table
```sql
\d table_name
```
List all users
```sql
\du
```
Exit psql
```sql
\q
```

## MySQL commands in linux

Connect to database under specific user
```bash
mysql -u username -p
```
Start / Stop / Restart MySQL
```bash
sudo service mysql start / stop / restart 
```
Create new database
```sql
CREATE DATABASE database_name;
```
Delete a database
```sql
DROP DATABASE database_name;
```
Show all databases
```sql
SHOW DATABASES;
```
Use a specific database
```sql
USE database_name;
```
Show tables in a database
```sql
SHOW TABLES;
```
Show table structure
```sql
DESCRIBE table_name;
```
Grant access to user on database
```sql
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
```
Change password of user
```sql
ALTER USER 'root'@'localhost' IDENTIFIED BY 'NewPassword';
```
Know the port mysql is working on
```sql
SHOW GLOBAL VARIABLES LIKE 'PORT';
```
Exit MySQL
```bash
exit
```
## Sqlite commands in linux
Connect to database under specific user
```bash
sqlite3 database_name.db
```
Exit sqlite
```bash
.exit
```
## Alembic commands
Create migration enviroment
```bash
alembic init alembic
```
Generating a base empty migration
```bash
alembic revision -m "message"
```
Autogenerating the migration
```bash
alembic revision --autogenerate -m "message"
```
Determine what the last migration applied to the database
```bash
alembic current
```
Shows every step from our initial empty migration to our current migration
```bash
alembic history
```
Upgrades the database
```bash
alembic upgrade head / [migration id] / +[number of steps]
```
Downgrade the database
```bash
alembic downgrade base / [migration id] / -[number of steps]
```
Marking a database migration as current
```bash
alembic stamp [migration id]
```
## React commands
Create a react app
```bash
npx create-react-app my-react-app
```
Start the react app
```bash
npm start
```
## nginx commands
Create a custom configuration file
```bash
sudo nano /etc/nginx/sites-available/your_domain
```
Configuration file content to write
```nginx
server {
    listen 80;
    listen [::]:80;

    server_name your_domain www.your_domain;
        
    location / {
        proxy_pass app_server_address;
        proxy_set_header Host $http_host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
Enable this configuration file
```bash
sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/
```
Test configuration file for syntax errors
```bash
sudo nginx -t
```
 Restart Nginx to apply your changes
```bash
sudo service nginx restart
```
## Other useful commands
Generate random 32 bit hexadecimal number
```bash
openssl rand -hex 32
```