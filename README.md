En esta página se explicará cómo instalar y configurar un servidor DNS sobre UbuntuServer 16.04.1, el servidor DNS que vamos a trabajar es Bind.

                 Índice ![Alt Text](url)
           
1. Información y configuración de las máquinas vírtuales.
2. Instalación y configuración del servidor DNS.

___

**NOTA:** Antes de la configuración del servidor DNS, debemos saber ya varias cosas que son:
* Tener ya varios equipos configurados y activos en la red (y todos ellos con una IP estática y nombres de la máquina).
* Saber el nombre de dominio que vamos a poner al servidor DNS, junto con la IP (también estática).

_Se ponen IPs estáticas para evitar conflictos de IP._
* Disponer de 2 servicios (subdominios, como apache2 y DNS). **??**
* Tener instalado y activo el servicio [Webmin](http://www.webmin.com/deb.html).

___

1. Información y configuración de las máquinas vírtuales.

Se necesitará 2 máquinas virtuales una UbuntuServer 16.04.1 y otra Windows 7 y deberán seguir estos pasos para su configuración

Empezamos con Windows:

   1.1.0 Debemos tener el adaptador en modo puente y conectarnos con una IP estática a la red, pero poner en la opción del DNS la IP del       UbuntuServer.
**IMAGEN**
   1.1.1 Ahora, iniciamos la máquina y configuramos la red para que sea estática y el DNS se lo aplicaremos a la IP que será la del DNS (UbuntuServer).
**IMAGEN**
   1.1.2 Aplicamos cambios y comprobamos que toda la configuración de la red que hemos hecho ahora, funcione.
**IMAGEN**

Ahora con UbuntuServer, usaremos Webmin para configurar tanto la red, como el DNS. 
   1.
   1.
   1.
   1.
  
2. 
   1. zzzz
   2. mmmm
