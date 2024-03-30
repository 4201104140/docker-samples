sudo apt-get update
sudo apt install mysql-server
mysql --version

Now we will set the VALIDATE PASSWORD component.
sudo mysql_secure_installation

sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
bind-address            = 0.0.0.0
sudo systemctl restart mysql

sudo mysql -u root

create database shop;

show databases;

use shop;

CREATE USER 'shop'@'localhost' IDENTIFIED BY 'password';

CREATE USER 'shop'@'10.172.70.1' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'shop'@'10.172.70.1' WITH GRANT OPTION;
GRANT PRIVILEGE ON shop.Products TO 'shop'@'localhost';

GRANT ALL PRIVILEGES ON *.* TO 'shop'@'localhost' WITH GRANT OPTION;

GRANT CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES, RELOAD on *.* TO 'sammy'@'localhost' WITH GRANT OPTION;

DROP USER 'user'@'host';

SELECT User FROM mysql.user;