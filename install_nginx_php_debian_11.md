#install #nginx

## install nginx php debian11

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

sudo systemctl restart php8.1-fpm.service

```

## включити потрібні модулі 

1. відкрити конфіг php-fpm   cd /etc/php/7.4/fpm/
2. віккрити конфіг vim php.ini 
3. знайти там потрібні модулі
4. розкоментити

~~~
extension=mbstring
extension=mysqli
extension=pdo_mysql
~~~

5. sudo systemctl restart (або reload) php7.4-fpm перезапустити сервіс php fpm
6. sudo systemctl restart (або reload) nginx перезапустити сервіс nginx


## відкорфігурувати ngixn default конфіг

1. 	Відкрити стандартний конфіг 

   ~~~
	vim /etc/nginx/sites-available/default
   ~~~
2. В цю строку додати index.php після слова  index вона зазвичай 44
~~~
  index index.html index.htm index.nginx-debian.html;
~~~

3. Розкоментувати підключенння php-fpm 
~~~
	#location ~ \.php$ {
	#	include snippets/fastcgi-php.conf;
	#	With php-fpm (or other unix sockets):
  	#	fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
	#	With php-cgi (or other tcp sockets):
	#	fastcgi_pass 127.0.0.1:9000;
	#}

~~~
потрібно розкоментувати 

include snippets/fastcgi-php.conf;
fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;

також location і звротню кавичку щоб було так:

~~~
location ~ \.php$ {
    include snippets/fastcgi-php.conf;
	     #	 With php-fpm (or other unix sockets):
    fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
      	#	 With php-cgi (or other tcp sockets):
      	#	fastcgi_pass 127.0.0.1:9000;
}
~~~~

4. перезапустити nginx 
```
sudo systemctl reload nginx
```







