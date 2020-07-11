# fail2ban

## **Explication de fail2ban**

fail2ban est un logiciel qui analyse les logs de connections (ex: ssh, Apache, ect...).

L'utilisateur met en place des jails (cellules). Les jails permettent de mettre des filtres qui vont surveiller les entrées des logs.

Au moment où le filtre correspond à la connection, des actions sont exécutées.

En clair, si il y a des connections répétés sur une machine, le filtre bannis l'ip.

## **Installer, démarrer et vérifier fail2ban**

1. Pour installer fail2ban il faudra faire :

>sudo apt-get install fail2ban

**Rappel : sudo = admin**

2. Maintenant nous allons démarrer fail2ban et pour ça il faudra faire :

>systemctl start fail2ban

3. À la suite de ça, nous allons créer un démmarage automatique, pour ça il vous faudra faire :

>systemctl enable fail2ban

4. Maintenant nous allons vérifier l'état de fail2ban (et aussi des jails, si vous en avait installer. **à voir dans "Configurer fail2ban"**), il faudra faire :

>systemctl status fail2ban

Si la réponse comporte du rouge et le mot "failed" " sur la ligne commençant par "Active :", les dernières lignes du message indiquent les raisons de l'échec et permettent sa correction.

## **Configurer fail2ban**

Pour activer la surveillance des connexion SSH, il suffit d'ajouter dans le fichier /etc/fail2ban/jail.d/defaults-debian.conf. vous trouverez ceci :

    [sshd]
    enabled = true

Si vous avez besoin de spécifier un jail comme par exemple : quand SSH n'est pas en écoute sur un port standard, un fichier de log particulier, ou un nombre de tentatives différent de la valeur par défaut.

    [sshd]

    enabled = true
    port = 22
    logpath = /var/log/auth.log
    maxretry = 5

Après l'opération effectuer il faut redémarrer fail2ban :

>sudo systemctl restart fail2ban

pour vérifier si vos jails en question à bien était correctement lancées, faites :

>sudo fail2ban-client status

le résultat devrait ressembler à ceci :

    Status
    |- Number of jail:      3
    `- Jail list:           apache, proftpd,sshd

vous pouvez contrôlées les jails séparément avec les clés start,stop,status. ex :

>sudo fail2ban-client stop sshd

réponse :

>Jail stopped

Pour examiner les logs de fail2ban, nous allons utiliser la commande tail qui va permettre de voir les mots/paragraphes du fichier en questions. Pour ça faites:

>tail -f /var/log/fail2ban.log

## **voir les personnes Bannis, les Dé-bannir ou bannir une ip**

pour voir les personnes bannis grâce à l'un de vos jails, rien de plus simple, faites :

>fail2ban-client status [Nom du jail]

**rappel : [Nom du jail] = (ex. sshd, ect...)**

Pour dé-bannir une ip, il faudra faire :

>fail2ban-client set [nom du jail] unbanip [IP concerné]

Pour bannir une ip, il faudra faire :

>fail2ban-client set [nom du jail] banip [IP à bannir]