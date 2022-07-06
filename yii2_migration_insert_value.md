#yii2 #migration #insert

## insert value migration 


```php
public function up() {
    $this->execute('
        CREATE TABLE IF NOT EXISTS `ad_court` (
        `id` int(11) NOT NULL AUTO_INCREMENT,
        `name` varchar(255) NOT NULL,
        PRIMARY KEY (`id`)
    ) ENGINE=InnoDB  DEFAULT CHARSET=utf8 AUTO_INCREMENT=18 ;');

    $this->insert('ad_court',array(
        'name' =>'Хўжалик суди',
    ));
    $this->insert('ad_court',array(
        'name' =>'Фуқаролик суди',
    ));
}
```