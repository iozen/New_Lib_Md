
#linux #wifi #arch_linux

To list all available commands:

~~~bash
[iwd]# help
~~~

#### Connect to a network

First, if you do not know your wireless device name, list all Wi-Fi devices:

~~~bash

[iwd]# device list
~~~

If the device or its corresponding adapter is turned off, turn it on:
~~~bash
[iwd]# device _device_ set-property Powered on

[iwd]# adapter _adapter_ set-property Powered on
~~~
Then, to initiate a scan for networks (note that this command will not output anything):
~~~bash
[iwd]# station _device_ scan
~~~
You can then list all available networks:
~~~bash
[iwd]# station _device_ get-networks
~~~
Finally, to connect to a network:
~~~bash
[iwd]# station _device_ connect _SSID_
~~~
**Note:** For automatic IP and DNS configuration via DHCP, you have to [manually enable](https://wiki.archlinux.org/title/Iwd#Enable_built-in_network_configuration) the built-in DHCP client or configure a [standalone DHCP client](https://wiki.archlinux.org/title/Network_configuration#DHCP "Network configuration").

**Tip:** The user interface supports autocomplete, by typing `station` and `Tab` `Tab`, the available devices are displayed, type the first letters of the device and `Tab` to complete. The same way, type `connect` and `Tab` `Tab` in order to have the list of available networks displayed. Then, type the first letters of the chosen network followed by `Tab` in order to complete the command.

If a passphrase is required, you will be prompted to enter it. Alternatively, you can supply it as a command line argument:

~~~bash
$ iwctl --passphrase _passphrase_ station _device_ connect _SSID_
~~~
~~~bash
[iwd]# station _device_ disconnect
~~~
#### Show device and connection information

To display the details of a WiFi device, like MAC address:
~~~bash
[iwd]# device _device_ show
~~~
To display the connection state, including the connected network of a Wi-Fi device:
~~~bash
[iwd]# station _device_ show
~~~
#### Manage known networks

To list networks you have connected to previously:
~~~bash
[iwd]# known-networks list
~~~
To forget a known network:
~~~bash
[iwd]# known-networks _SSID_ forget
~~~