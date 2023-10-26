# Ubuntu / Mint OS development environment setup

## OS installation

Make bootable device using [Rufus](https://rufus.ie/downloads/)

### Linux only
Follow [this link](https://itsfoss.com/install-ubuntu/)

### Windows + Linux alongside

Follow [this link](https://itsfoss.com/install-ubuntu-1404-dual-boot-mode-windows-8-81-uefi/)


## List of contents
Perfom system update everytime before a software installation to avoid most of the errors
- [System update](#system-update)
- [Git](#git)
- [Node](#node)
- [Python](#python)
- [apache2](#apache2)
- [mySql](#mysql)
- [PHP](#php)
- [phpMyAdmin](#phpmyadmin)
- [Composer](#composer) 
- [MongoDB](#mongodb) 
- [Zsh](#zsh)
- [Useful commands](#useful-commands)


### System update
```bash
sudo apt update
sudo apt upgrade
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

### Node
If you want to install Node version manager then install [nvm](https://github.com/nvm-sh/nvm#install--update-script)
```bash
nvm install --lts
nvm use --lts
```

Installing standalone Node 20
```
curl -sL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Python
If you want to install Python version manager then install [pyenv](https://github.com/pyenv/pyenv#automatic-installer) and [setup shell environment](https://github.com/pyenv/pyenv#set-up-your-shell-environment-for-pyenv) and [build environment](https://github.com/pyenv/pyenv/wiki#suggested-build-environment)
```bash
pyenv install --list
pyenv global PYTHON_VERSION
```

Standalone Python installation and make latest version: [the link](https://www.debugpoint.com/install-python-3-12-ubuntu/) 

### apache2
```bash
sudo apt install apache2
sudo systemctl stop apache2.service
sudo systemctl start apache2.service
sudo systemctl enable apache2.service
```

### MySQL
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

### PHP
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

### MongoDB
Follow [this link](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/#install-mongodb-community-edition-using-deb-packages)

### Zsh
```bash
sudo apt install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# If shell is not changed to zsh, try the command below and restart
chsh -s `which zsh`
```
zsh plugins:
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md)
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)
- [powerlevel10k](https://github.com/romkatv/powerlevel10k#installation)

Other tools:
- [bat](https://github.com/sharkdp/bat#installation)
- [fzf](https://github.com/junegunn/fzf#installation)

## Useful commands
```bash
# Reboot immediately
sudo shutdown -r 0
# load bash
source ~/.bashrc
# load zsh
source ~/.zshrc
# switch to bash
exec bash
# switch to zsh
exec zsh
```
