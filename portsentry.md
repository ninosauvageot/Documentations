# Documentation portsentry

## Commandes :

installer portsentry

    sudo apt-get install portsentry

paramétrer portsentry

    nano /etc/portsentry/portsentry.conf

remplacer :

    ADVANCED_PORTS_TCP="1024"
    ADVANCED_PORTS_UDP="1024"

par : 

    ADVANCED_PORTS_TCP="1024,443,80,22,21"
    ADVANCED_PORTS_UDP="1024,21"

remplacer :

    BLOCK_UDP="0"
    BLOCK_TCP="0"

par :

    BLOCK_UDP="1"
    BLOCK_TCP="1"


ouvrir le fichier /etc/default/portsentry

    nano  /etc/default/portsentry

remplacer : 
   
    TCP_MODE="tcp"
    UDP_MODE="udp"

par: 

    TCP_MODE="atcp"
    UDP_MODE="audp"

redémarrer portsentry :

    sudo systemctl restart portsentry

vérifier le status de portsentry :

    sudo systemctl status portsentry

pour débanir une IP : 

1) effacer la ligne correpondant à l'ip dans le fichier :

    /etc/hosts.deny

2) entrer la commande : 

    sudo route del adressIP reject