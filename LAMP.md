##Instalacion de LAMP en Ubuntu
Ingresar como usuario root y actualizar los paquetes  
`$ sudo`  
`$ apt-get update` 

###Instalacion de Apache2
Correr el siguiente comando para instalar apache2  
`$ apt-get install apache2`  

Escribir el siguiente comando para visualizar los errores de sintaxis  
`$ sudo apache2ctl configtest`  

Para corregir el mensaje de advertencia abrir el archivo de configuracion  
`$ vi /etc/apache2/apache2.conf`  
`Y escribir en la ultima linea "ServerName nombre_del_dominio_o_IP"`  

Reiniciar o Recargar el servicio  
`$ service apache2 reload`  

Volver a ingresar el comando y ya no se visualizara el error de sintaxis  
`$ sudo apache2ctl configtest`  

###Ajustar el Firewall para permitir el trafico Web
Instalar el Firewall UFW  
`$ apt-get install ufw`  

Visualizar si UFW tiene un perfil de aplicación para Apache  
`$ sudo ufw app list`  

Si observa el perfil Apache Full, deberia mostrar que habilita el tráfico a los puertos 80 y 443:  
`$ sudo ufw app info "Apache Full"`  

Permitir el trafico entrante para este perfil  
`$ sudo ufw allow in "Apache Full"`  

###Instalacion de Mysql 
Para instalar Mysql correr el siguiente comando  
`$ sudo apt-get install mysql-server`  

El siguiente comando sirve para configurar la seguridad en Mysql  
`$ sudo mysql_secure_installation`  

Para acceder a mysql mediante consola escribir el siguiente comando y luego escribir la contraseña  
`$ mysql -u nombre_usuario -p`  

###Instalacion de PHP
Añadir en /etc/opt/sources.list los siguientes paquetes si en caso no hay un paquete candidato para la instalacion (Para el caso de DEBIAN)  
`deb http://packages.dotdeb.org jessie all`  
`deb-src http://packages.dotdeb.org jessie all`  
    
El comando siguiente instala PHP, la libreria para interactuar con el servidor Apache2, la libreria de encriptacion y la libreria para interactuar con Mysql  
El comando siguiente instala PHP, la libreria para interactuar con el servidor Apache2, la libreria de encriptacion y la libreria para interactuar con Mysql  
`$ sudo apt-get install php7.0 libapache2-mod-php7.0 php7.0-mcrypt php7.0-mysql`
