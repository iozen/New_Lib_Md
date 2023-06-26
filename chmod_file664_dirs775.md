
~~~bash

chmod 755 $(find . -type d)
chmod 644 $(find . -type f)


find . -type d -exec chmod 755 {} \;
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