#install #composer

## install composer debian11


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