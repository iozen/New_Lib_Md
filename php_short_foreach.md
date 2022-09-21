#php #foreach #showsyntax #short_if


~~~
<?php foreach ($products as $v): ?>
~~~


~~~
<?php endforeach; ?>
~~~


`<?php if ($a == 5): ?>   A égal 5   <?php endif; ?>`

Dans l'exemple ci-dessus, le bloc HTML "A égal 5" est inclus à l'intérieur d'un `if` en utilisant cette nouvelle syntaxe. Ce code HTML ne sera affiché que si la variable $a est égale à 5.

Cette autre syntaxe fonctionne aussi avec le `else` et `elseif`. L'exemple suivant montre une structure avec un `if`, un `elseif` et un `else` utilisant cette autre syntaxe :

`<?php   if ($a == 5):       echo "a égale 5";       echo "...";   elseif ($a == 6):       echo "a égale 6";       echo "!!!";   else:       echo "a ne vaut ni 5 ni 6";   endif;   ?>`

> **Note**:
> 
> Vous ne pouvez pas utiliser différentes syntaxes dans le même bloc de contrôle.

**Avertissement**

Tout affichage (y compris d'espaces) entre une structure `switch` et le premier `case` va produire une erreur de syntaxe. Par exemple, ceci n'est pas valide :

`<?php switch ($foo): ?>       <?php case 1: ?>       ...   <?php endswitch ?>`

Alors que ceci est valide, vu que la dernière nouvelle ligne après la structure `switch` est considérée comme faisant partie de la balise de fin `?>` et donc, rien n'est affiché entre `switch` et `case` :

`<?php switch ($foo): ?>   <?php case 1: ?>       ...   <?php endswitch ?>`