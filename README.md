# APRaspberry

Este script configura un AP en la raspberry pi 3, configuración valida para Raspbian Strech Septiembre 2017

# Uso

~~~ 
$ sudo RasAP.sh Password_de_la_red Nombre_de_AP
~~~

# Script Original 

https://gist.github.com/Lewiscowles1986/fecd4de0b45b2029c390#file-rpi3-ap-setup-sh


# Compartir internet

Si quisieras compartir el internet de tu interfaz ethernet a los usuarios del WIFI debes hacer lo siguiente

~~~
$sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE  
$sudo iptables -A FORWARD -i eth0 -o wlan0 -m state --state RELATED,ESTABLISHED -j ACCEPT  
$sudo iptables -A FORWARD -i wlan0 -o eth0 -j ACCEPT 
~~~