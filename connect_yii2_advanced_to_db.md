## підключенння до бази yii2 advanced

1. відкриваємо файл common/config/main-local.php
2. там робимо зміни 

dbname=назва бази
'username' => 'a',
'password' => 'io25',

        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=localhost;dbname=somename',
            'username' => 'someuser',
            'password' => 'somepass',
            'charset' => 'utf8',
        ],
 
 