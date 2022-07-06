## interfaces

#This file describes the network interfaces available on your system
#and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

#The loopback network interface

auto lo
iface lo inet loopback

auto enp3s0 
allow-hotplug enp3s0
iface enp3s0 inet dhcp

auto wlp4s0
iface wlp4s0 inet dhcp
wpa-ssid MikroTik-ADCE0B
wpa-psk alpachino25


## lan 

DHCP

  auto eth0
    allow-hotplug eth0
    iface eth0 inet dhcp
	
STATIC 

auto eth0
iface eth0 inet static
        address 192.168.0.7
        netmask 255.255.255.0
        gateway 192.168.0.254


## wifi

/etc/network/interfaces 

MikroTik-ADCE0B

auto wlan0
iface wlan0 inet dhcp
    wpa-ssid mynetworkname
    wpa-psk mysecretpassphrase
