# Ubuntu / Mint OS development environment setup

## OS installation

Make bootable device using [Rufus](https://rufus.ie/downloads/)

### Linux only
Follow [this link](https://itsfoss.com/install-ubuntu/)

### Windows + Linux alongside

Follow [this link](https://itsfoss.com/install-ubuntu-1404-dual-boot-mode-windows-8-81-uefi/)


## Software list
- apache2
- php7.2 
- mySql
- phpMyAdmin 
- node11 
- composer 
- git 
- mongodb 
- zsh 


### System update
```bash
sudo apt update
sudo apt upgrade
```

### apache2
```bash
sudo apt install apache2
sudo systemctl stop apache2.service
sudo systemctl start apache2.service
sudo systemctl enable apache2.service
```

### mysql
```bash
sudo apt install mysql-server mysql-client
sudo systemctl stop mysql.service
sudo systemctl start mysql.service
sudo systemctl enable mysql.service
```

**Fixing MySQL password problem**

***Method 1***
```bash
sudo mysql_secure_installation
```
Enter y for everything
```bash
mysql -u root -p
yourPassword
```

***Method 2***

Follow [this link](https://linuxconfig.org/how-to-reset-root-mysql-password-on-ubuntu-18-04-bionic-beaver-linux)

To restart MySQL
```bash
sudo systemctl restart mysql.service
```

### php
```bash
sudo apt install php7.2 libapache2-mod-php php7.2-common php7.2-mbstring php7.2-xmlrpc php7.2-soap php7.2-gd php7.2-xml php7.2-mysql php7.2-cli php7.2-zip
```

**If "Unable to locate package" problem come**
```bash
sudo apt-add-repository ppa:ondrej/php
```

**Switch between php versions**  

Follow [this link](https://tecadmin.net/switch-between-multiple-php-version-on-ubuntu/)

### phpMyAdmin
```bash
sudo apt install phpmyadmin
```
An alternative: [Adminer](https://www.adminer.org/#download)

### Composer
```bash
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```

### Node
```
curl -sL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Git
```bash
sudo apt install git
git config --global user.name YourName
git config --global user.username YourUsername
git config --global user.email YourEmail
```

**Generate ssh for github**

Follow [this link](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)


### MongoDB
Follow [this link](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/#install-mongodb-community-edition-using-deb-packages)

### oh my zsh
```bash
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
#chsh -s `which zsh`
```

sudo shutdown -r 0
