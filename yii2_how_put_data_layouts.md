
#yii2 #layout 


Є можливість передати у глобальний масив

~~~php 

Yii::$app->params['form'] = $contactFrom;

~~~

А у layout це отримати

~~~php 
`Yii::$app->params['form']
~~~
