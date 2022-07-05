#install #server #debian11

## start installation 
```
sudo apt update
```

## install nginx + php
```
sudo apt install nginx php php-fpm php-curl php-mysql 
```

```
sudo apt install phpunit  php-cli unzip php-zip
```

```
sudo systemctl enable nginx
sudo systemctl start nginx
sudo systemctl status nginx

sudo systemctl enable php7.4-fpm 
sudo systemctl start php7.4-fpm 
sudo systemctl status php7.4-fpm
```
Або 
```
sudo systemctl enable php-fpm 
sudo systemctl start php-fpm 
sudo systemctl status php-fpm

```

## install mariadb
```
sudo apt install mariadb-server mariadb-client 
```
Або
```
sudo apt install mariadb
```

```
sudo mysql_secure_installation
```

```
sudo systemctl enable mariadb
sudo systemctl start mariadb
sudo systemctl status mariadb
```

## install composer 
 
  ```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" 
   ```

A `composer-setup.php` file will be created in current directory. Now execute this PHP script to install the composer at the desired location. Use `--install-dir` to set the binary location and `--filename` to set the binary name. You can install composer globally accessible for all users and projects or install locally for a specific project.

-   To install composer globally, type:
    
    ```
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer
    ```
	
	```
    chmod +x /usr/local/bin/composer
    ```

```
composer --version
```

```
composer self-update
```

