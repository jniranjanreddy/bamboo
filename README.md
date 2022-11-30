## How to install Bamboo in Ubuntu 20.x
## Source - https://www.hackerxone.com/2022/02/11/steps-to-install-configure-bamboo-on-ubuntu-20-04-lts/
```
apt-get update
apt-get install openjdk-8-jdk
java -version


apt install postgresql postgresql-contrib
sudo -u postgres psql
create database bamboo;
create user user_bamboo with encrypted password 'Password';
grant all privileges on database bamboo to user_bamboo;
\q

cd /opt
wget https://www.atlassian.com/software/bamboo/downloads/binary/atlassian-bamboo-8.1.2.tar.gz
tar -xvf atlassian-bamboo-8.1.2.tar.gz
mv atlassian-bamboo-8.1.2 bamboo
cd /opt/bamboo/

mkdir -p /home/ubuntu/bamboo/bamboo-home
vim /opt/bamboo/atlassian-bamboo/WEB-INF/classes/bamboo-init.properties
bamboo.home=/home/ubuntu/bamboo/bamboo-home

cd /opt/bamboo/bin
./start-bamboo.sh

ufw allow 8085
http://server-ip:8085

```
