
~~~sql 
CREATE TABLE `category` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `link` varchar(300) DEFAULT NULL,
  `parent_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb4;
/*!40101 SET character_set_client = @saved_cs_client */;

CREATE TABLE employees ( 
id INT PRIMARY KEY AUTO_INCREMENT, 
name VARCHAR(50), 
age INT, 
department VARCHAR(50) 
);


CREATE TABLE example_table ( 
id INT PRIMARY KEY AUTO_INCREMENT, 
name VARCHAR(50), 
age INT, 
salary DECIMAL(10, 2), 
is_active BOOLEAN, 
hire_date DATE, 
created_at DATETIME, 
profile_image BLOB, 
description TEXT, 
height FLOAT, 
weight DOUBLE );


