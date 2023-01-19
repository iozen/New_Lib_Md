
#yii2 #userdata

How can I get the name of the logged-in-user in yii2? I can get the user-id with

```php
Yii::$app->user->id;
```

and I know that I could find the name in the database but I want a direct way. The name-column in the database has the name "username", but

```php
Yii::$app->user->username;
```

doesn't work and

```php
Yii::$app->user->name;  
```