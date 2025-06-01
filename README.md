# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Рождественский Александр`



### Задание 1

1. Вход в админку Zabbix

![Снимок](/img/img5.jpg)
1. Список использованных команд для
```
sudo apt install postgresql -y
wget https://repo.zabbix.com/zabbix/7.2/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.2+ubuntu24.04_all.deb
dpkg -i zabbix-release_latest_7.2+ubuntu24.04_all.deb
apt update

apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent

sudo -u postgres createuser --pwprompt zabbix
sudo -u postgres createdb -O zabbix zabbix

zcat /usr/share/zabbix/sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

systemctl restart zabbix-server zabbix-agent apache2
systemctl enable zabbix-server zabbix-agent apache2

```
3. Так же был отредктирован файл `/etc/zabbix/zabbix_server.conf`


---
### Задание 2 
1. Cкриншот раздела Configuration
![hosts](/img/img2.png)

1. Cкриншот лога zabbix agent

![log](/img/img6.jpg)

1. Скриншот раздела Monitoring
![monitoring](/img/img4.png)

1. Список использованных команд
```
wget https://repo.zabbix.com/zabbix/7.2/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.2+ubuntu24.04_all.deb
dpkg -i zabbix-release_latest_7.2+ubuntu24.04_all.deb
apt update

apt install zabbix-agent2

apt install zabbix-agent2-plugin-mongodb zabbix-agent2-plugin-mssql zabbix-agent2-plugin-postgresql

systemctl restart zabbix-agent2
systemctl enable zabbix-agent2
```