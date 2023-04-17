
#linux #imaginemagick #imagemagick #terminal #images #convertion

^ Зберегти пропорції картинки 
-gravity center Зробити по центру центрування

~~~bash 
convert input_image.jpg -resize 800x600^ -gravity center output_image.jpg
~~~

~~~bash
convert input_image.jpg -resize 300x300^ -gravity center -extent 300x300 output_image.jpg
~~~