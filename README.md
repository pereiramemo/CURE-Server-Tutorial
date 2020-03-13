# CURE-Server-Tutorial


**1.** Configuramos la ["Virtual Private Network" (VPN)](https://es.wikipedia.org/wiki/Red_privada_virtual) siguiendo los pasos de este [enlace](http://wiki.cure.edu.uy/index.php/Como_configurar_conexi%C3%B3n_VPN).

**2.** Una vez conectados por VPN, nos podemos conectar al servidor con el siguiente comando:
```
ssh -X usuario@lacalavera.cure.edu.uy
```

**Nota1:** También nos podemos conectar usando directamente la dirección IP del servidor 164.73.226.83, en lugar del nombre.


**3.** Luego de ingresar la contraseña, estaremos logueados (aunque sin interfase gráfica). [Aca](https://fortinux.gitbooks.io/humble_tips/content/usando_la_linea_de_comandos/) hay un tutorial para usar la linea de comando. Alguns comandos básicos:  
```cd```: cambia de directorio  
```mkdir```: crea un directorio  
```ls```: lista los archivos en un directorio  
```less```: muestra el contenido de un archivo de texto  
```rm```: elimina un archivo o directorio (i.e.,```rm -r```)

**4.** Para conectarnos con una interfase gráfica, es decir ver la pantalla del servidor, debemos usar el ["Virtual Network Computing" (VNC)](https://es.wikipedia.org/wiki/VNC). Para esto, primero tenemos que instalar un cliente de VNC en nuestra computadora (e.g., [Remmina](https://remmina.org)) y luego vamos a correr el siguiente comando desde el servidor, para iniciar el VNC server:
```
vncserver :1 -geometry 1400x1000 
```

**Nota2:** los parámtros ```:1``` y ```-geometry 1400x1000``` deben ser ajustados.

Con el cliente VNC instalado en nuestra computadora local, vamos a entrar la dirección lacalvera.cure.edu.uy:5901 en el campo de conexión VNC.

**Nota3:** Igual que la conexión por ```ssh```, También podemos usar la dirección IP.

**5.** Para copiar archivos usaremos el prgrama [rsync](https://kyup.com/tutorials/copy-files-rsync-ssh/).

Por ejemplo, para copiar un archivo desde nuestra computadora local al servidor corremos el comando:

```
rsync -a /ruta/al/archivo/local/nombre_del_archivo usuario@lacalavera.cure.edu.uy:/ruta/de/destino/en/servidor
```

**6.** Para usar R en el servidor, vamos a usar Rstudio server. Para esto, simplemente compiamos el siguiente link en el browser de nuestra computadora: http://lacalavera.cure.edu.uy:8787. Luego, nos logueamos con nuestro usuario y contraseña del servidor.  

**Nota4:** Todos los archivos utilizados y generados en R estarán en el servidor, en nuestro directorio home.   

