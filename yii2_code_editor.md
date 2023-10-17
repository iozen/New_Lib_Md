
#yii2 #code_editor

~~~bash 
composer require conquer/codemirror "*"
~~~

in field

~~~php 



$form->field($model, 'code')->widget(
    CodemirrorWidget::className(),
    [
        'preset'=>'php',
        'options'=>['rows' => 20],
    ]
);

~~~
