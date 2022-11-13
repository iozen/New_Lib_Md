~~~
catalog/controller/startup/startup.php
```
system/modification/controller/startup/startup.php
```
~~~
added code 
~~~
if(empty($_GET)){
$this->session->data['language'] = 'uk-ua';                                                                                                             
}
~~~

додав у таблицю oc_url_alias                                                                                                                                                                                 

![[Pasted image 20220726111740.png]]



catalog/controller/common/language.php

~~~

   public function getLangPrefix ($lng_code) {                                                                                                            
        $ret='';                                                                                                                                           
         $lng_code == self::$code_ua ? $ret = "ua/" : null;                                                                                                 
        $lng_code == self::$code_en ? $ret = "en/" : null;                                                                                               
                                                                                                                                                           
       if($_GET['_route_'] == 'ua/'){                                                                                                                     
           $lng_code == self::$code_ru ? $ret = "ru/" : null;                                                                                                      }                                                                                                                                                  
       if($_GET['_route_'] != 'ua/'){                                                                                                                     
            $lng_code == self::$code_ru ? $ret = "" : null;                                                                                                
        }                                                                                                                                                  
 //  var_dump($this->request->get['route']);                                                                                                    return $ret;                                                                                                                                       
     }


~~~


catalog/controller/startup/seo_pro.php
system/storage/modification/catalog/controller/startup/seo_pro.php


~~~
 public function index() {                                                                                                                           
       // Add rewrite to url class
       if ($this->config->get('config_seo_url')) {

       if($_GET['_route_'] == 'ua/' || $_GET['_route_'] == 'ua/ru/'){
               unset($this->cache_data['queries']['common/home']);
               $this->cache_data['queries']['common/home'] = '';
       }

           $this->url->addRewrite($this);
       } else {
           return;
       } 
~~~
