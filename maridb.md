mysql -u //user_name// -p -h //ip_address// //db_name//

MariaDB [test]> 

----------------------------------------------------------------------------------
CREATE DATABASE IF NOT EXISTS test;

----------------------------------------------------------------------------------
USE test;

----------------------------------------------------------------------------------
CREATE TABLE IF NOT EXISTS books (
  BookID INT NOT NULL PRIMARY KEY AUTO_INCREMENT, 
  Title VARCHAR(100) NOT NULL, 
  SeriesID INT, AuthorID INT);
  
----------------------------------------------------------------------------------
CREATE TABLE IF NOT EXISTS authors 
(id INT NOT NULL PRIMARY KEY AUTO_INCREMENT);

----------------------------------------------------------------------------------
CREATE TABLE IF NOT EXISTS series 
(id INT NOT NULL PRIMARY KEY AUTO_INCREMENT);

----------------------------------------------------------------------------------
INSERT INTO books (Title,SeriesID,AuthorID) 
VALUES('The Fellowship of the Ring',1,1), 
      ('The Two Towers',1,1), ('The Return of the King',1,1),  
      ('The Sum of All Men',2,2), ('Brotherhood of the Wolf',2,2), 
      ('Wizardborn',2,2), ('The Hobbbit',0,1);

----------------------------------------------------------------------------------
SHOW TABLES;
+----------------+
| Tables_in_test |
+----------------+
| authors        |
| books          |
| series         |
+----------------+
3 rows in set (0.00 sec)

----------------------------------------------------------------------------------
DESCRIBE books;
+----------+--------------+------+-----+---------+----------------+
| Field    | Type         | Null | Key | Default | Extra          |
+----------+--------------+------+-----+---------+----------------+
| BookID   | int(11)      | NO   | PRI | NULL    | auto_increment |
| Title    | varchar(100) | NO   |     | NULL    |                |
| SeriesID | int(11)      | YES  |     | NULL    |                |
| AuthorID | int(11)      | YES  |     | NULL    |                |
+----------+--------------+------+-----+---------+----------------+

----------------------------------------------------------------------------------
SELECT * FROM books;
+--------+----------------------------+----------+----------+
| BookID | Title                      | SeriesID | AuthorID |
+--------+----------------------------+----------+----------+
|      1 | The Fellowship of the Ring |        1 |        1 |
|      2 | The Two Towers             |        1 |        1 |
|      3 | The Return of the King     |        1 |        1 |
|      4 | The Sum of All Men         |        2 |        2 |
|      5 | Brotherhood of the Wolf    |        2 |        2 |
|      6 | Wizardborn                 |        2 |        2 |
|      7 | The Hobbbit                |        0 |        1 |
+--------+----------------------------+----------+----------+
7 rows in set (0.00 sec)

----------------------------------------------------------------------------------
INSERT INTO books (Title, SeriesID, AuthorID)
VALUES ("Lair of Bones", 2, 2);

Query OK, 1 row affected (0.00 sec)

----------------------------------------------------------------------------------
SELECT * FROM books;

----------------------------------------------------------------------------------
UPDATE books 
SET Title = "The Hobbit" 
WHERE BookID = 7;

----------------------------------------------------------------------------------
rename table 

rename table category_data to category_details;

----------------------------------------------------------------------------------
type of chars 

char [ (length) ] [ character set charset_name ] [ collate collation_name ]
varchar [ (length) ] [ character set charset_name ] [ collate collation_name ]
binary [ (length) ]
varbinary (length)
date
time
timestamp
datetime
year
tinyint [ (length) ] [ unsigned ] [ zerofill ]
smallint [ (length) ] [ unsigned ] [ zerofill ]
mediumint [ (length) ] [ unsigned ] [ zerofill ]
int [ (length) ] [ unsigned ] [ zerofill ]
integer [ (length) ] [ unsigned ] [ zerofill ]
bigint [ (length) ] [ unsigned ] [ zerofill ]
real [ (length, decimals) ] [ unsigned ] [ zerofill ]
double [ (length, decimals) ] [ unsigned ] [ zerofill ]
float [ (length, decimals) ] [ unsigned ] [ zerofill ]
decimal [ (length, [ decimals ]) ] [ unsigned ] [ zerofill ]
numeric [ (length, [ decimals ]) ] [ unsigned ] [ zerofill ]
tinyblob
blob
mediumblob
longblob
tinytext [ binary ] [ character set charset_name ] [ collate collation_name ]
text [ binary ] [ character set charset_name ] [ collate collation_name ]
mediumtext [ binary ] [ character set charset_name ] [ collate collation_name ]
longtext [ binary ] [ character set charset_name ] [ collate collation_name ]
enum(value1, value2, ...) [ character set charset_name ] [ collate collation_name ]
