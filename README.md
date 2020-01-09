En esta página se explicará cómo configurar un servidor DNS de BIND9 sobre UbuntuServer 16.04.1 que previamente hemos instalado.

## ÍNDICE
[1. Información y configuración de la(s) máquina(s) virtual(es).](Material necesario.MD)

[2. Instalación del servidor DNS usando Webmin.](Instalación y comprobación.MD)

[3. Configuración del DNS con Webmin.](README.md)

[4. Comprobación de los errores sintácticos de la configuración del DNS empleando Webmin.](README.md)

 
## 3. CONFIGURACIÓN DEL DNS CON WEBMIN.

### Crear Zona Directa.

   3.1- Partiendo la pantalla de configuración (del punto 2-3- Comprobar que la instalación del DNS se instaló correctamente), debemos darle a "Create master zone".
   
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/zonas.PNG)

   3.2- **(Registro NS)** Ahora, configuramos la zona maestra: en "Zone type" lo pondremos en 'Forward (Name to Addresses)'. Después en: "Domain name / Network" escribiremos nuestro dominio (debe ser el mismo dominio que hemos puesto en "Listado..." cuando estabamos configurando el UbuntuServer,en mi caso lounico.local). Por último nos obligará poner algo en: "Email address", podemos escribir cualquier cosa para evadirlo si no queremos poner un correo verdadero.
 
 
 

   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/1 zona maestra directa.PNG)
  
   3.3- **(Registro A)** Una vez creado la zona maestra, podemos visualizar todas las opciones de configuración de la zona maestra, de momento, le daremos a la casilla "Address(0)".
   
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/2 menús zona maestra.PNG)

   3.4- Dentro de "Address(0)", procederemos a poner los nombres de los equipos en la variable "Name" junto con su respectiva IP privada en "Address".
   
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/3 poner registros nombres a IP.PNG)
   Crearemos varias más, para poder probarlas más adelante.

Después de crear varias IP con los nombres, en la esquina superior derecha, nos encontraremos 2 botones; pulsaremos primero dónde dice: "Apply configuration luego en: "Apply zone", para salvar los cambios.

   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/3 poner registros nombres a IP 2.PNG)
   
   3.5- Desde el menú de configuración de la zona maestra, le daremos a "Name Alias".
            ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/CNAME 0.PNG)
   
   3.6- **(Registro CNAME)** Ahora procederemos con los alias o CNAME. En "Name", escribiremos el nombre del subdominio y en "Real Name" pondremos el nombre que habíamos puesto en "Name" del menú "Address" de los pasos 3-3 y 3-4, pero alfinal añadimos el dominio (para hacer referencia a un host).
   
 
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/4 CNAME.PNG)
   
   Una vez finalizada la creación de CNAME, le volvemos a dar primero dónde dice: "Apply configuration" luego en: "Apply zone", para salvar los cambios.
 
![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/4 CNAME 2.PNG)

   3.7- **(Registro MX)** Casi llegando al último paso de esta zona maestra, vamos a hacer un registro MX (e-mail). Para ello, nos situamos en la configuración de la zona maestra y le daremos a "Mail Server".
   
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/mailserver.PNG)

   3.8- Ahora pondremos en "Name" cómo queremos que se llame el servicio web, en mi caso, le puse "servidorweb" y en "Real Name" ponemos la IP de nuestro servidor email que tengamos (que en mi caso, es el propio UbuntuServer). Aquí también le daremos a "Apply Configuration" y "Apply Zone".
   
    
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/Capturaq9w48209432.PNG)


   3.9- Para terminar de configurar esta zona, nos situamos en la ventana de inicio de la zona y arriba a la izquierda, estarán los 2 botones para guardar la configuración.
   
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/direc.png)
  
### Crear Zona Inversa

   3.10- A continuación, crearemos otra zona maestra (viendo como referencia el paso 3.1), pero esta será inversa NO le seleccionamos 'Forward (Name to Addresses)', si no, el otro el que dice 'Reverse (Addresses to Name)', en "Domain name / Network" escribiremos la dirección de red, pero sin la última sección (se quedará en 3 secciones; 192.168.1).
 
 En "Master server", lo dejamos como está y pondremos el mismo correo electrónico en la variable "Email". 
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/5 zona maestra inversa.PNG)
  
   3.11- **(Registro PTR)** Posteriormente de crear la zona maestra inversa, podremos observar todas las casillas de configuración, hacemos click en "Reverse Addresses(0)".
   
   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/6 menús zona maestra inversa.PNG)
   
   3.12- Ahora haremos justamente lo contrario al paso 3.4-, pondremos primero la dirección IP en "Address" y el nombre en "Hostname".
 ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/7 poner IP a nam.PNG)
 
 Y procederemos nuevamente a salvar los cambios con las opciones: "Apply configuration" luego en: "Apply zone", para salvar los cambios.
   
   3.13- Por último paso, salvaremos la configuración desde el raíz del DNS (dónde hemos dado click en "create master zone".
    ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/Sin título.png)
   
   
  
## 4. COMPROBAR ERRORES SINTÁCTICOS EN LA CONFIGURACIÓN DNS EMPLEANDO WEBMIN.

Para comprobar si hay errores sintácticos en las zonas maestras del servidor DNS, debemos entrar primero en la configuración de una de las zonas maestras.

Para ir a las zonas maestras, iremos a la raíz del DNS y ahí podemos visualizar las zonas maestras creadas (tanto directa o inversa).
    ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/Sin título2.png)

### Zona Directa:

Primero, debemos situarnos en la zona maestra directa (lounico.local) y dar clic en el botón: "Check Records".

   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/Check Di.PNG)

Y como podemos ver, manda un mensaje de que no se han encontrado errores.

   ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/Check Di2.PNG)

### Zona Inversa:

Para la zona inversa, es EXACTAMENTE lo mismo que en la zona directa, nos situamos en la zona maestra inversa (192.168.1) y le daremos a "Check Records".

  ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/Check Inversa.PNG)
  
  Y en la otra zona, tampoco hay errores como podemos visualizar en la siguiente fotografía.
  
  ![Insertar foto que te cagas de lo chula que es](Imagenes/Configuración/Check Inversa 2.PNG)
  
  **OJO: ESTO SOLO CORRIJE SOLAMENTE ERRORES SINTÁCTICOS, SI TE EQUIVOCASTES A LA HORA DE ESCRIBIR LA IP O NOMBRE, NO TE LO DIRÁ.**
