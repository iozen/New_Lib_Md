
#yii2 #migration 

```php

//add column 

$this->addColumn('{{%sponsor}}', 'message', $this->getDb()->getSchema()->createColumnSchemaBuilder('longtext'));


//create 

'bodytext' => $this->getDb()->getSchema()->createColumnSchemaBuilder('longtext');

				 
```