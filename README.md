# Server Setup Documentation
A LAMP stack is a web development platform consisting of Linux, Apache, MySQL, and PHP, commonly used to host dynamic web applications because it is open-source, widely supported, and well-documented. Ubuntu provides packages for all components, making installation and maintenance straightforward with the apt package manager.

## Installation Steps
1. System update
- sudo apt update
  sudo apt upgrade -y
  
2. Install Apache
- sudo apt install apache2 -y
  sudo systemctl enable apache2
  sudo systemctl start apache2
  sudo systemctl status apache2
Verify in browser

3. Install MySQL
- sudo apt install mysql-server -y
  sudo systemctl enable mysql
  sudo systemctl start mysql
  sudo systemctl status mysql
Run security script:
- sudo mysql_secure_installation
Test login:
- sudo mysql

4. Install PHP
- sudo apt install php libapache2-mod-php php-mysql -y
  php -v
Restart Apache to load PHP

5. Web root and file permissions
- /var/www/html
- sudo chown -R $USER:www-data /var/www/html
  sudo chmod -R 750 /var/www/html

## MySQL: create a database and user
- CREATE DATABASE library_opac CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
  CREATE USER 'opac_user'@'localhost' IDENTIFIED BY 'STRONG_PASSWORD_HERE';
  GRANT ALL PRIVILEGES ON library_opac.* TO 'opac_user'@'localhost';
  FLUSH PRIVILEGES;
