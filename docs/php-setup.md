---
layout: default
title: PHP Development Server
published: true
parent: Linux
---

# PHP Development Server

* [Apache with PHP 8.1](#apache-with-php-81)
* [Apache with PHP 7.4](#apache-with-php-74)

## Apache with PHP 8.1

* Start the VM
* Login as super user `sudo su`

Add PHP repository:

```
apt install software-properties-common
add-apt-repository ppa:ondrej/php
apt update
```

Copy this installation sh script to `/shared/setup.sh`

```sh
#!/usr/bin/env bash

apt update
apt install vim unzip -y
apt install libapache2-mod-php8.1 php8.1
apt install mysql-client libmysqlclient-dev -y
apt install php8.1-mysql php8.1-sqlite3 -y
apt install php8.1-mbstring php8.1-curl php8.1-intl php8.1-gd php8.1-zip php8.1-bz2 -y
apt install php8.1-dom php8.1-xml php8.1-soap -y

a2enmod php8.1
a2enmod rewrite
a2enmod actions

sed -i '170,174 s/AllowOverride None/AllowOverride All/g' /etc/apache2/apache2.conf

rm -rf /var/www
mkdir /var/www
ln -s /shared/ /var/www/html

service apache2 restart

cd ~
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
php -r "unlink('composer-setup.php');"
composer self-update
```

Set execute permission:

```
chmod +x /shared/setup.sh
```

Run the setup script:

```
./shared/setup.sh
```

Add `vboxsf` to apache `www-data` group:

```
usermod -a -G vboxsf www-data
```

Add current user to vboxsf group:

```
sudo usermod -aG vboxsf $USER
```

Reboot.

## Apache with PHP 7.4

* Start the VM
* Login as super user `sudo su`
* Copy this installation sh script to `/shared/setup.sh`

```sh
#!/usr/bin/env bash

apt update
apt install vim unzip apache2 -y
apt install mysql-client libmysqlclient-dev -y
apt install libapache2-mod-php7.4 php7.4 php7.4-mysql php7.4-sqlite -y
apt install php7.4-mbstring php7.4-curl php7.4-intl php7.4-gd php7.4-zip php7.4-bz2 -y
apt install php7.4-dom php7.4-xml php7.4-soap -y

a2enmod rewrite
a2enmod actions

sed -i '170,174 s/AllowOverride None/AllowOverride All/g' /etc/apache2/apache2.conf

rm -rf /var/www
mkdir /var/www
ln -s /shared/ /var/www/html

service apache2 restart

cd ~
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
php -r "unlink('composer-setup.php');"
composer self-update
```

Set execute permission:

```
sudo chmod +x /shared/setup.sh
```

Run the setup script:

```
./shared/setup.sh
```

Add `vboxsf` to apache `www-data` group:

```
usermod -a -G vboxsf www-data
```

Add current user to vboxsf group:

```
sudo usermod -aG vboxsf $USER
```

Reboot.

## Testing

On the guest VM open `http://192.168.0.172`in your browser to the hosted website.
Change the IP address as shown in `ifconfig`

Please note: When you start the VM it will take some seconds until
apache is started. 
