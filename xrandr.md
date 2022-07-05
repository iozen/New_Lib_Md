xrandr --output HDMI-1 --mode 1280x1024 --pos 0x0 --auto \\
--output DVI-D-1 --mode 1920x1080 --pos 1280x0 --auto --right-of HDMI-1 \\
--output DVI-I-1 --mode 1360x768 --pos 3200x0 --auto --right-of DVI-D-1 \\

xrandr --fb 5760x1080 --output DVI-D-1 --primary --auto --panning 1920x1080+0+0 --output HDMI-1 --mode 1280x1024 --panning 1920x1080+1920+0 --output DVI-I-1 --mode 1440x900 --panning 1920x1080+3840+0


split monitors
xrandr --setmonitor VIRTUAL-LEFT 2560/0x1440/1+0+0 DP-1
xrandr --setmonitor VIRTUAL-RIGHT 2560/1x1440/1+2560+0 none

xrandr --setmonitor VIRTUAL-LEFT 800/0x1440/1+0+0 DP-1
xrandr --setmonitor VIRTUAL-MIDDLE 2000/0x1440/1+800+0 DP-1
xrandr --setmonitor VIRTUAL-RIGHT 640/1x1440/1+2800+0 none