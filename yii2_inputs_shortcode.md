
#yii2 #input #active_form 

~~~php 


<?= $form->field($model, 'description')->textarea(['rows' => '10']) ?>


<?= $form->field($model, 'password')->passwordInput() ?>

<?= $form->field($model, 'username')->textInput()->hint('Please enter your name')->label('Name') ?>

<?= $form->field($model, 'email')->input('email') ?>

<?= $form->field($model, 'email')->input('time') ?>

<?= $form->field($model, 'email')->input('color') ?>

<?= $form->field($model, 'color')->input('color', ['value'=>$productDetails->color]) ?>

echo $form->field($model, 'uploadFile[]')->fileInput(['multiple'=>'multiple']);



<?= $form->field($model, 'rememberMe')->checkbox();


// allow multiple items to be checked:
echo $form->field($model, 'items[]')->checkboxList(['a' => 'Item A', 'b' => 'Item B', 'c' => 'Item C']);



echo $form->field($model, 'category')->dropdownList([
1 => 'item 1',
 2 => 'item 2' 
 ], 
['prompt'=>'Select Category'] 
);

echo $form->field($model, 'category')->radioList([
1 => 'radio 1', 
2 => 'radio 2' 
]);

echo $form->field($model, 'category')->checkboxList([ 
1 => 'checkbox 1',
2 => 'checkbox 2' 
]);

~~~