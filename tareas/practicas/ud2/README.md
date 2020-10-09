
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/1.png)
Para comenzar vamos al panel de control.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/2.png)
luego a redes e internet
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/3.png)
Entramos en centro de redes y decursos compartidos.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/4.png)
y en esta pantalla vamos a conexión de area local.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/5.png)
Nos dará el estado de la conexión, luego vamos a propiedades.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/6.png)
En este caso entramos en las propiedades de ipv4.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/7.png)
En esta pantalla desconectamos el dhcp y ingresamos nuestra ip. 
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/13.png)
luego regresamos al panel de control.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/14.png)
entramos en sistema y seguridad.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/15.png)
entramos en el firewall de windows.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/16.png)
Entramos en la configuración avanzada.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/17.png)
Creamos una nueva regla de entrada ya que no estamos recibiendo paquetes y tenemos que habilitar una respuesta icmp.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/18.png)
Damos boton derecho sobre reglas de entrada y creamos una nueva regla.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/19.png)
Seleccionamos personalizado.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/20.png)
Habilitamos la regla a todos los programas.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/21.png)
Seleccionamos icmpv4.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/22.png)
Seleccionamos cualquier dirección ip.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/23.png)
Habilitamos permitir la conexión.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/24.png)
Seleccionamos todos los checkbox.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/25.png)
Le damos un nombre y finalizamos.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/9.png)
En ubuntu server procedemos a ir a la ruta etc/netplan/
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/10.png)
Realizamos un sudo nano con el archivo que se encuentra dentro de la ruta.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/11.png)
configuramos la conexión según el protocolo netplan.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/12.png)
realizamos el ping hacia la máquina windows.
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/ultima.png)
Realizamos el ping de windows a linux. 
![imagen](https://raw.githubusercontent.com/romentoss/dpl_B_romen/master/tareas/practicas/ud2/imagenes/26.png)
Romen Padilla Polegre


