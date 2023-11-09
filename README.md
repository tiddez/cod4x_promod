# cod4x promod Server


*Install linux, in my case use Ubuntu Server 20 LTS*


apt update && apt upgrade


apt install screen


dpkg --add-architecture i386


apt update


sudo -i cd /etc/apt/sources.list.d | echo "deb http://old-releases.ubuntu.com/ubuntu/" >ia32-libs-raring.list


sudo apt install libc6:i386 libncurses5:i386 libstdc++6:i386


sudo apt install libc6 libncurses5 libstdc++6


sudo apt install steamcmd


cd /home


mkdir servers


cd servers


wget https://ia804705.us.archive.org/15/items/cod4_linux_server_files_201501/cod4_linux_server_files.zip


apt install unzip


unzip cod4_linux_server_files.zip


cd cod4


ln -s /root/.local/share/Steam/steamcmd/linux32/steamclient.so /home/servers/cod4


chmod -R 777 cod4x18_dedrun main pb mods


**copy the files "main" "runtime" "zone" and cod4x18_dedrun from cod4x_server-linux_21.2 into the same folders that whare extracted before from cod4_linux_server_files.zip**


*upload mod and unzip*


nano start.sh


#!/bin/bash
screen -dmS cod4 ./cod4x18_dedrun +set dedicated 2 +set net_port 28960 +set sv_punkbuster 1 +set fs_game mods/pml220pub +exec server.cfg +set rcon_password qwe12345678 +map_rotate


sudo chmod +x start.sh


cd /home/servers/cod4


./start.sh


*Install htop to monitor the process "Screen cod4x18..."*


**Put the server.cfg into "/home/servers/cod4/main" folder not just in cod4 folder**
