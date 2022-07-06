#install #setup #domain #nginx

## Настройка домена nginx

1. створити і відкрити файл який називається так як домен
	~~~
	cd /etc/nginx/sites-available/
	touch mydomain.com.ua
	vim mydomain.com.ua
	~~~

2. створити на основі коду конфіги для фронтенд частини і бекенд
у поле server_name підставляємо назву домена
у поле root прописуємо шлях до сайта як у прикладі 
frontend: 
 ~~~
	    server {
        charset utf-8;
        client_max_body_size 128M;

        listen 80; ## listen for ipv4
        #listen [::]:80 default_server ipv6only=on; ## listen for ipv6

        server_name frontend.test;
        root        /path/to/yii-application/frontend/web/;
        index       index.php;

        location / {
            try_files $uri $uri/ /index.php$is_args$args;
        }

        location ~ ^/assets/.*\.php$ {
            deny all;
        }

        location ~ \.php$ {
                include snippets/fastcgi-php.conf;
                fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
        }
    
        location ~* /\. {
            deny all;
        }
    }
~~~

у поле server_name підставляємо panel. назву домена 
у поле root прописуємо шлях до сайта як у прикладі 
backend:
 ~~~
    server {
        charset utf-8;
        client_max_body_size 128M;
    
        listen 80; ## listen for ipv4
        #listen [::]:80 default_server ipv6only=on; ## listen for ipv6
    
        server_name backend.test;
        root        /path/to/yii-application/backend/web/;
        index       index.php;
    
        location / {
            try_files $uri $uri/ /index.php$is_args$args;
        }
    

        location ~ ^/assets/.*\.php$ {
            deny all;
        }

        location ~ \.php$ {
                include snippets/fastcgi-php.conf;
                fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
        }
    
        location ~* /\. {
            deny all;
        }
    }

~~~
3. створити посилання на ці конфіги у папці /etc/nginx/sites-enabled/
за допомогою команди
~~~
ln -s /etc/nginx/sites-available/mydomain.com /etc/nginx/sites-enabled/
~~~
4. перезапустити nginx
~~~
systemctl reload nginx
~~~
