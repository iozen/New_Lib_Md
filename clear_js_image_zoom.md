#js #zoom #image


~~~html
<figure class="zoom" onmousemove="zoom(event)" style="background-image: url(//res.cloudinary.com/active-bridge/image/upload/slide1.jpg)">
  <img src="//res.cloudinary.com/active-bridge/image/upload/slide1.jpg" />
</figure>

~~~

~~~css
figure.zoom {
  & img:hover {
    opacity: 0;
  }
  img {
    transition: opacity .5s;
    display: block;
    width: 100%;
  }
  background-position: 50% 50%;
  position: relative;
  width: 500px;
  overflow: hidden;
  cursor: zoom-in;
}
~~~

~~~js
function zoom(e){
  var zoomer = e.currentTarget;
  e.offsetX ? offsetX = e.offsetX : offsetX = e.touches[0].pageX
  e.offsetY ? offsetY = e.offsetY : offsetX = e.touches[0].pageX
  x = offsetX/zoomer.offsetWidth*100
  y = offsetY/zoomer.offsetHeight*100
  zoomer.style.backgroundPosition = x + '% ' + y + '%';
}
~~~

Інший спосіб: 

[link to w3schols](https://www.w3schools.com/howto/howto_js_image_zoom.asp)