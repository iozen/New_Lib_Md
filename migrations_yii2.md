#yii2 #migrations

```php 

public function up()
{
    $this->dropColumn('post', 'position');

    $this->renameColumn('post', 'owner_id', 'user_id');

    $this->alterColumn('post', 'updated', $this->timestamp()->notNull()->defaultValue('0000-00-00 00:00:00'));
}
```

~~~php 

$this->addColumn('{{%mods}}', 'img', $this->string(600));

~~~

