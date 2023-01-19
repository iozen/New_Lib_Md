
#yii2 #baseurl

~~~php 

use yii\helpers\Url;

Url::base();         // /myapp
Url::base(true);     // http(s)://example.com/myapp - depending on current schema
Url::base('https');  // https://example.com/myapp
Url::base('http');   // http://example.com/myapp
Url::base('');       // //example.com/myapp



Yii::getAlias('@web');

You can also always rely on one of these two:

Yii::$app->homeUrl;

Url::base();


Yii::$app->homeUrl

Yii::$app->getUrlManager()->getBaseUrl();


Yii::$app->request->baseUrl




~~~