
Цей код міняємо

~~~css

.icon-header-noti::after {
  content: attr(data-notify);
  font-family: Poppins-Regular;
  font-size: 12px;
  color: #fff;
  line-height: 15px;
  text-align: center;

  display: block;
  position: absolute;
  top: -7px;
  right: 0;
  min-width: 15px;
  height: 15px;
  padding: 0 3px;
  background-color: #717fe0;
}

~~~

на цей 

~~~css

.icon-header-noti .indicator {
  font-family: Montserrat-Regular;
  font-size: 12px;
  color: #fff;
  line-height: 15px;
  text-align: center;
 display: block;
  position: absolute;
  top: -7px;
  right: 0;
  min-width: 15px;
  height: 15px;
  padding: 0 3px;
  background-color: #f7be0c;
}

~~~