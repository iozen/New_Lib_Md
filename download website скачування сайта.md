wget \
     --recursive \
     --no-clobber \
     --page-requisites \
     --html-extension \
     --convert-links \
     --restrict-file-names=windows \
     --domains website.org \
     --no-parent \
         www.website.org/tutorials/html/


wget --recursive --page-requisites --adjust-extension --span-hosts --convert-links --restrict-file-names=windows --domains yoursite.com --no-parent yoursite.com

wget -r -k -l 7 -p -E -nc http://site.com/

wget -m -l 10 -e robots=off -p -k -E --reject-regex "wp" --no-check-certificate -U="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.106 Safari/537.36"  site-addr.com


-m (--mirror) - Включает рекурсию (чуть ли не до бесконечного погружения) и сохраняет списки каталогов
-l (--level) - Указывает на максимальную глубину погружения рекурсии
-e (--execute) - Выполнение команды. В данном примере - исключить роботов
-p (--page-requisites) - Эта опция заставляет Wget загружать все файлы, необходимые для правильного отображения HTML-страницы
-k (--convert-links) - После окончания загрузки (скачивания) все ссылки будут преобразованы, чтобы быть пригодными для локальной работы
-E (--adjust-extension) - Если файл типа application/xhtml + xml и URL-адрес не заканчивается регуляркой '\.[Hh][Tt][Mm][Ll]?' - в названии локального файла будет дописываться .html
-U (--user-agent) - Я думаю тут объяснять особо не нужно :)
--reject-regex - Исключает скачивание файлов, в которых есть часть их значения reject-regex. Почему я это добавил? Потому что я ненавижу скачивать страницы на wordpress. Это долго, очень много файлов и я не люблю wordpress. Тапками не бросаться!

## no-check-certificate - Не производится проверка сертификата сервера с доступными центрами сертификации


## one page wget download

wget -E -H -k -K -p http://www.example.com/


