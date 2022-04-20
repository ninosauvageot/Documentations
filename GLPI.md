# Documentation GLPI

## Commandes :

installer les paquets nécessaires :

    apt-get install apache2 mariadb-server mariadb-client php build-essential perl libapache2-mod-perl2 libxml-simple-perl libio-compress-perl libdbi-perl libapache-dbi-perl libdbd-mysql-perl libnet-ip-perl libsoap-lite-perl libxml-libxml-perl libmojolicious-perl nmap snmp php7.3-mysql php7.3-gd php7.3-mbstring php-ldap php-imap php-apcu php-xmlrpc php-soap php-cas php7.3-xml

configuration de GLPI :

    mysql_secure_installation

se connecter :

    mysql -u root -p

créer un utilisateur "user" avec le mot de passe "azerty"

    create user 'user'@'%' identified by 'azerty';

création de la base de donnée "glpi"

    create database glpi;

attribue tous les privilèges à "user" pour la base de donnée "glpi"

    grant all privileges on glpi.* TO 'user'@'%';

on recharge les droits et on quitte mariadb:

    flush privileges;

    exit;

on va se diriger vers /var/www/html pour aller supprimer l'index.html :

    cd /var/www/html

    rm index.html

on télécharge l’archive :

    wget https://github.com/glpi-project/glpi/releases/download/9.4.5/glpi-9.4.5.tgz

on extraie l’archive :

    tar -zxvf glpi-9.4.5.tgz

on modifie un fichier de configuration pour apache :

    nano /etc/apache2/sites-available/000-default.conf

modification du fichier :

    <virtualHost *:80>
            ServerAdmin webmaster@localhost
            DocumentRoot /var/www/html/glpi
            <Directory /var/www/html/glpi>
                    Options Indexes FollowSymLinks
                    AllowOverride All
                    Require all granted
            </Directory>
            ErrorLog ${APACHE_LOG_DIR}/error.log
            CustomLog ${APACHE_LOG_DIR}/access.log combined
    </virtualHost>

on modifie les droits :

    chown -R www-data:www-data /var/www/html/glpi

on redémarre le serveur web :

    systemctl restart apache2

