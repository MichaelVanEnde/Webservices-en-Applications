###Project Webapplications

##Configuren en Instaleren Webserver
Instalatie aan de hand van deze tutorials[Raspberry PI](https://www.raspberrypi.org/documentation/remote-access/web-server/apache.md) [DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu)

#Instaleren van openssh
Om dat de virtuele machine gebruikt maakt van een querty toetsenbord is het aangenamer om te wereken via putty. zo kunnen we ook commando's plakken.
het comando:
'''
sudo apt-get install openssh-server openssh-client
'''

#apache2
apache is zeer simpel te instaleren aan de hand van volgend commando:
'''
sudo apt-get install apache2
'''

#Php 
Instaleren van php
'''
sudo apt-get install php libapache2-mod-php
'''

hoe testen we dat de installatie werkt en apache php kan gebruiken? 
we vervangen de index pagina van apache met een index.php en voeren een simpel php comando uit
dit commando geeft mooi alle info over php weer.
'''
<?php phpinfo(); ?>
'''

#MySql
MySql server pakket binnenhalen 
'''
sudo apt-get install mysql-server
'''
Er wordt automatich gevraagd om een wachtwoord aan te maken. het is dan ook aangeraden om dit veld niet leeg te laten!

eens alles geinstaleerd is kunt u MySql runnen aan de hand van dit commando:
'''
mysql -u root -p
'''
Vervolgens nieuwe gebruiker aanmaken
'''
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
'''
Gebruiker ook de nodige permissies geven
'''
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
'''

##Linken
het is belangrijk dat we php en MySql aan apache linken
'''
sudo apt-get install apache2-utils libapache2-mod-php5 php5-mysql php5-gd php5-mcrypt 
'''
in mijn geval laat ik de 5 achter php vallen.
anders krijg ik hierdoor error's omdat hij php5 niet kan vinden omdat ik php7 heb

het volgende is het enabele van rewrite voor apache
'''
sudo a2enmod rewrite
'''
zo kunnen we later de URL aanpassen
