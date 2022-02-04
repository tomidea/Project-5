# Project-5
IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).
TASK – Implement a Client Server Architecture using MySQL Database Management System (DBMS).
1. Create and configure two Linux-based virtual servers (EC2 instances in AWS).
    Server A name - `mysql server`
    Server B name - `mysql client`
    
2. On mysql server Linux Server install MySQL Server software.
3. On mysql client Linux Server install MySQL Client software.
4. Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your ‘mysql client’.
5. configure MySQL server to allow connections from remote hosts.
   *sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf*
   Replace ‘127.0.0.1’ to ‘0.0.0.0’ 
6. From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.
7. Check that you have successfully connected to a remote MySQL server and can perform SQL queries:
    *Show databases;*
