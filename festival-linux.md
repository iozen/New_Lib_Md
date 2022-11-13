#linux #texttospeach #terminal 

Утиліта для читання тексту голосом в терміналі linux

~~~
sudo apt-get install festival festvox-ru 
~~~

~~~
echo "ты кто такой? давай до свидания!" | festival --tts --language russian
~~~

~~~
text2wave -o вывод_wav -eval '(voice_msu_ru_nsh_clunits)' text.txt
~~~



