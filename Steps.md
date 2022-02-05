# IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).

##### Create and configure two Linux-based virtual servers (EC2 instances in AWS).
Server A name - `mysql server`
Server B name - `mysql client`

img

On mysql server install MySQL Server software.
 
 update a list of packages in package manager:
 *sudo apt update*
 img
 
 *sudo apt install mysql-server*
 img
 
 Run the security script that comes pre-installed with MySQL. I did notconfigure the VALIDATE PASSWORD PLUGIN so that i can use a simple password for this project.

 *sudo mysql_secure_installation*
 img
 
 On the mysql client install the MySQL Client software.
 
 update a list of packages in package manager:
 *sudo apt update*
 img
 
  *sudo apt install mysql-client*
   img
   
  
  Creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups to allow TCP port 3306 on the client's private ip by default
  img
  
  Create a user on mysql-server
  *sudo mysql*
 
  *mysql>CREATE USER 'firstuser'@'localhost' IDENTIFIED BY 'pass123';*
  img
  
  Create a database
 *mysql> CREATE DATABASE first_database;*
  img
  
  Grant 'first user' priviledges to the the database 
  *mysql> GRANT ALL PRIVILEGES ON first_database . * TO 'firstuser'@'localhost';*
  img
  
  Reload all the privileges
  *mysql>FLUSH PRIVILEGES;*
  img
  
  exit to leave mysql environment
  
  Configure MySQL server to allow connections from remote hosts by Replacing  the bind address ‘127.0.0.1’ with ‘0.0.0.0’ 
  *sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf*
  img
  
  Restart mysql to apply chnages
  *sudo systemctl restart mysql*
  
  From mysql client Linux Server connect remotely to mysql server Database Engine with the mysql utility 
  
  
  
