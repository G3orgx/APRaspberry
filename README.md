# APRaspberry

Este script configura un AP en la raspberry pi 3, configuración valida para Raspbian Strech Septiembre 2017

# Uso

~~~ 
$ sudo RasAP.sh Password_de_la_red Nombre_de_AP
~~~

# Script Original 

https://gist.github.com/Lewiscowles1986/fecd4de0b45b2029c390#file-rpi3-ap-setup-sh



# Una vez instalado el script

Una vez que reinicias la interfaz eth0 pierde sus propiedades por lo que hay que cofigurarla nuevamente

~~~
$sudo nano /etc/network/interfaces
~~~

Agregamos la siguiente configuración debajo de la configuración de wlan0

~~~
auto eth0
iface eth0 inet dhcp
~~~

Ahora reiniciamos el servicio de red

~~~
$sudo /etc/init.d/networking restart
~~~

Perderemos la interfaz wifi para recuperarla hacemos

~~~
$sudo ifconfig wlan0 up
~~~

y por ultimo reiniciamos 

~~~
$sudo reboot
~~~