![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/1.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/2.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/3.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/4.png)







El propósito de la misma es permitir la inclusión de otros archivos de configuración adicionales.
La primera línea incluirá las directivas presentes en ports.conf. Dentro de este encontramos 
la configuración de puertos. 

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/5.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/6.png)
































No existía el archivo 000-default.conf en el directorio ya que aún no habíamos realizado el comando a2ensite por lo tanto aún no se había creado. A2ensite es un script que habilita un sitio web especificado (que contiene un bloque VirtualHost) dentro de la configuración de apache2. Mediante la creación de enlaces simbólicos en / etc/apache2/sites-enabled.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/7.png)


ServerRoot 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/8.png)
La directiva ServerRoot especifica el directorio de nivel superior que tiene el contenido web. Por defecto, ServerRoot está configurado a "/etc/httpd" para servidores seguros y no seguros. 

Timeout 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/9.png)
Timeout define, en segundos, el tiempo que el servidor esperará por recibir y transmitir durante la comunicación. Timeout está configurado por defecto a 300 segundos, lo cual es apropiado para la mayoría de las situaciones. 

KeepAlive 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/10.png)
KeepAlive determina si el servidor permitirá más de una petición por conexión y se puede usar para prevenir a un cliente consumir demasiados recursos del servidor. 
MaxKeepAliveRequests 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/11.png)
Esta directiva establece el número máximo de peticiones permitidas por cada conexión persistente. El Proyecto Apache recomienda un valor alto, lo que mejoraría el rendimiento del servidor. El valor predeterminado de MaxKeepAliveRequests es de 100 que debería bastar en la mayoría de los casos. 
KeepAliveTimeout 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/12.png)

La directiva KeepAliveTimeout establece el número de segundos que el servidor esperará tras haber dado servicio a una petición, antes de cerrar la conexión. Una vez que el servidor recibe una petición, se aplica la directiva Timeout en su lugar. KeepAliveTimeout está configurado a 15 segundos por defecto. 
User y Group 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/13.png)
La directiva User establece el nombre de usuario para el proceso del servidor y determina qué archivos puede accesar el servidor. Cualquier archivo que no esté accesible a este usuarip tampoco estará disponible para los clientes del Servidor Apache HTTP. 
Especifica el nombre del grupo de los procesos Servidor Apache HTTP. 
ErrorLog 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/14.png)

ErrorLog especifica el archivo donde se guardan los errores del servidor . Por defecto, esta directiva es configurada a /var/log/httpd/error_log. 


Consulta la documentación de Apache y responde entonces a las siguientes preguntas.

¿Se permiten conexiones persistentes?Si, las conexiones persistentes nos permite el poder hacer todas las peticiones a través de la misma conexión, y no tener que negociar nuevas conexiones. La respuesta del servidor será más rápida y tendremos un mejor rendimiento. . ¿Qué directiva define este comportamiento? 
KeepAlive
¿Cuál es el fichero de errores?El registro de errores del servidor, cuyo nombre y ubicación se especifica en la directiva ErrorLog, es el más importante de todos los registros. Apache enviará cualquier información de diagnóstico y registrará cualquier error que encuentre al procesar peticiones al archivo de registro seleccionado. Es el primer lugar donde tiene que mirar cuando surja un problema al iniciar el servidor o durante su operación normal, porque con frecuencia encontrará en él información detallada de qué ha ido mal y cómo solucionar el problema . ¿Qué directiva lo define? Errorlog.

Consulta el fichero /etc/apache2/ports.conf, y comprueba cuál es el puerto en el que escucha las peticiones Apache. En el 80 y en caso de habilitar el módulo en el 443. ¿En qué puerto escuchará también si se habilita el módulo modssl?. CAPTURA DE PANTALLA
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/15.png)



Consulta el fichero /etc/apache2/sites-avalaible/000-default.conf observa y comenta la función de cada uno de los siguientes puntos:
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/16.png)


Dentro de la directiva <VirtualHost>... </VirtualHost> se define el comportamiento del servidor virtual por defecto.
Los VirtualHost son una configuración muy útil al momento de desarrollar nuestras aplicaciones ya que las mismas permiten acceder fácilmente a una aplicación PHP alojada un en servidor web Apache a través de un simple dominio que configuremos en nuestra máquina o servidor.
La primera línea <VirtualHost> simplemente indicamos la IP (a través del dominio) del virtual host y el puerto que por defecto es el 80.
El ServerName establece la base o raíz del dominio y con esta dirección es la que emplearemos en el navegador para accedes a nuestra aplicación.
El DocumentRoot establece la ubicación al directorio que en otras palabras significa el sitio a donde apunta nuestro dominio configurado con el VirtualHost.
La directiva ErrorLog determina el nombre del fichero en el cual el servidor almacenará los mensajes de error en caso de que ocurra alguno. Si el file-path no es absoluto, entonces se asume que es relativo al valor especificado en la directiva ServerRoot.



Consulta el fichero /etc/apache2/apache2.conf observa y comenta la función de cada uno de los siguientes puntos:


La directiva contenedora <Directory> .... </Directory> que se utiliza para determinar cómo Apache sirve el contenido del directorio/var/www.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/17.png)

La configuración de Apache se realiza a través de archivos de texto mediante directivas que permiten escoger las distintas opciones disponibles.

Aunque las directivas son las mismas sea cual sea el sistema operativo, la localización de los archivos de configuración es diferente.

Realiza una captura de ese fichero y señala en él la directiva que se sigue.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/18.png)


Options FollowSymLinks. es una directiva regla de los servidores http de Apache , la cual tiene la función de seguir los enlaces simbólicos de un directorio o carpeta. Si ponemos FollowSymLinks o +FollowSymLinks, lo afirmamos y permitimos que se sigan los enlaces simbólicos.
AllowOverride . controla qué directivas se pueden situar en los ficheros .htaccess.
Require. proporciona una variedad de diferentes maneras de permitir o denegar el acceso a los recursos. Además puede ser usada junto con las directivas:RequireAll, RequireAny, y RequireNone, estos requerimientos pueden ser combinados de forma compleja y arbitraria, para cumplir cualquiera que sean tus políticas de acceso.


CONFIGURACIÓN BÁSICA DE APACHE 

Vamos a crear dos archivos de configuración fp.conf que hará referencia a la web alojada en la ruta /var/www/fp/.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/19.png)








Crear los siguientes directorios y archivos:

 +  `/var/www/fp/index.html`
 +  `/var/www/fp/ciclos/listado.html`
 +  `/var/www/fp/ciclos/examenes/`
 +  `/var/www/fp/ciclos/asir/asir.html`
 +  `/var/www/fp/ciclos/daw/daw.html`
 +  `/var/www/fp/ciclos/dam/dam.html`



![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/20.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/21.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/22.png)





Luego realizamos un netplan apply para realizar la conexión con el cliente. 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/23.png)



Para esto tenemos que cambiar la configuración el archivo fp.conf que está en la ruta etc/apache2/sites-available y proceder a darle un Name y un Alias. 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/24.png)


Antes de lanzarnos a abrir nuestra página web por parte del cliente tenemos que acceder al archivo host en el cliente, y modificar este poniendo la ip de la cual vamos a hacer la petición y el nombre del host. Previamente de todo esto vamos a tener que tener activa la red interna y hacer un reload de apache server. 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/25.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/26.png)


Ficheros a servir por defecto (Directory Index).


Desde cliente_nombre abre un navegador y establece una conexión a http://10.70.XX.11
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/27.png)
	

No se ha solicitado ningún recurso en concreto por lo que el servidor ha enviado el index.html (valor en la directiva DirectoryIndex por defecto). CAPTURA DE PANTALLA
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/28.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/29.png)

Renombra el fichero /var/www/fp/index.html a /var/www/fp/indice.html
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/30.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/31.png)



Desde cliente_nombre abre un navegador y establece una conexión a http://10.70.XX.11. ¿Qué ocurre ahora? ¿Ha cambiado lo que envía el servidor?. CAPTURA DE PANTALLA
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/32.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/33.png)



Cambiamos el nombre de index.html a indice.html.
Hacemos primero un reload de apache. Antes de esto hacemos un sudo a2ensite de fp. 
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/34.png)




Edita el fichero /etc/apache2/apache2.conf y añade la siguiente directiva: DirectoryIndex listado.html en la la sección<Directory /var/www>. Explica que conseguimos al hacer esta modificación CAPTURA DE PANTALLA
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/35.png)

Conseguimos crear un listado el cual incluye la carpeta ciclos y el indice.html. 

Desde cliente_nombre abre un navegador y establece una conexión al servidor de nuevo. ¿Ha cambiado el fichero de carga?.CAPTURA DE PANTALLA

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/36.png)


Páginas de error personalizadas.

Configura el servidor para que cuando retorne el código de error 404 (página no encontrada) envíe el texto Página no encontrada en el servidor.

Para configurar esto solo debemos crear un archivo error en var/www/fp y enlazarlo en el archivo localized-error-pages.conf que se encuentra en /etc/apache2/conf-available
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/37.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/38.png)




Reinicia el servidor. Desde el cliente_nombre establece una conexión a http://www.fpdaw.org/noexiste.html y muestra qué te aparece en la pantalla.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/39.png)





Redirecciones.

Configura el servidor para que al entrar a http://www.fpdaw.org/ciclos haga una redirección automática hacia http://www.fpdaw.org/dam mostrando la página web correspondiente a DAM.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/51.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/52.png)

Alias.

Crea un alias de forma que forma que al entrar en http://www.fpdaw.org/logosmuestre el contenido de los logotipos alojados en la ruta/home/usuarios/Documentos

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/53.png)
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/54.png)

Autenticación

Configura el servidor creando dos grupos de usuarios suiguientes: + 
alumnos :formado por alumno1 y alumno2 
profesores. formado por profesor1 y profesor2
Los profesores deben poder acceder a todo el site, mientras que los alumnos tienen el acceso restringido a la carpeta /fp/ciclos/examenes.
Creamos la directiva.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/lodedirect.png)

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/55.png)

Luego realizamos el a2enmod de authz_groupfile

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/56.png)

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/57.png)

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/58.png)




Creamos los alumnos y profesores registrandolos en el fichero passwd.
![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/44.png)

Creamos el archivo grupos donde generamos los grupos. 


Le damos grupo a los usuarios y le damos solo permiso al grupo profesores en la directiva. 




Configuración de HTTPS

Configura el uso de HTTPS en el servidor web. Explica detalladamente todo el proceso aportando capturas de pantalla.

Primero procedemos a instalar certbot


![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/59.png)

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/60.png)

En el caso que falte el plugin de apache tendremos que ejecutar sudo apt-get install python-certbot-apache -y

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/61.png)

![image](https://github.com/romentoss/dpl_B_romen/blob/master/tareas/practicas/proyecto/imagenes/62.png)











