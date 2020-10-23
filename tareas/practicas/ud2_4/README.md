# 2.Instalación del servidor Apache
## .Actualización del repositorio y paquetes.
## sudo apt update
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/1.png?raw=true)
## sudo apt upgrade
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/2.png?raw=true)

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/3.png?raw=true)
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/4.png?raw=true)
# 3.Instalación del servidor de base de datos MaríaDB
## sudo apt install mariadb-server mariadb-client

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/5.png?raw=true)

## Inserta el comando utilizado para comprobar el estado del
## servidor y una captura de pantalla
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/6.png?raw=true)
## Para permitir que MariaDB se inicie automáticamente en el momento del arranque, debemos ejecutar:
## sudo systemctl enable mariadb
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/7.png?raw=true)


## Ejecutamos un script de seguridad posterior a la instalación, por medio del siguiente comando:
## sudo mysql_secure_installation
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/8.png?raw=true)
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/9.png?raw=true)


## Prueba el acceso a la base de datos con la nueva contraseña.
## Inserta  comando utilizado y captura de pantalla
## mysql -u 'usuario' -p 'password'
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/10.png?raw=true)

## Crea un nuevo usuario en la base de datos llamado developer con la contraseña 5t6y7u8i.
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/11.png?raw=true)
# 4.Instalación de la última versión de PHP.
## Vamos a escribir el siguiente comando para instalar PHP y algunos módulos PHP comunes:
## sudo apt install php7.4 libapache2-mod-php7.4 php7.4-mysql php-common php7.4-cli php7.4-common php7.4-json php7.4-opcache php7.4-readline
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/12.png?raw=true)
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/13.png?raw=true)

## Ahora tendremos que activar el módulo Apache php8 y reiniciar el servidor web Apache.
## sudo a2enmod php7.4

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/14.png?raw=true)
## sudo systemctl restart apache2
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/15.png?raw=true)

## Verificamos la versión de PHP instalada mediante el comando:
## php --version
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/16.png?raw=true)

## Dentro del archivo vamos a pegar el siguiente código PHP:
## <?php phpinfo(); ?>
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/17.png?raw=true)
## Una vez guardado el archivo, ahora en la barra de direcciones del navegador tendremos que escribir dirección-ip/info.php.
## Inserta captura de pantalla del resultado

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/18.png?raw=true)
# 4.1
 # Ejecutando código PHP en Apache.

## sudo a2dismod php7.4
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/19.png?raw=true)
## Posteriormente instalamos PHP-FPM:
## sudo apt install php7.4-fpm

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/20.png?raw=true)
## Continuamos habilitando proxy_fcgi y el módulo setenvif:
## sudo a2enmod proxy_fcgi setenvif

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/21.png?raw=true)
## El siguiente paso será habilitar el archivo de configuración /etc/apache2/conf-available/php7.4-fpm.conf:
## sudo a2enconf php7.4-fpm
## Después debemos reiniciar Apache:
## sudo systemctl restart apache2
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/22.png?raw=true)
## Ahora, si actualizas la página info.php en el navegador, encontrarás que la API del servidor ha cambiado de Apache 2.0 Handler a FPM/FastCGI, lo que significa que ## el servidor web Apache pasará las solicitudes de PHP a PHP-FPM.

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_4/imagenes/23.png?raw=true)
















