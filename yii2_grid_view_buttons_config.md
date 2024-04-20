
#yii2 #gridview #buttons

how to configurate buttons 

~~~php 
 'template' => '{view} {delete}',

~~~

all code: 

```php 
<?= GridView::widget([
    'dataProvider' => $dataProvider,
    'columns' => [
        // Other columns...
        [
            'class' => 'yii\grid\ActionColumn',
            'template' => '{view} {update} {delete} {custom}', // Define template including your custom button
            'buttons' => [
                'custom' => function ($url, $model, $key) use ($event_id)
{
                    return Html::a('<span class="glyphicon glyphicon-flag"></span>', ['controller/action', 'id' => $model->id, 'event_id'=>$event_id], [
                        'title' => Yii::t('yii', 'Custom Action'),
                        // Add any other HTML options for your button
                    ]);
                },
            ],
        ],
    ],
]); 
?>
```

