#php #foreach #showsyntax #short_if


~~~php
<?php foreach ($products as $v): ?>
~~~


~~~php
<?php endforeach; ?>
~~~


~~~php
<?php if ($a == 5): ?>   A égal 5   <?php endif; ?>
~~~

У наведеному вище прикладі HTML-блок "Дорівнює 5" укладено всередині "якщо" за допомогою цього нового синтаксису. Цей HTML-код відображатиметься, лише якщо змінна $a дорівнює 5.

Цей альтернативний синтаксис також працює з «else» і «elseif». У наступному прикладі показано структуру з «if», «elseif» і «else» з використанням цього альтернативного синтаксису:

~~~php 
`<?php   if ($a == 5):       echo "a égale 5";       echo "...";   elseif ($a == 6):       echo "a égale 6";       echo "!!!";   else:       echo "a ne vaut ni 5 ni 6";   endif;   ?>`
~~~

> **Note**:
> 
> Vous ne pouvez pas utiliser différentes syntaxes dans le même bloc de contrôle.

**Увага**

Будь-яке відображення (включно з пробілами) між структурою `switch` і першим `case` спричинить синтаксичну помилку. Наприклад, це недійсно:

~~~php
`<?php switch ($foo): ?>       <?php case 1: ?>       ...   <?php endswitch ?>`
~~~

Хоча це дійсно, оскільки останній новий рядок після структури `switch` вважається частиною кінцевого тегу `?>`, тому нічого не відображається між `switch` і `case`:

~~~php
`<?php switch ($foo): ?>   <?php case 1: ?>       ...   <?php endswitch ?>`
~~~