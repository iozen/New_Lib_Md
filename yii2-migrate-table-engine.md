#yii2 #tableengine #mysql #engine

Як при створені таблиці змінити рушій

~~~php 
public function safeUp() { 

	$tableOptions = 'CHARACTER SET utf8 COLLATE utf8_unicode_ci ENGINE=InnoDB'; 
	
		$this->createTable('news', [ 
			'id' => $this->primaryKey(), 
			'title' => $this->string()->notNull(),
			'content' => $this->text(), ], 
	$tableOptions
	); 
}
~~~


~~~php 
$tableOptions = 'CHARACTER SET utf8 COLLATE utf8_unicode_ci ENGINE=InnoDB';
~~~