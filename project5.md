##Client-Server Architecture With MYSQL
#install mysql for server and client
For server
`sudo apt update -y`
`sudo apt install mysql-server -y`
`sudo systemctl enable mysql`

for client
`sudo apt update -y`
`sudo apt install mysql-client -y`

#configure server to allow connection from remote host
`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`
replace ‘127.0.0.1’ with ‘0.0.0.0’
`sudo systemctl restart mysql`

#create new user for MYSQL server
`sudo mysql_secure_installation`
CREATE USER 'jolly_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
CREATE DATABASE test_db;
GRANT ALL ON test_db.* TO 'jolly_user'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
exit;

#connect server from client
`sudo mysql -u remote_user -h 172.31.47.9 -p`
![alt text](./images/show databases.PNG)
