-     Install package net-tools to run ifconfig command
:~$ sudo apt-get install net-tools -y

-     Configure a network interface (Check the current IP for my web server) 
:~$ ifconfig 

-     Reachability of a host on an internet
:~$ ping google.com  

-     Install apache2 to the vm
:~$ sudo apt update

:~$ sudo apt install apache2

-     Create directory "about" and folder "home" for new website in /var/www/html
:~$ sudo mkdir /var/www/html/about

:~$ sudo mkdir /var/www/html/home

-     Install package vim to run vims commands
:~$ sudo apt install vim -y 

-     Create web pages inside folder "about" , folder "home" and another one for default page , then I wrote the html code for each page.
:~$ sudo vim /var/www/html/about/index.html

:~$ sudo vim /var/www/html/home/index.html

:~$ sudo vim /var/www/html/index.html

-     Create subdomain file "contact" that be located under “~/contact” directory
:~$ sudo mkdir ~/contact

-     Create web pages inside subdomain file "contact" , then I wrote the html code for the contact page.
:~$ sudo vim ~/contact/index.html

-     For the "contact" subdomain, make sure grant apache2 the required permission (chmod: to modify the file permissions).
:~$ sudo chmod -R 755 ~/contact

-     For the "contact" subdomain, make sure grant apache2 the required permission (chmod: to modify the file permissions).
:~$ sudo chmod -R 755 ~/contact

-     To make sure the apache user, which is “www-data”, has the required permission to the contact folder
:~$ sudo chown -R www-data ~/contact

-     Make subdomains then modified the ServerName and DocumentRoot then pressed to ctrl+c twice and wrote " :wq "  
:~$ cd /etc/apache2/sites-available

:/etc/apache2/sites-available$ sudo vim 000-default.conf 

:/etc/apache2/sites-available$ sudo vim www.about.rahafshami.com.conf 

:/etc/apache2/sites-available$ sudo vim www.home.rahafshami.com.conf 

![330132855_3440294186296645_1807383859319545175_n](https://user-images.githubusercontent.com/75248980/221284561-ec15d154-05ce-429c-bb37-faf4398bab6f.jpg)

-     Make subdomains then modified the ServerName , DocumentRoot and  Directory then pressed to ctrl+c twice and wrote " :wq "  
:/etc/apache2/sites-available$ sudo vim www.contact.rahafshami.com.conf 

![330132855_3440294186296645_1807383859319545175_n](https://user-images.githubusercontent.com/75248980/221284630-48e6e8dd-9ec3-4c44-b9e7-1eeedb8b9a0f.jpg)

-     Rename hostname of my web server 
:/etc/apache2/sites-available$ sudo vim /etc/hostname

-     Wrote IP with hostname
:/etc/apache2/sites-available$ sudo vim /etc/hosts





