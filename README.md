# CURE-Server-Tutorial


**1.** Configuramos la ["Virtual Private Network" (VPN)](https://es.wikipedia.org/wiki/Red_privada_virtual) siguiendo los pasos de este [enlace](http://wiki.cure.edu.uy/index.php/Como_configurar_conexi%C3%B3n_VPN).



**2.** Una vez conectados por VPN, nos podemos conectar al servidor lacalavera u oceania con los comandos
`ssh -X usuario@lacalavera.cure.edu.uy` y `ssh -X usuario@oceania.cure.edu.uy`, respectivamente (sustituyendo la palabra `usuario` con su nombre de usuario). 

**Nota1:** También nos podemos conectar usando directamente la dirección IP del servidor: 164.73.226.87 y 164.73.226.92 (lacalavera y oceania, respectivamente).

**Nota2:** En caso de utilizar windows, será necesario instalar y configurar [PuTTy](https://www.putty.org/) para poder conectarse por [SSH](https://en.wikipedia.org/wiki/Secure_Shell). En está [página](https://phoenixnap.com/kb/install-putty-on-windows) pueden encontrar los pasos necesarios para la configuración. 

**3.** Luego de ingresar la contraseña, estaremos logueados (aunque sin interfase gráfica). [Aca](https://fortinux.gitbooks.io/humble_tips/content/usando_la_linea_de_comandos/) hay un tutorial para usar la linea de comando. 
Algunos comandos básicos son:  
```cd```: cambia de directorio  
```mkdir```: crea un directorio  
```ls```: lista los archivos en un directorio  
```less```: muestra el contenido de un archivo de texto  
```rm```: elimina un archivo o directorio (i.e.,```rm -r```)

**4.** Para conectarnos con una interfase gráfica, es decir ver el escritorio en el servidor, debemos usar el ["Virtual Network Computing" (VNC)](https://es.wikipedia.org/wiki/VNC). Para esto, primero tenemos que instalar un cliente de VNC en nuestra computadora (e.g., [Remmina](https://remmina.org)) y luego vamos a correr el siguiente comando desde el servidor para iniciar el VNC server:
```
vncserver :1 -geometry 1400x1000 
```

**Nota3:** Los parámetros ```:1``` y ```-geometry 1400x1000``` deben ser ajustados.

Con el cliente VNC instalado en nuestra computadora local, vamos a poner la dirección ```lacalavera.cure.edu.uy:5901``` en el campo de conexión VNC.

**Nota4:** Igual que la conexión por ```ssh```, también podemos usar la dirección IP.

**Nota5:** Por el momento, el servidor lacalavera es el únicao que tiene interfase gráfica. Dependiendo del uso de oceania, consideraremos en el futuro, instalar una interface gráfica también en este servidor.

**5.** Para copiar archivos desde nuestra computadora al servidor (y viceversa) usaremos el programa [rsync](https://kyup.com/tutorials/copy-files-rsync-ssh/).

Por ejemplo, para copiar un archivo desde nuestra computadora local al servidor lacalavera corremos el comando:

```
rsync -a /ruta/al/archivo/local/nombre_del_archivo usuario@lacalavera.cure.edu.uy:/ruta/de/destino/en/servidor
```

Para el servidor oceania, el comando sería especificando `oceania` en lugar de `lacalavera`:

```
rsync -a /ruta/al/archivo/local/nombre_del_archivo usuario@oceania.cure.edu.uy:/ruta/de/destino/en/servidor
```

**6.** Para usar R en el servidor, vamos a usar [RStudio Server](https://www.rstudio.com/products/rstudio/#rstudio-server). Para esto, simplemente copiamos el siguiente link en el browser de nuestra computadora: http://lacalavera.cure.edu.uy:8787. Luego, nos logueamos con nuestro usuario y contraseña del servidor.  

**Nota6:** Todos los archivos utilizados y generados en R estarán en el servidor. 

**Nota7:** Todas las conexiones al servidor, ya sea por SSH, VNC, o R, solo pueden hacerse si estamos conectados por VPN.

**Nota8:** Por el momento, el RStudio Server está únicamente instalado en la lacalavera. Dependiendo del uso de oceania, consideraremos en el futuro, tenerlo también en este servidor.
