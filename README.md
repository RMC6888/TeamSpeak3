# TeamSpeak3
Di upload oleh JZ02BNK

untuk linux server

teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2

teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2

Running on Debian server 11 Bullseye

[teamspeak-3.0.13.6.tar](https://github.com/RMC6888/TeamSpeak3-Linux-server/releases/download/TS3-JZ02BNK/teamspeak-3.0.13.6.tar)

[teamspeak-3.0.13.8.tar](https://github.com/RMC6888/TeamSpeak3-Linux-server/releases/download/TS3-JZ02BNK/teamspeak-3.0.13.8.tar)

====================================

apt-get update && apt-get upgrade

adduser --disabled-login teamspeak

cd /home/teamspeak

wget https://github.com/RMC6888/TeamSpeak3/releases/download/TS3-JZ02BNK/teamspeak-3.0.13.8.tar

tar xvf teamspeak-3.0.13.8.tar

touch /home/teamspeak/.ts3server_license_accepted

nano /lib/systemd/system/teamspeak.service

[Unit]
Description=TeamSpeak 3 Server<br>
After=network.target<br>
[Service]<br>
WorkingDirectory=/home/teamspeak/<br>
User=teamspeak<br>
Group=teamspeak<br>
Type=forking<br>
ExecStart=/home/teamspeak/ts3server_startscript.sh start inifile=ts3server.ini<br>
ExecStop=/home/teamspeak/ts3server_startscript.sh stop<br>
PIDFile=/home/teamspeak/ts3server.pid<br>
RestartSec=15<br>
Restart=always<br>
[Install]<br>
WantedBy=multi-user.target<br>

systemctl enable teamspeak.service

systemctl start teamspeak.service

systemctl | grep teamspeak.service

service teamspeak status

ufw allow 9987/udp<br>
ufw allow 30033/tcp<br>
ufw allow 10011/tcp<br>
ufw allow 10022/tcp<br>
ufw allow 10080/tcp<br>

cat /home/teamspeak/logs/ts3server_*

====================================

Video tutorial

[![Tonton Video](https://img.youtube.com/vi/bMgNPVSAphk/maxresdefault.jpg)](https://www.youtube.com/watch?v=bMgNPVSAphk)
