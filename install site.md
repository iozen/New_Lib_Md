#install #site #yii2

## install site yii2 

1. [Створити базу і користувача під проєкт](obsidian://open?vault=Lib&file=create%20new%20database%20and%20user)
2. Перейти у папку із сайом 
3. git init (ініціюємо репозиторій)
4. git remote add h адреса репозиторію (Додаємо відделений репозиторій)
5. git pull h master (скачуємо зміни із віддаленого репозиторію)
6. composer install (встановлюємо пакети)
7. php init (створюємо тимчасові файли і вибераємо режим або development або production) *по замовчуванню Production*
8. [Підключаємось до бази](obsidian://open?vault=Lib&file=connect%20yii2%20advanced%20to%20db)
9. php yii migrate (запускаємо міграцію щоб додати всі данні у базу та створити структуру)
