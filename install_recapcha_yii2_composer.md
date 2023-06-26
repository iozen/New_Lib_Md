
#yii2 #recapcha #capcha 

~~~bash

composer require --prefer-dist "himiklab/yii2-recaptcha-widget" "*"

~~~

in config file

inside **components**

~~~php 

 'reCaptcha' => [

 'name' => 'reCaptcha',

 'class' => 'himiklab\yii2\recaptcha\ReCaptcha',

  'siteKey' => 'sitekey',

 'secret' => 'secret key',

 ],



~~~

using 

~~~php 

 <?= $form->field($model, 'verifyCode')->widget(Captcha::className(), [

 'template' => '<div class="row"><div class="col-lg-3">{image}</div>
  <div class="col-lg-6">{input}</div></div>',

  ]) ?>


  <?= $form->field($model, 'reCaptcha')->widget(\himiklab\yii2\recaptcha\ReCaptcha::className()) ?>

~~~

form rules 

~~~php 


public function rules()
{
return [
// name, email, subject and body are required
[['name', 'email', 'subject', 'body','reCaptcha'], 'required'],
// email has to be a valid email address
['email', 'email'],
// verifyCode needs to be entered correctly
['reCaptcha', \himiklab\yii2\recaptcha\ReCaptchaValidator::className(), 'secret' => '6LeTXQgUAAAAALExcpzgCxWdnWjJcPDoMfK3oKGi']

];
}

~~~