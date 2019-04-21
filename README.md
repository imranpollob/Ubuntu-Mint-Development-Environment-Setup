# MINT OS (Also works in Ubuntu) Development environment setup
## apache2 php7.2 mySql phpMyAdmin node11 composer git laravel mongodb zsh 

https://itsfoss.com/guide-install-linux-mint-16-dual-boot-windows/

### System update
sudo apt update
sudo apt upgrade

### apache2
sudo apt install apache2

sudo systemctl stop apache2.service
sudo systemctl start apache2.service
sudo systemctl enable apache2.service

### mysql
sudo apt-get install mysql-server mysql-client

sudo systemctl stop mysql.service
sudo systemctl start mysql.service
sudo systemctl enable mysql.service

**mysql password problem**
***Method 1***
sudo mysql_secure_installation
(y for everything) 
mysql -u root -p
yourPassword

***Method 2***
follow https://linuxconfig.org/how-to-reset-root-mysql-password-on-ubuntu-18-04-bionic-beaver-linux

sudo systemctl restart mysql.service

### php
sudo apt install php7.2 libapache2-mod-php php7.2-common php7.2-mbstring php7.2-xmlrpc php7.2-soap php7.2-gd php7.2-xml php7.2-mysql php7.2-cli php7.2-zip

**if "Unable to locate package" problem come**
sudo apt-add-repository ppa:ondrej/php

**switch between php versions** - https://tecadmin.net/switch-between-multiple-php-version-on-ubuntu/

### phpMyAdmin
sudo apt install phpmyadmin

An alternative- **Adminer** https://www.adminer.org/#download

### composer
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer

### node
curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
sudo apt-get install -y nodejs

### git
sudo apt install git

git config --global user.name YourName
git config --global user.username YourUsername
git config --global user.email YourEmail

**generate ssh for github -** https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

### New laravel project:
composer create-project --prefer-dist laravel/laravel blog

### mongodb
https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/#install-mongodb-community-edition-using-deb-packages

### installing oh my zsh
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
chsh -s `which zsh`
sudo shutdown -r 0
