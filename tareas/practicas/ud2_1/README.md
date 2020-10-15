
##Instalar Apache.
#Primero hacemos un sudo apt update
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/1.png?raw=true)
#Luego procedemos a instalar apache con sudo apt install apache2
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/2.png?raw=true)
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/3.png?raw=true)
##Configurar el firewall.
#Hacemos sudo ufw app list Obteniendo una lista de los perfiles de aplicación.
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/4.png?raw=true)
#Se recomienda habilitar el perfil más restrictivo, que de todos modos permitirá el tráfico que configuró. 
#Debido a que en esta práctica aún no configuramos SSL para nuestro servidor, solo deberemos permitir el tráfico en el puerto 80:
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/5.png?raw=true)
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/6.png?raw=true)
#Podemos verificar el cambio mediante el siguiente comando:
#sudo ufw status
#Para volver al estado activo: sudo ufw enable
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/8.png?raw=true)
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/9.png?raw=true)
## Comprobar el estado del servidor web con sudo systemctl status apache2.
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/10.png?raw=true)
##Comprobar funcione correctamente mediante su dirección ip.
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/12.png?raw=true)
##Administrar el proceso de Apache.
#Usamos sudo systemctl stop apache2 para parar el server. 
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/11.png?raw=true)
# Para iniciar el servidor web cuando no esté activo usamos: sudo systemctl start apache2.

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/13.png?raw=true)
#Para detener y luego iniciar el servicio de nuevo, usamos:sudo systemctl restart apache2
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/14.png?raw=true)
#Si solo realiza cambios de configuración, Apache a menudo puede recargarse sin cerrar conexiones. Para hacerlo, utilice este comando:sudo systemctl reload apache2
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/15.png?raw=true)
#Por defecto, Apache está configurado para iniciarse automáticamente cuando el servidor (Ubuntu) lo hace. Si no es lo que quiere, deshabilite este comportamiento escribiendo lo siguiente:sudo systemctl disable apache2
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/16.png?raw=true)
#Para volver a habilitar el servicio de modo que se cargue en el inicio, escriba lo siguiente:sudo systemctl enable apache2
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_1/imagenes/17.png?raw=true)


