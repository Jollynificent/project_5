For server
`sudo apt update -y`
`sudo apt install mysql-server -y`
`sudo systemctl enable mysql`

for client
`sudo apt update -y`
`sudo apt install mysql-client -y`


Server
`sudo mysql_secure_installation`
CREATE USER 'jolly_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
CREATE DATABASE test_db;
GRANT ALL ON test_db.* TO 'jolly_user'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
exit;
`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`
‘127.0.0.1’ to ‘0.0.0.0’
`sudo systemctl restart mysql`

CLient
`sudo mysql -u remote_user -h <private IP address> -p`
