# Podman
MicroOS

podman pull docker.io/library/mariadb

mkdir -p /opt/var/lib/mysql/data

podman run --name db-mariadb -p 3306:3306 -v /opt/var/lib/mysql/data:/var/lib/mysql:Z -e MYSQL_ROOT_PASSWORD=rootpass -e MYSQL_DATABASE=mydb -e MYSQL_USER=myuser -e MYSQL_PASSWORD=mypass -d docker.io/library/mariadb

podman inspect db-mariadb

podman exec -it db-mariadb /bin/bash

grep mysql /etc/passwd

ps -aux | grep mysqld | grep -v grep

ip addr

mysql -u root -h <IP> -p
