
~~~bash
find . -type d -exec chmod 775 {} \;
~~~

For files only do this.  

Code:
~~~bash
find . -type f -exec chmod 664 {} \;
~~~~

~~~bash 
find _directory_ -type d -exec chmod 755 {} +
~~~

To _chmod_ only files to 644:

~~~bash
$ find _directory_ -type f -exec chmod 644 {} +
~~~