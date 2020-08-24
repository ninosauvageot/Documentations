# Documentation FusionInventory

## Commandes :

installer les paquets nécessaires :

    apt -y install dmidecode hwdata ucf hdparm
    apt -y install perl libuniversal-require-perl libwww-perl libparse-edid-perl
    apt -y install libproc-daemon-perl libfile-which-perl libhttp-daemon-perl
    apt -y install libxml-treepp-perl libyaml-perl libnet-cups-perl libnet-ip-perl
    apt -y install libdigest-sha-perl libsocket-getaddrinfo-perl libtext-template-perl
    apt -y install libxml-xpath-perl libyaml-tiny-perl
    apt -y install libnet-snmp-perl libcrypt-des-perl libnet-nbname-perl
    apt -y install libfile-copy-recursive-perl libparallel-forkmanager-perl
    apt-get install libnet-cups-perl libnet-ip-perl libwww-perl libparse-edid-perl libproc-daemon-perl libuniversal-require-perl libfile-which-perl libxml-treepp-perl libxml-xpath-perl libyaml-perl libtext-template-perl libhttp-daemon-perl libsocket-getaddrinfo-perl

installer les paquets

    wget https://github.com/fusioninventory/fusioninventory-agent/releases/download/2.5.2/fusioninventory-agent_2.5.2-1_all.deb
    wget https://github.com/fusioninventory/fusioninventory-agent/releases/download/2.5.2/fusioninventory-agent-task-collect_2.5.2-1_all.deb
    wget https://github.com/fusioninventory/fusioninventory-agent/releases/download/2.5.2/fusioninventory-agent-task-network_2.5.2-1_all.deb
    wget https://github.com/fusioninventory/fusioninventory-agent/releases/download/2.5.2/fusioninventory-agent-task-deploy_2.5.2-1_all.deb
    wget https://github.com/fusioninventory/fusioninventory-agent/releases/download/2.5.2/fusioninventory-agent-task-esx_2.5.2-1_all.deb

dépaquet les paquets

    dpkg -i fusioninventory-agent_2.5.2-1_all.deb
    dpkg -i fusioninventory-agent-task-collect_2.5.2-1_all.deb
    dpkg -i fusioninventory-agent-task-network_2.5.2-1_all.deb
    dpkg -i fusioninventory-agent-task-deploy_2.5.2-1_all.deb
    dpkg -i fusioninventory-agent-task-esx_2.5.2-1_all.deb

relancer et rechargé l'agent

    systemctl restart fusioninventory-agent

    systemctl reload fusioninventory-agent