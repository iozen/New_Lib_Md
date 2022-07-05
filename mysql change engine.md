ALTER TABLE osradar ENGINE = MyISAM;

Changing the storage engine by default on MariaDB / MySQL
To change the default storage engine, edit the MariaDB or MySQL configuration file. This can vary according to the versions of the operating system or the same program. In the case of Ubuntu 20.04 and MariaDB it is:

:~$ sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
And change the next line:

default-storage-engine=InnoDB
A:

default-storage-engine=MyISAM


## change engine table 

alter table category ENGINE = MyISAM;
alter table category_details ENGINE = MyISAM;
alter table img ENGINE = MyISAM;
alter table page_category_connection ENGINE = MyISAM;
alter table product ENGINE = MyISAM;
alter table product_category_connection ENGINE = MyISAM;
alter table product_details ENGINE = MyISAM;
alter table product_img_connection ENGINE = MyISAM;
