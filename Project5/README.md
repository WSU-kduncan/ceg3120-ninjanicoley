Part 1
1. Link below was used for the cf-template (luedemanP5-cf-template.yml)
https://github.com/pattonsgirl/Fall2021-CEG3120/blob/main/Projects/Project5/cf-template.yml



Part 2 - Setup Load Balancing TODOs
1. Description of how /etc/hosts file is configured

2. Document how to SSH in between the systems utilizing their private IPs. 

3. HAProxy config and documentation
a. How to install package
b. What file(s) were modified and their location. 
c. What config were set (if any).
d. How to restart the service after configuration change.
e. Resources used (websites).

4. Webserver 1 & 2 config and documentation

To configure the webserver, we must install apache2 with sudo apt install apache2.
Check the status of apache2 by running sudo systemctl status apache2.
We then make the directory to store everything: sudo mkdir/var/www/hostnameChoice (I used my proxy IP)
Assign ownership with sudo chown -R $USER:$USER /var/www/hostnameChoice
We also have to change those permissions with chmod -R 755 /var/www/hostnameChoice
and then add the index.html file to that directory. 
We run sudo nano /etc/apache2/sites-available/hostnameChoice.conf here and paste in the following: 
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName hostnameChoice
    ServerAlias hostnameChoice
    DocumentRoot /var/www/hostnameChoice
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

Now that we have that done, we enable it with sudo a2ensite hostnameChoice.conf, disable sudo a2dissite 000-default.conf, reload if you have to, and then sudo apache2ctl configtest to test the configuration. 
If that all goes according to plan, we run sudo systemctl restart apache2. 

Resource used: 
https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-20-04

5. When connecting to the proxy server, take 2 screenshots:
a. one screenshot that shows content from "server 1".

b. one screenshot that shows content from "server 2".
