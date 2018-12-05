# UBUNTU

1.- Primero instalamos Apache, MySQL y PHP. Todo lo podemos instalar con este código para que sea mas rapido:

$ sudo apt install apache2 php mysql-server mysql

1.1.- Si quieres podemos hacer unas pruebas para ver si todo quedo bien.

$ sudo service apache2 start

$ php ==version

$ sudo service mysql start 

2.- Para sacar la base de datos escribimos este codigo:

$ cd /var/www/html

$ sudo git clone https://github.com/dgeti-cetis108/Programacion-M4S2-2018.git

3.-Aquí, la base de datos tiene el nombre de Programacion-M4S2-2018 y le vamos a cambiar el nombre a library.com

$ sudo mv Programacion-M4S2-2018 library.com

4.- Le vamos a agregar la base de datos al  html.

$ cd library.com/db

$ sudo -i

mysql>source  /var/www/html/library.com/db/library.sql

5.- Ahora, vamos a crear un usuario y una contraseña.

mysql>create user ´Alfonso´@´localhost´ identified by ´123´;

6.- Ya que termine le vamos a dar permisos.

mysql>grant all on library.* to ´Alfonso´@´localhost´;

7.- Y ahora vamos a salirnos de MySQL.

mysql>exit

8.- Comprobamos la conexión de mysql con nuestro nuevo usuario.

$ mysql -u Alfonso -p

9.- Editaremos nuestro library.com

$ sudo service apache2 restart

$ sudo apt install php-mysql

$ sudo nano /var/www/html/library.com/classes/conexion.php

10.- Cambiamos nuestra IP para que cuando pongamos library.com nos redireccione.

c:\>windows\system32\drivers\etc\hosts

$ sudo nano library.com.conf

$ cd /etc/apache2/sities-available

<VirtualHost *:80>

​	ServerName "library.com"

​	ServerAlias "www.library.com"

​	Server Admin "16325061080097@cetis108.edu.mx"

​	DocumentRoot "/var/www/html/library.com"

​	ErrorLog "/var/log/library.com-error.log"

​	CustomLog "/var/log/library.com-access.log" common

"</VirtualHost>"

11.- Y ya para terminar agregamos los siguientes códigos para que sirva correctamente.

$ sudo service apache2 restart

$ sudo a2ensite library.com





