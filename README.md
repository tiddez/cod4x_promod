# cod4x_promod
Cod4x promod server 
Install linux, in my case use Ubuntu Server 20 LTS

apt update && apt upgrade
apt install screen
dpkg --add-architecture i386
apt update
sudo -i cd /etc/apt/sources.list.d | echo "deb http://old-releases.ubuntu.com/ubuntu/ raring main restricted universe multiverse" >ia32-libs-raring.list
sudo apt install libc6:i386 libncurses5:i386 libstdc++6:i386
cd /home
mkdir servers
cd servers
wget https://drive.google.com/file/d/18UkFG_ksl_5p3xkbf7P11bRGBr7ubLiX/view?usp=sharing
apt install unzip
unzip cod4x_server-linux_20.1.zip
cd cod4
chmod -R 777 cod4x18_dedrun main pb mods
upload mod and pb file and unzip
nano start.sh
#!/bin/bash
screen -dmS cod4 ./cod4_lnxded +set dedicated 2 +set sv_authorizemode 0 +set rcon_password seekers123 +set sv_punkbuster 1 +exec server.cfg +set sv_maxclient 32 +set net_port 28960 +set fs_basepath /home/servers/cod4 +set fs_homepath /home/servers/cod4 +set fs_game mods/pml220 +map_rotate
sudo chmod +x start.sh
cd /home/servers/cod4
./start.sh

Install htop to monitor the process "Screen cod4x18..."
