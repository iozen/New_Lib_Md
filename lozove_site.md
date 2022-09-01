#lozove #site #commands

1. Перевірити чи той проєкт  
2. Перевірити чи та дата  
3. Зверни увагу чи у тебе авто кавички  
4. Зверни увагу на тих де 1 000 грн  
  
 ~~~
g/\d\d \d\d\d./d  
g/.*, \d\d/d  
g/^\d\.\d\d$/d  
  
g/\d\d:\d\d/norm I$temp = array('time' => '  
g/time/norm f';;;xx  
g/time/norm A',  
  
g/.*\.\d\d/norm I'price' => '  
g/price/norm f';;x  
g/price/norm A'); array_push($data, $temp);  
  
%s/Від//g  
  
g/^ \{1}[А-Яа-яєіІїІЄ\-A-Za-z ]*/norm I'fio' => "  
g/fio/norm f"x  
g/fio/norm A",  
g/fio/norm $x  
  
g/Зарахування переказу/norm I'fio' => "  
g/Зарахування переказу/norm f"x  
g/Зарахування переказу/norm A",  
g/Зарахування переказу/norm $x  
  
%s/Зарахування переказу/відправник невідомий/g  
  
  
g/fio/s/тут символ таба//g
~~~