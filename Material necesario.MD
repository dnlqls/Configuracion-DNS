En esta página se explicará qué materiales usaremos y sus respectivas configuraciones.

## ÍNDICE

[1. Información y configuración de la(s) máquina(s) virtual(es).](Material necesario.MD)

[2. Instalación del servidor DNS usando Webmin.](Instalación y comprobación.MD)

[3. Configuración del DNS con Webmin.](README.md)

[4. Comprobación de los errores sintácticos de la configuración del DNS empleando Webmin.](README.md)


# 1. INFORMACIÓN Y CONFIGURACIÓN DE LA(S) MÁQUINA(S) VIRTUAL(ES).

Se necesitará 1 máquina virtual de UbuntuServer 16.04.1 y el sistema operativo anfitrión (u otra máquina virtual si no podemos cambiar la configuración de la red en la anfitrión, en mi caso usaré UbuntuServer 16.04.1 y mi equipo físico Windows 8.1).

 1.1.- Empezamos con la anfitrión (Windows 8.1):

   1.1.1- En la configuración de red, pondremos IP estática, gateway, etc. pero en el ServerDNS introduciremos la IP del UbuntuServer y en el alternativo un servidor DNS real, para traducir las direcciones ajenas de la red local.
 
 
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/Red W8.1.PNG)
   
   1.1.2- Aplicamos cambios y comprobamos que toda la configuración de la red que hemos hecho ahora, funcione.
   
   
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/Red 2.PNG)

*1.2.- Ahora con UbuntuServer, usaremos Webmin para configurar tanto la red, como el DNS.* 

__NOTA: EN CADA PASO, SE PINCHARÁ SOBRE "Salvar" o similares, no se puso en los pasos por obviedad.__

   1.2.1- Primero escogeremos el menú "Redes" y luego en el submenú "configuración de la red" del Webmin.
   
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/1 MENÚ.PNG)
  
  1.2.2- Después, seleccionaremos la opción de "Interfaces de red".
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/2 escoger submenú.PNG)
  
   1.2.3- Ahora, seleccionaremos la interfaz de la red  que vamos a configurar (en mi caso, enp0s3).
   
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/3 escoger Interfaz.PNG)
  
  1.2.4- Luego, configuraremos la interfaz con una IP estática y máscara de red.
 
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/4 Configurar interfaz.PNG)
  
  1.2.5- El siguiente paso, es partiendo desde el submenú "configuración de la red" vamos a entrar en el apartado "Enrutamiento y puertas de enlace".
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/GW MENU.PNG)
  
  1.2.6- Posteriormente, ingresaremos la IP del gateway, en mi caso 192.168.1.1
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/6 GateWay.PNG)
  
  1.2.7- A continuación, partiendo desde el submenú "configuración de la red", ingresaremos en el apartado "Nombre de host y cliente DNS.
  
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/HOSTNAME MENU DNS.PNG)

1.2.8- Ahora, configuramos el servidor DNS en "Servidores DNS" como primera opción asi mismo y luego un servidor DNS real, para traducir las direcciones ajenas de la red local. También en "Orden de resolución" ponemos como 1º opción "Archivos de host" y luego, "DNS". Y por último, en "Buscar dominios", seleccionaremos "Listado.." y debajo escribiremos el nombre de nuestro dominio DNS (en mi caso lounico.local ).




  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/DNS .png)

 1.2.9 Llegando casi al último paso, aplicaremos la configuración de la interfaz.
    ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/5 Salvar interfaz.PNG)

  1.2.10- Finalmente, vamos a la máquina de UbuntuServer y escribiremos el comando: ifconfig . Para comprobar que la configuración se aplicó correctamente.
  
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Red/Final.PNG)
  
  
  [2. Instalación del servidor DNS usando Webmin.](Instalación y comprobación.MD)
