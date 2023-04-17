#yii2 #telegram #php 



https://github.com/akbarjoudi/yii2-bot-telegram

Either run

```bash
composer require aki/yii2-bot-telegram "*"
```


```
php composer.phar require aki/yii2-bot-telegram "*"
```

or add

```
"aki/yii2-bot-telegram": "*"
```


## Usage

first add to config.php

~~~
<?php
'components' => [
	'telegram' => [
		'class' => 'aki\telegram\Telegram',
		'botToken' => '112488045:AAGs6CVXgaqC92pvt1u0L6Azfsdfd',
	]
]
?>
~~~

Once the extension is installed, simply use it in your code by :

~~~
<?php Yii::$app->telegram->sendMessage([
	'chat_id' => $chat_id,
	'text' => 'test',
]); ?>
~~~

send message width inline keyboard by:

~~~
<?php Yii::$app->telegram->sendMessage([
        'chat_id' => $chat_id,
        'text' => 'this is test',
        'reply_markup' => json_encode([
            'inline_keyboard'=>[
                [
                    ['text'=>"refresh",'callback_data'=> time()]
                ]
            ]
        ]),
    ]); ?>
~~~

send photo by :

~~~
<?php 
Yii::$app->telegram->sendPhoto([
	'chat_id' => $chat_id,
	'photo' => Yii::$app->getBaseUrl().'/uploads/test.jpg',
	'caption' => 'this is test'
]); ?>
~~~

## [](https://github.com/akbarjoudi/yii2-bot-telegram#usage-in-controller)Usage in controller

First of all you need to disable the enableCsrfValidation feature in the controller

The robot is currently running from your server But when we start /start run the robot from the telegram application on the mobile, the request does not reach the action inside the controller because the telegram sends the request to the POST and yii requests it without csrf Sends Bad Request (# 400). So then the code doesn't run inside your method

Consider the following example

~~~
class SiteController extends Controller
{
	public $enableCsrfValidation = false;

	public function actionIndex()
    {
        $res = Yii::$app->telegram->sendMessage([
            'chat_id' => $chat_id,
            'text' => 'hello world!!' 
        ]);
       
    }
}
~~~
##  Sample Code:

How to get user chat_id from the bot ?

> **You can use : `$telegram->input->message->chat->id` to get chat_id**

Sample widget class :

~~~

$res = Yii::$app->telegram->sendMessage([
	'chat_id' => $telegram->input->message->chat->id,
	'text' => "salam"
]);

~~~
## New feature Command

---

How to use the command
~~~
use aki\telegram\base\Command;

Command::run("/start", function($telegram){
   $result = $telegram->sendMessage([
      'chat_id' => $telegram->input->message->chat->id,
      "text" => "hello"
   ]);
});

~~~