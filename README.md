# linux-apps-setup

#!/bin/bash

echo ">>> Setup initialized..."

sudo apt-get update && sudo apt-get upgrade

sudo apt-get install snapd



echo ">>> Installing Snap programs..."

echo ">>> Installing IDEs and Editors..."

sudo snap install android-studio --classic

sudo snap install phpstorm --classic

sudo snap install pycharm-professional --classic

sudo snap install intellij-idea-ultimate --classic

sudo snap install webstorm --classic

sudo snap install code --classic

sudo snap install sublime-text --classic


echo ">>> Installing additional dev tools..."

sudo snap install postman

sudo snap install gitkraken

sudo snap install insomnia


echo ">>> Installing essentials..."

sudo snap install spotify

sudo snap install slack --classic

sudo snap install skype --classic

sudo snap install mailspring




echo ">>> Setting up LAMP..."

sudo apt-get install apache2

sudo apt-get install mysql-server mysql-client libmysqlclient-dev

sudo mysql_secure_installation

sudo apt install php7.0 libapache2-mod-php7.0 php7.0-mysql php7.0-curl php7.0-json php7.0-cgi

sudo apt-get install phpmyadmin

sudo systemctl restart apache2



echo ">>> Setting up Python"

sudo apt-get install python-pip

alias python="python3"

alias pip="pip3"



echo ">>> Setting up ngrok"

wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip

unzip ngrok-stable-linux-amd64.zip

rm ngrok-stable-linux-amd64.zip

# ./ngrok authtoken 3R2tTAeDJvKKR8PvTCk1E_4WMmnj4Kk91czhKyKWfhu

alias ngrok="~/./ngrok http 80"



echo ">>> Installing Tmux"

sudo apt-get install tmux



echo ">>> Setting up mosquitto..."

sudo apt-get install mosquitto

sudo apt-get install mosquitto-clients

wget https://s3-us-west-2.amazonaws.com/workswithweb/mqttbox/latest/linux/MQTTBox.deb

sudo dpkg -i MQTTBox.deb

rm MQTTBox.deb



echo ">>> Installing uGet..."

sudo apt-add-repository ppa:plushuang-tw/uget-stable

sudo apt-add-repository ppa:plushuang-tw/uget-stable

sudo apt-get install uget aria2



echo ">>> Fix Wifi..."

sudo apt install git dkms build-essential

git clone https://github.com/tomaspinho/rtl8821ce.git

cd rtl8821ce

sudo ./dkms-install.sh

mokutil --sb-state



echo ">>> To do..."
echo "1. Download and setup Opera"
echo "2. Configure MQTT password"
echo "3. Install Popcorn-Time: https://itsfoss.com/popcorn-time-ubuntu-linux/"
echo "4. Check on PhpMyAdmin installation - https://askubuntu.com/questions/387062/how-to-solve-the-phpmyadmin-not-found-issue-after-upgrading-php-and-apache"
