En esta página se explicará cómo instalar un servidor DNS sobre UbuntuServer 16.04.1, el servidor DNS que vamos a trabajar es Bind.


* Indice
1. Información y configuración de las máquinas vírtuales.
2. Instalación y configuración del servidor DNS.

**NOTA:** Antes de la configuración del servidor DNS, debemos saber ya varias cosas que son:
* Tener ya varios equipos configurados y activos en la red (y todos ellos con una IP estática).
* Saber el nombre de dominio que vamos a poner al servidor DNS, junto con sus nombres a IP.


* 1

Se necesitará 2 máquinas virtuales una UbuntuServer 16.04.1 y otra Windows 7.

Empezamos con Windows:
1. Debemos tener el adaptador en modo puente y conectarnos con una IP estática a la red, pero poner en la opción del DNS la IP del UbuntuServer.
