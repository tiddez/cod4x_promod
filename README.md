# cod4x_promod

Cod4x promod server 

Install linux, in my case use Ubuntu Server 20 LTS

apt update && apt upgrade
apt install screen
dpkg --add-architecture i386
apt update
sudo -i cd /etc/apt/sources.list.d | echo "deb http://old-releases.ubuntu.com/ubuntu/" >ia32-libs-raring.list
sudo apt install libc6:i386 libncurses5:i386 libstdc++6:i386
sudo apt install steamcmd
ln -s /root/.local/share/Steam/steamcmd/linux32/steamclient.so /home/servers/cod4
cd /home
mkdir servers
cd servers
wget https://ia804705.us.archive.org/15/items/cod4_linux_server_files_201501/cod4_linux_server_files.zip
apt install unzip
unzip cod4x_server-linux_20.1.zip
cd cod4
chmod -R 777 cod4x18_dedrun main pb mods
upload mod and pb file and unzip
nano start.sh
#!/bin/bash
screen -dmS cod4 ./cod4x18_dedrun +set dedicated 2 +set net_port 28960 +set sv_punkbuster 1 +set fs_game mods/pml220pub +exec server.cfg +set rcon_password qwe12345678 +map_rotate
sudo chmod +x start.sh
cd /home/servers/cod4
./start.sh

Install htop to monitor the process "Screen cod4x18..."

#Colocar o server.cfg dentro da pasta main
