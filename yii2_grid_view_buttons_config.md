
#yii2 #gridview #buttons

how to configurate buttons 

~~~php 
 'template' => '{view} {delete}',

~~~

all code: 

~~~php 

<?= GridView::widget([
    'dataProvider' => $dataProvider,
    'columns' => [
        ['class' => 'yii\grid\SerialColumn'],
        .
        .
        .
        .
        [
         'class' => 'yii\grid\ActionColumn',
        'template' => '{view} {delete}',
       ],
]); ?>

~~~