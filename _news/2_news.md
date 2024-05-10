---
layout: post
date: 2023-01-16 00:00:00
inline: true
related_posts: false
---

Installing a LEMP (Linux, Nginx, MySQL/MariaDB, PHP) stack on a Linux server is a popular choice for hosting dynamic websites and web applications. Here's a step-by-step guide on how to install LEMP:

Step 1: Update Package Repositories

Before installing any software, it's a good practice to update the package repositories to ensure you're installing the latest versions of the software packages. Run the following commands:

bash
Copy code
sudo apt update
sudo apt upgrade
For distributions other than Ubuntu, you may need to use a different package manager, such as yum for CentOS or dnf for Fedora.

Step 2: Install Nginx

Nginx is a lightweight and high-performance web server. Install it using the following command:

bash
Copy code
sudo apt install nginx
After installation, start the Nginx service and enable it to start on boot:

bash
Copy code
sudo systemctl start nginx
sudo systemctl enable nginx
Step 3: Install MySQL/MariaDB

You can choose either MySQL or MariaDB as the database server. Install your preferred database server using one of the following commands:

For MySQL:

bash
Copy code
sudo apt install mysql-server
For MariaDB:

bash
Copy code
sudo apt install mariadb-server
During the installation process, you'll be prompted to set a root password for the database server. Follow the instructions to complete the installation.

Start the MySQL or MariaDB service and enable it to start on boot:

bash
Copy code
sudo systemctl start mysql
sudo systemctl enable mysql
Step 4: Secure MySQL/MariaDB Installation (Optional but Recommended)

MySQL and MariaDB provide a script to secure the installation and set some security options. Run the following command and follow the instructions:

bash
Copy code
sudo mysql_secure_installation
Step 5: Install PHP

PHP is a server-side scripting language used for dynamic web content. Install PHP along with common PHP extensions using the following command:

bash
Copy code
sudo apt install php-fpm php-mysql
Step 6: Configure Nginx to Use PHP

Nginx needs to be configured to pass PHP requests to the PHP processor. Open the default Nginx configuration file:

bash
Copy code
sudo nano /etc/nginx/sites-available/default
Find the following block:

bash
Copy code
location ~ \.php$ {
    include snippets/fastcgi-php.conf;
    fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
}
Uncomment these lines if necessary (remove the # at the beginning of each line).

Save and close the file, then restart Nginx for the changes to take effect:

bash
Copy code
sudo systemctl restart nginx
Step 7: Test PHP Processing

Create a PHP test file in the Nginx document root directory to test PHP processing:

bash
Copy code
sudo nano /var/www/html/info.php
Add the following PHP code to the file:

php
Copy code
<?php
phpinfo();
?>
Save and close the file. Now, you can access this file in a web browser by navigating to http://your_server_ip/info.php. You should see the PHP information page if PHP is configured correctly.

Step 8: Firewall Configuration

If you have a firewall enabled (such as UFW), you need to allow traffic on port 80 (HTTP) and, if necessary, port 443 (HTTPS):

bash
Copy code
sudo ufw allow 'Nginx Full'
Step 9: Finalize Configuration

You have now successfully installed the LEMP stack on your server. You can now deploy your web applications or websites and configure Nginx server blocks as needed.

Remember to regularly update your server's software and follow security best practices to keep your LEMP stack secure and up-to-date.