## Data Importing

# Importing through command line
Open MySQL Workbench, Create a new database to store the tables you'll import (eg-FacilitySerivces) Then create the table using CREATE query

Copy the MySQL bin directory path: C:\Program Files\MySQL\MySOL Server 8.0\bin

Go to the folder in command line by using: cd path

Connect to MySQL database: mysql -u root -p(root is basically your username)

If you are logged in successfully, then set the global variables by using below command so that the data can be imported from local computer folder.
mysql> SET GLOBAL local_infile = 1;
Query OK, 0 rows affected (0.00 sec)

(you've just instructed MySQL server to allow local file upload from your computer)
Quit current server connection(mysql> quit)

Load the file from CSV file to the MySQL database. In order to do this, please follow the commands: 
(We'll connect with the MySQL server again with the local-infile system variable. This basically means you want to upload data into a file from a local machine)
mysql --local-infile=1 -u root -p (give password)

Show Databases; (It'll show all the databases in MySQL server.)
mysql> USE dbase; (makes the database that you had created in step 1 as default schema to use for the next sql scripts)

mysql> LOAD DATA LOCAL INFILE 'fullpath\\file.csv'<br>
INTO TABLE tablename
FIELDS TERMINATED BY','
ENCLOSED BY '"'
LINES TERMINATED BY '\r\n' IGNORE 1 ROWS;

* Note: VERY IMP-Please replace single backward (1) slash in the path with double back slashes (\\) instead of single slash
