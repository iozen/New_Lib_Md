#install #server #debian11

## початок встановлення
```
sudo apt update
```

## встановлення nginx + php
[Install nginx php](install_nginx_php_debian_11.md)

## встановлення mariadb
[Mariadb install debian11](install_mariadb_debian11.md)
## встановлення composer 
 
 [install composer debian 11](install_composer_debain_11.md)

## встановлення  git 
```
sudo apt install git 
```

## встановлення vim mc ranger certbot
```
sudo apt install vim mc ranger 
```

[install Certbot debian 11](install_certbot.md)


## встановлення сайту
[install yii2 site](install_site.md)

## перевірка стану проєкту

сайт має відкриватись за адресою: 

```
ip name-of-site/frontend/web/

наприклад: 
0.0.0.0/site/frontend/web/
```

## налаштуваня домена 

[налаштування домена](install_setup_domain_nginx.md)



## Команди
~~~

sudo apt update
sudo apt install nginx php php-fpm php-curl php-mysql 
sudo systemctl enable nginx
sudo systemctl start nginx
journalctl -xe
systemctl status apache2
systemctl stop apache
systemctl stop apache2
apt remove apache2
sudo systemctl start nginx
systemctl start nginx
systemctl status nginx
systemctl enable php7.4-fpm 
systemctl start php7.4-fpm
systemctl status php7.4-fpm
vim  /etc/php/7.4/fpm/php.ini
systemctl restart php7.4-fpm
systemctl restart nginx
systemctl reload nginx
cd /var/www/html
> test.php
vim test.php 
apt install mariadb-server mariadb-client 
systemctl enable mariadb
systemctl start mariadb
systemctl status mariadb
cd
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" 
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
chmod +x /usr/local/bin/composer
composer --version
composer self-update
sudo apt install git 
sudo apt install vim mc ranger 
sudo apt install certbot python3-certbot-nginx
mysql -u root

~~~