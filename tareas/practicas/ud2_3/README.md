#1. Instalar Tomcat 9.


## sudo apt update
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/1.png?raw=true)
## Instalaremos los paquetes principales, correspondientes al núcleo de Tomcat y a las aplicaciones administrativas:
## sudo apt install -y tomcat9 tomcat9-admin

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/2.png?raw=true)


# 2. Configurar el firewall.
## Si vas a acceder a Tomcat 9 desde la red y tienes activado este firewall en Ubuntu 20.04 LTS, habrá que añadir una regla:
## sudo ufw allow 8080/tcp

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/3.png?raw=true)
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/4.png?raw=true)
# 3. Configuración de Tomcat 9 en Ubuntu Server.

    
## 3.1 Puerto de conexión.
## sudo nano /etc/tomcat9/server.xml
## Buscaremos la siguiente directiva Conector:
## ...
##     <Connector port="8080" protocol="HTTP/1.1"
##                connectionTimeout="20000"
##                redirectPort="8443" />
## ...
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/6.png?raw=true)

# 3.2 Usuarios de Tomcat.

## sudo nano /etc/tomcat9/tomcat-users.xml
## Antes del cierre del bloque tomcat-users añadiremos una definición de usuario con contraseña y los roles necesarios:
## ...
##         <user username="chacho" password="XXXXXXXX" roles="admin-gui,manager-gui"/>
## </tomcat-users>
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/7.png?raw=true)

# 3.3 Acceso remoto a las aplicaciones.

## sudo nano /usr/share/tomcat9-admin/manager/META-INF/context.xml
## Dentro del bloque Context encontraremos una directiva Valve:
## ...
##   <Valve className="org.apache.catalina.valves.RemoteAddrValve"
##          allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" />
## ...

## Debemos desactivar esta directiva encerrándola en un bloque de comentarios XML:
## ...
## <!--
## <Valve className="org.apache.catalina.valves.RemoteAddrValve"
##          allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" />
## -->
## ....
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/8.png?raw=true)


## Para el Gestor de Máquina Virtual, o aplicación Host Manager, habría que hacer un cambio exactamente igual en su archivo context.xml, ubicado en su propia ruta de ## configuración:
## sudo nano /usr/share/tomcat9-admin/host-manager/META-INF/context.xml
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/9.png?raw=true)
# 3.4 Aplicando los cambios a la configuración.
## Después de hacer estos cambios, habrá que reiniciar el servicio Tomcat 9 para aplicarlos:
## sudo systemctl restart tomcat9
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/10.png?raw=true)
# 4. Acceder a Tomcat 9.

## http://ip_del_server:8080
## Obteniendo como resultado la página de inicio de Tomcat 9:
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/11.png?raw=true)


# 5. Aplicación Manager.
## Si intentamos acceder al Gestor de Aplicaciones Web, aplicación /manager/html, o http://ip_del_server:8080/manager/html en este ejemplo, sí que se nos solicita  ## autenticación
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/12.png?raw=true)
## Introduciremos el nombre y la contraseña del usuario que creamos con el rol manager-gui para poder acceder, y se mostrará el Gestor de Aplicaciones Web de Tomcat, ## donde podrás desplegar, replegar, iniciar o detener aplicaciones web servidas desde Tomcat 9:
![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/13.png?raw=true)
# 6. Aplicación Host Manager.

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/14.png?raw=true)

# 7. Desplegando aplicaciones sobre Tomcat 9 en Ubuntu Server.

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/15.png?raw=true)

# 8. Cambiando el tamaño máximo admitido de los archivos .war

![imagen](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/ud2_3/imagenes/16.png?raw=true)



