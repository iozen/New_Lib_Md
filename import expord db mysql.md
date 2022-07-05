    mysqldump -u username -p database_name > data-dump.sql

    mysql -u username -p new_database < data-dump.sql
