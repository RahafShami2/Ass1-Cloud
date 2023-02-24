-     Install package net-tools to run ifconfig command
:~$ ``sudo apt-get install net-tools -y``


-     Configure a network interface (Check the current IP for my web server) 
:~$ ifconfig 

![0e4d2037-3b27-400e-ab2b-c7557a8e4620](https://user-images.githubusercontent.com/75248980/221287602-e67553ed-69e0-4d16-a2c2-7dd254b17419.jpg)


-     Reachability of a host on an internet
:~$ ping google.com  

![2a1a87ab-8673-4636-a323-885c58a85306](https://user-images.githubusercontent.com/75248980/221287886-93a92b2b-d836-47ab-a959-308d404745a1.jpg)


-     Install apache2 to the vm
:~$ sudo apt update

:~$ sudo apt install apache2

-     Create directory "about" and folder "home" for new website in /var/www/html
:~$ sudo mkdir /var/www/html/about

:~$ sudo mkdir /var/www/html/home

-     Install package vim to run vims commands
:~$ sudo apt install vim -y 

-     Create web pages inside folder "about" , folder "home" and another one for default page , then I wrote the html code for each page then pressed to ctrl+c twice and wrote " :wq ". 
:~$ sudo vim /var/www/html/about/index.html

:~$ sudo vim /var/www/html/home/index.html

:~$ sudo vim /var/www/html/index.html

![35ea13c7-233c-4cb5-a1d4-91a12904bb7d](https://user-images.githubusercontent.com/75248980/221288336-dd8085c4-1bdc-4369-b9a4-c8606f894357.jpg)


-     Create subdomain file "contact" that be located under “~/contact” directory
:~$ sudo mkdir ~/contact

-     Create web pages inside subdomain file "contact" , then I wrote the html code for the contact page then pressed to ctrl+c twice and wrote " :wq "
:~$ sudo vim ~/contact/index.html


-     For the "contact" subdomain, make sure grant apache2 the required permission (chmod: to modify the file permissions).
:~$ sudo chmod -R 755 ~/contact

-     To make sure the apache user, which is “www-data”, has the required permission to the contact folder
:~$ sudo chown -R www-data ~/contact

-    Going into the configuration files directory
:~$ cd /etc/apache2/sites-available/

-    Since Apache came with a default VirtualHost file, let’s use that as a base, to match subdomain name 
:/etc/apache2/sites-available$ sudo cp 000-default.conf www.about.rahafshami.com 

:/etc/apache2/sites-available$ sudo cp 000-default.conf www.home.rahafshami.com

:/etc/apache2/sites-available$ sudo cp 000-default.conf www.contact.rahafshami.com


-     Make subdomains then modified the ServerName and DocumentRoot then pressed to ctrl+c twice and wrote " :wq "  
:/etc/apache2/sites-available$ sudo vim 000-default.conf 

:/etc/apache2/sites-available$ sudo vim www.about.rahafshami.com.conf 

:/etc/apache2/sites-available$ sudo vim www.home.rahafshami.com.conf 

![330132855_3440294186296645_1807383859319545175_n](https://user-images.githubusercontent.com/75248980/221284561-ec15d154-05ce-429c-bb37-faf4398bab6f.jpg)


-     Make subdomains then modified the ServerName , DocumentRoot and  Directory then pressed to ctrl+c twice and wrote " :wq "  
:/etc/apache2/sites-available$ sudo vim www.contact.rahafshami.com.conf 

![330132855_3440294186296645_1807383859319545175_n](https://user-images.githubusercontent.com/75248980/221284630-48e6e8dd-9ec3-4c44-b9e7-1eeedb8b9a0f.jpg)


 -     Activate the virtual hosts configuration file to enable it.
:/etc/apache2/sites-available$ sudo a2ensite www.about.rahafshami.com www.contact.rahafshami.com www.home.rahafshami.com


 -    To load the new site, we restart Apache 
:/etc/apache2/sites-available$ systemctl reload apache2

OR :/etc/apache2/sites-available$ systemcrl restart apache2
 

-     Rename hostname of my web server then pressed to ctrl+c twice and wrote " :wq "
:/etc/apache2/sites-available$ sudo vim /etc/hostname

![f398bc92-a49a-4074-8e23-03999be6983c](https://user-images.githubusercontent.com/75248980/221286892-2b65d8df-6738-4882-9222-f107e8c524a9.jpg)


-     Wrote IP with hostname then pressed to ctrl+c twice and wrote " :wq "
:/etc/apache2/sites-available$ sudo vim /etc/hosts

![49a0c078-1fc0-4e62-ac93-65dc24832bbc](https://user-images.githubusercontent.com/75248980/221286846-35d269e9-51c2-4aa6-bd31-78940b972dee.jpg)





