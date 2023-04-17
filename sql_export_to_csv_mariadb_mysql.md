
#sql #mysql #mariadb 

atention!!! before you must create folder width user and group mysql

~~~sql 

select title, date, time_sec from obj where project_id = 68 
INTO OUTFILE '/var/www/html/yii2/mysite/sql/for_sql/data.csv'
FIELDS ENCLOSED BY '"'
TERMINATED BY ','
ESCAPED BY '"'
LINES TERMINATED BY '\n';

~~~