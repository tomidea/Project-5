# IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).

##### STEP 1: Create and configure two Linux-based virtual servers (EC2 instances in AWS).
Server A name - `mysql server`
Server B name - `mysql client`

  <img width="1029" alt="client-server instance" src="https://user-images.githubusercontent.com/51254648/152635547-21212c31-cda0-4b04-9b93-0915dc764087.png">


STEP 2: On mysql server install MySQL Server software.
 
 update a list of packages in package manager:
 
 *sudo apt update*
 
 <img width="769" alt="sudo apt udate" src="https://user-images.githubusercontent.com/51254648/152635106-f3c1515a-9fb3-4a8b-b7bb-efae090dc3a2.png">

 
 *sudo apt install mysql-server*
 
<img width="829" alt="sudo install mysql-server" src="https://user-images.githubusercontent.com/51254648/152635109-bf5e9233-f4bb-4db8-a413-36832dc42dd5.png">
 
 
 STEP 3: Run the security script that comes pre-installed with MySQL. I did notconfigure the VALIDATE PASSWORD PLUGIN so that i can use a simple password for this project.

 *sudo mysql_secure_installation*
 
 <img width="545" alt="secure installation" src="https://user-images.githubusercontent.com/51254648/152635111-276018c0-6e1c-47ba-b89f-9e67714888c3.png">

 
STEP 4: On the mysql client install the MySQL Client software.
 
 update a list of packages in package manager:
 
 *sudo apt update*
 
 <img width="798" alt="apt update client" src="https://user-images.githubusercontent.com/51254648/152635112-71383717-563d-4615-8265-a6cce0400d57.png">

 
  *sudo apt install mysql-client*
 
 <img width="795" alt="install mysql client" src="https://user-images.githubusercontent.com/51254648/152635113-578a7343-5240-4b2b-814c-427bc130d207.png">

   
  
  STEP 5: Creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups to allow TCP port 3306 using the client's private IP 
  
  <img width="1190" alt="inbound rule" src="https://user-images.githubusercontent.com/51254648/152635114-2b2ec2e5-a1c7-42ac-b6d8-d04958a0f9e0.png">

  
 STEP 6: Create a user on mysql-server
  
  *sudo mysql*

*mysql>CREATE USER 'db_user'@'%' IDENTIFIED BY 'pass123';*

<img width="419" alt="create user" src="https://user-images.githubusercontent.com/51254648/152635122-8b84512e-bcf5-4c50-84f5-8ca868917b1b.png">
  
  
  STEP 7: Create a database
 
 *mysql> CREATE DATABASE first_database;*
 
 <img width="292" alt="create db" src="https://user-images.githubusercontent.com/51254648/152635115-8f84bb10-3c5a-4f32-bdcc-56853f1e5fbd.png">

  
  STEP 8: Grant 'first user' priviledges to the the database 
  
  *mysql> GRANT ALL PRIVILEGES ON first_database . * TO 'firstuser'@'localhost';*
  
<img width="499" alt="grant privileges" src="https://user-images.githubusercontent.com/51254648/152635121-2ea33f92-f5ea-4f2f-a129-a9f532515428.png">
  
  
  STEP 9: Reload all the privileges with the code below
  
  *mysql>FLUSH PRIVILEGES;*
  
  <img width="267" alt="FLUSH PRIVILEGES" src="https://user-images.githubusercontent.com/51254648/152635116-196f15c3-9708-4f5c-9b85-7a60fa42f162.png">

  
  exit the mysql environment
  
  STEP 10: Configure MySQL server to allow connections from remote hosts by Replacing  the bind address ‘127.0.0.1’ with ‘0.0.0.0’ 
  
  *sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf*
  
  <img width="286" alt="bind address" src="https://user-images.githubusercontent.com/51254648/152635117-43147ee5-10f7-48c0-aea1-c982d3d9fe19.png">

Restart mysql to apply chnages
  
  *sudo systemctl restart mysql*
  
  ##### connect from client server
  From mysql client Linux Server connect remotely to mysql server Database Engine with the mysql utility 
  
  *mysql -u db_user -h 172.31.5.218 -p*

<img width="824" alt="show databse" src="https://user-images.githubusercontent.com/51254648/152635119-17f6225b-147e-4706-a865-0dea065d6e1d.png">


