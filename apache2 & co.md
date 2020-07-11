# Comment voir son site en réseau local

## **Liste outils**

Je vous site tous les outils qui nous seront indispensable (à mon avis)

- avoir un système d'exploitation linux
- avoir apache2
- avoir un site
- avoir le logiciel FileZilla (optionnelle)

## **Installer apache2**

On va commencer par la commande pour l'installer

>sudo apt-get install apache2

**Rappel : sudo (pour ceux qui non pas les droits admin)**

## **Mettre son site sur apache2**

On va aller à l'endroit suivant pour y mettre le site. (De base, il y a deja une page index qui est installé en même temps que apache2)

>/var/www/html

Si, votre linux est un ordinateur virtuel et que votre site est sur un notre.

Alors, on va utiliser FileZila

## **Explication et utilisation de FileZilla**

1. L'explication

FileZilla permet de transférer ces fichiers à partir d'une connexion SSH ou autres.

2. Pour son utilisation

Lancer FileZilla

Mettez l'ip de l'ordinateur au quelle vous voulez faire une connexion dans le cadre "hôte"

Mettez votre identifiant et mot de passe

Mettez le port 22 pour une connexion SSH (mais vous pouvez mettre une autre connexion si vous connaissez autre choses)

Et faites "connexion rapide"

À la suite de ça, allez dans

>/var/www/html

Pour y déposer votre site

## **Pour voir le site sur un navigateur**

Mettez tous simplement l'ip locale de la machine qu'il héberge (ex:192.168.1.20)

**Rappel : pour connaitre son ip taper la commande : ip a**

Et vous pourrez voir votre magnifique site.