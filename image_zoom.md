#js #zoom #image


[Image zoom on github](https://github.com/malaman/js-image-zoom)


~~~html



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF8">
    <title>Title</title>
    <script src="https://unpkg.com/js-image-zoom@0.7.0/js-image-zoom.js" type="application/javascript"></script>
</head>
<body>
<div id="img-container" style="width: 400px">
    <img src="https://github.com/malaman/js-image-zoom/blob/master/example/1.jpg?raw=true" />
</div>
<script>

var options1 = {
    width: 400,
    zoomWidth: 500,
    offset: {vertical: 0, horizontal: 10}
};

// If the width and height of the image are not known or to adjust the image to the container of it
var options2 = {
    fillContainer: true,
    offset: {vertical: 0, horizontal: 10}
};

new ImageZoom(document.getElementById("img-container"), options2);

</script>
</body>
</html>


~~~