# Домашнее задание Александра Липовецкого по занятию "Система мониторинга Zabbix"

vm-zabbix

ROOT

    1  wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-2+ubuntu24.04_all.deb
    2  dpkg -i zabbix-release_7.0-2+ubuntu24.04_all.deb
    3  apt update
    4  apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts
    5  exit
    6  systemctl restart zabbix-server apache2
    7  systemctl enable zabbix-server apache2
    8  systemctl status  zabbix-server
    
VM-SAM
1  sudo apt update
2  sudo apt upgrade
3  sudo apt install postgresql
4  sudo -s
5  sudo -u postgres createuser --pwprompt zabbix
6  sudo -u postgres createdb -O zabbix zabbix
7  zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
8  sudo nano /etc/zabbix/zabbix_server.conf
9  sudo -s
VM-SAM
12 sudo -s
ROOT
11  apt install zabbix-agent
12  systemctl restart zabbix-agent
13  systemctl enable zabbix-agent
14  systemctl status zabbix-agent

vm-ansible
VM-SAM
719  sudo apt upgrade
720  sudo -s
721  cd /etc/zabbix/zabbix_agentd.d/
722  ll
723  cd ..
724  ll
725  sudo nano zabbix_agentd.c
726  sudo nano zabbix_agentd.conf
727  sudo -s

ROOROOT
104  wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-2+ubuntu24.04_all.deb
105  dpkg -i zabbix-release_7.0-2+ubuntu24.04_all.deb
106  apt update
107  apt install zabbix-agent
108  systemctl restart zabbix-agent
109  systemctl enable zabbix-agent
110  systemctl status zabbix-agent
111  exit
112  systemctl restart zabbix-agent
113  systemctl status zabbix-agent
114  tail -f /var/log/zabbix/zabbix_agentd.log

![Авторизация в админке](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Авторизация_в_админке.png)

![Configuration > Hosts](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Configuration_Hosts.png)

![Лог zabbix agent](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Log_zabbix_agent.png)

![Monitoring > Latest data](https://github.com/AleksandrLipovetskiy/zabbix_hw/blob/main/Monitoring_Latest_data.png)






  
