
#yii2 #install #ckeditor #elfinder #redacror


## install ckeditor

```bash
for me

composer require --prefer-dist mihaildev/yii2-ckeditor "*"
```

```bash
php composer.phar require --prefer-dist mihaildev/yii2-ckeditor "*"
```

## install elfinder

```bash
for me 

composer require --prefer-dist mihaildev/yii2-elfinder "*"
```

```bash

php composer.phar require --prefer-dist mihaildev/yii2-elfinder "*"
```

## install redactor 

```bash
for me 

composer require --prefer-dist yiidoc/yii2-redactor "*"
```

```bash
php composer.phar require --prefer-dist yiidoc/yii2-redactor "*"
```


## configuration 

config/main.php

~~~php 

<?php
$params = array_merge(
    require __DIR__ . '/../../common/config/params.php',
    require __DIR__ . '/../../common/config/params-local.php',
    require __DIR__ . '/params.php',
    require __DIR__ . '/params-local.php'
);

return [
    'id' => 'app-backend',
    'name' => 'База Лозове',
    'basePath' => dirname(__DIR__),
    'controllerNamespace' => 'backend\controllers',
    'bootstrap' => ['log'],
//  here
	'modules' => [
		'redactor' => 'yii\redactor\RedactorModule',
		'class' => 'yii\redactor\RedactorModule',
          'uploadDir' => '@frontend/web/uploads',
          'uploadUrl' => 'https://lozove.holotiuk.pp.ua/uploads',
	],
// here end
    'components' => [
        'request' => [
            'csrfParam' => '_csrf-backend',
        ],
        'user' => [
            'identityClass' => 'common\models\User',
            'enableAutoLogin' => true,
            'identityCookie' => ['name' => '_identity-backend', 'httpOnly' => true],
        ],
        'session' => [
            // this is the name of the session cookie used for login on the backend
            'name' => 'advanced-backend',
        ],
        'log' => [
            'traceLevel' => YII_DEBUG ? 3 : 0,
            'targets' => [
                [
                    'class' => 'yii\log\FileTarget',
                    'levels' => ['error', 'warning'],
                ],
            ],
        ],
        'errorHandler' => [
            'errorAction' => 'site/error',
        ],
        /*
        'urlManager' => [
            'enablePrettyUrl' => true,
            'showScriptName' => false,
            'rules' => [
            ],
        ],
        */
    ],
    // here 
'controllerMap' => [
        'elfinder' => [
			'class' => 'mihaildev\elfinder\PathController',
			'access' => ['@'],
			'root' => [
				'baseUrl'=>'https://lozove.holotiuk.pp.ua',
                    'basePath'=>'@frontend/web/',
				'path' => 'uploads',
				'name' => 'Files'
			],
	/*		'watermark' => [
						'source'         => __DIR__.'/logo.png', // Path to Water mark image
						 'marginRight'    => 5,          // Margin right pixel
						 'marginBottom'   => 5,          // Margin bottom pixel
						 'quality'        => 95,         // JPEG image save quality
						 'transparency'   => 70,         // Water mark image transparency ( other than PNG )
						 'targetType'     => IMG_GIF|IMG_JPG|IMG_PNG|IMG_WBMP, // Target image formats ( bit-field )
						 'targetMinPixel' => 200         // Target image minimum pixel size
	]*/
		]
    ],

// here end
    'params' => $params,
];



~~~