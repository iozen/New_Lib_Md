
#yii2 #model #rules


~~~php 

public function rules()
    {
        return [
//        [['title', 'about'], 'required'],
//        [['name', 'email'], 'required'],
//        ['email', 'email'],
//        ['title', 'required', 'message' => 'Введіть заголовок...'],
//        ['about', 'required', 'message' => 'Введіть Наповнення... '],
            'title' => [['title'], 'string', 'max' => 60],
            'about' => [['about'], 'string'],
            'date' => [['date'], 'string', 'max' => 300],
            'time' => [['time'], 'string', 'max' => 300],
            'project_id' => [['project_id'], 'number'],
            'todo_id' => [['todo_id'], 'number'],
            'time_sec' => [['time_sec'], 'number'],

        ];

    }


[['name', 'email', 'subject', 'body'], 'string'],

~~~