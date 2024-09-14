# Домашнее задание Александра Липовецкого по занятию "Система мониторинга Zabbix"

vm-zabbix

ROOT

    wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-2+ubuntu24.04_all.deb
    dpkg -i zabbix-release_7.0-2+ubuntu24.04_all.deb
    apt update
    apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts
    exit
    systemctl restart zabbix-server apache2
    systemctl enable zabbix-server apache2
    systemctl status  zabbix-server

VM-SAM

    sudo apt update
    sudo apt upgrade
    sudo apt install postgresql
    sudo -s
    sudo -u postgres createuser --pwprompt zabbix
    sudo -u postgres createdb -O zabbix zabbix
    zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
    sudo nano /etc/zabbix/zabbix_server.conf
    sudo -s
    
VM-SAM

    sudo -s
    
ROOT

    apt install zabbix-agent
    systemctl restart zabbix-agent
    systemctl enable zabbix-agent
    systemctl status zabbix-agent
    
vm-ansible

VM-SAM

    sudo apt upgrade
    sudo -s
    cd /etc/zabbix/zabbix_agentd.d/
    ll
    cd ..
    ll
    sudo nano zabbix_agentd.c
    sudo nano zabbix_agentd.conf
    sudo -s
    
ROOT

   wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-2+ubuntu24.04_all.deb
   dpkg -i zabbix-release_7.0-2+ubuntu24.04_all.deb
   apt update
   apt install zabbix-agent
   systemctl restart zabbix-agent
   systemctl enable zabbix-agent
   systemctl status zabbix-agent
   exit
   systemctl restart zabbix-agent
   systemctl status zabbix-agent
   tail -f /var/log/zabbix/zabbix_agentd.log
   



![Авторизация в админке](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Авторизация_в_админке.png)

![Configuration > Hosts](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Configuration_Hosts.png)

![Лог zabbix agent](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Log_zabbix_agent.png)

![Monitoring > Latest data](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Monitoring_Latest_data.png)






  
