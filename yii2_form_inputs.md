
#yii2 #inputs #form 

Validation message

~~~php 

public function rules() { 

return [ ['username', 'required', 'message' => 'Please choose a username.'], ]; 

}
~~~