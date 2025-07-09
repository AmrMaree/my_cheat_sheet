# My Cheat Sheet

## Git commands
Initialize local repository
```bash
git init
```
Add a remote repository
```bash
git remote add origin [repository url]
```
Stage changes for the next commit
```bash
git add .
```
Commit staged changes
```bash
git commit -m "commit description"
```
Push changes to a remote repository
```bash
git push origin [branch name]
```
Pull changes from a remote repository
```bash
git pull origin [branch name]
```
Create new branch but doesn't switch to it
```bash
git branch [branch name]
```
Create new branch and switches to it
```bash
git checkout -b [new branch name]
```
Know the branch you are connected to
```bash
git branch
``` 
Switch to another branch
```bash
git checkout [branch name]
```
Check the status of your files
```bash
git status
```
Clone an existing repository
```bash
git clone [repository url]
```
Merge with another branch
```bash
git merge [other branch]
```
Configure user information
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```
Merge one branch into another

```bash
git checkout target-branch
git merge source-branch
```

 Merge by overwriting the target branch with the source branch’s content

```bash
git checkout target-branch
git reset --hard source-branch
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
## WSL commands
List your installed WSL distributions
```bash
wsl --list --verbose || wsl -l -v
```
Restart WSL
```bash
wsl --shutdown
wsl
```
Tells you distrubution name 
```bash
lsb_release -a
```
## Move WSL from one drive to another
List your installed WSL distributions
```bash
wsl --list --verbose
```
Export your desired distribution (e.g., Ubuntu-20.04) to a file on the drive you want to move to (e.g., D:\\)
```bash
wsl --export Ubuntu-20.04 D:\wsl\ubuntu.tar
```
Unregister the current WSL distribution
```bash
wsl --unregister Ubuntu-20.04
```
Create a directory on the D: drive where you want to store the WSL files
```bash
mkdir D:\wsl\ubuntu
```
Import the distribution from the exported file
```bash
wsl --import Ubuntu-20.04 D:\wsl\ubuntu D:\wsl\ubuntu.tar
```
Start your WSL distribution to ensure it’s working correctly
```bash
wsl -d Ubuntu-20.04
```
## 🐍 NumPy
Import NumPy
```python
import numpy as np
```
Creates a 1D array from a list
```python
arr1 = np.array([1, 2, 3])
```
Creates a 2D array (matrix) from a nested list
```python
arr2 = np.array([[1, 2], [3, 4]])
```
Creates a 3x3 array filled with zeros   
```python
zeros = np.zeros((3, 3))
```
Creates a 2x2 array filled with ones
```python
ones = np.ones((2, 2))
```
Creates a 3x3 array with random integers between 0 and 9
```python
random_arr = np.random.randint(0, 10, size=(3, 3))
```
Array Operations
```python
arr = np.array([1, 2, 3])
arr_sum = arr + 10       # Adds 10 to each element.
arr_product = arr * 2    # Multiplies each element by 2.
```
Element-wise Operations
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
sum_arr = arr1 + arr2   # Adds corresponding elements.
dot_product = np.dot(arr1, arr2)   # Computes the dot product of two arrays.
arr_T = arr2.T   # Transposes a 2D array 
```
Indexing and Slicing
```python
arr = np.array([1, 2, 3, 4, 5])
first_element = arr[0]    # Access the first element.
last_element = arr[-1]    # Access the last element.
slice_arr = arr[1:4]      # Access elements from index 1 to 3.
```
Statistical Functions
```python
arr = np.array([1, 2, 3, 4, 5])
mean = np.mean(arr)       # Calculates the mean of the array.
median = np.median(arr)   # Calculates the median of the array.
std = np.std(arr)         # Calculates the standard deviation of the array.
```
Logical Operations
```python
greater_than_3 = arr > 3   # Creates a boolean array where True indicates elements greater than 3.
```
Reshapes the array to have 5 rows and 1 column
```python
reshaped = arr.reshape(5, 1)
```
Concatenates two arrays
```python
arr1 = np.array([1, 2])
arr2 = np.array([3, 4])
concat = np.concatenate((arr1, arr2))
```
## 🐼 Pandas 
Import Pandas
```python
import pandas as pd
```
Creating DataFrames from a dictionary
```python
data = {"Name": ["Alice", "Bob", "Charlie"], "Age": [25, 30, 35]}
df = pd.DataFrame(data)
```
Creating DataFrames from a list of lists
```python
data = [["Alice", 25], ["Bob", 30], ["Charlie", 35]]
df = pd.DataFrame(data, columns=["Name", "Age"])
```
Read CSV file
```python
df = pd.read_csv("file.csv")
```
Save DataFrame to CSV
```python
df.to_csv("output.csv", index=False)
```
Viewing Data
```python
df.head()       # Displays the first 5 rows.
df.tail()       # Displays the last 5 rows.
df.info()       # Displays information about the DataFrame.
df.describe()   # Generates summary statistics for numeric columns.
```
Selecting Data
```python
ages = df["Age"]  # Selects the "Age" column.
first_row = df.loc[0]  # Selects the first row by label/index.
first_row = df.iloc[0]  # Selects the first row by integer position.
```
Filtering Data
```python
filtered_df = df[df["Age"] > 30]  # Filter rows where age > 30
```
Add a New Column
```python
df["Salary"] = [50000, 60000, 70000]
```
Deleting Columns
```python
df = df.drop(columns=["Salary"])
```
Sorting
```python
df = df.sort_values(by="Age", ascending=True)  # Sort by Age in ascending order
```
Grouping Data
```python
grouped = df.groupby("Name").mean()  # Groups the DataFrame by "Name" and calculates the mean of numeric columns.
```
Detect missing values
```python
missing_values = df.isnull()
```
Fill missing values
```python
df["Age"] = df["Age"].fillna(30)
```

## Other useful commands
Generate random 32 bit hexadecimal number
```bash
openssl rand -hex 32
```