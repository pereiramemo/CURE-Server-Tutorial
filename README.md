# CURE-Server-Tutorial


**1.** Configuramos la ["Virtual Private Network" (VPN)](https://es.wikipedia.org/wiki/Red_privada_virtual) siguiendo los pasos de este [enlace](http://wiki.cure.edu.uy/index.php/Como_configurar_conexi%C3%B3n_VPN).

**2.** Una vez conectados por VPN, nos podemos conectar al servidor con el siguiente comando:
```
ssh -X usuario@lacalavera.cure.edu.uy
```

**3.** Luego de ingresar la contraseña, estaremos logueados (aunque sin interfase gráfica). [Aca](https://fortinux.gitbooks.io/humble_tips/content/usando_la_linea_de_comandos/) hay un tutorial para usar la linea de comando. Alguns comandos básicos:  
```cd```: cambia de directorio  
```mkdir```: crea un directorio  
```ls```: lista los archivos en un directorio  
```less```: muestra el contenido de un archivo de texto  
```rm```: elimina un archivo o directorio (si se utiliza el flag -r)

**4.** Para conectarnos con una interfase gráfica (i.e., ver la pantalla del servidor), debemos usar el ["Virtual Network Computing" (VNC)](https://es.wikipedia.org/wiki/VNC). Para esto, primero tenemos que instalar un cliente de VNC en nuestra computadora (e.g., Remmina) y luego vamos a correr el siguiente comando desde el servidor, para iniciar el VNC server:
```
vncserver :1 -geometry 1400x1000 
```

**Nota1**: los parámtros ```:1``` y ```-geometry 1400x1000``` deben ser ajustados.


### Explorar en windows ...

6. Para copiar archivos: [rsync](https://kyup.com/tutorials/copy-files-rsync-ssh/) o PuTTY.

### Explorar en windows ...

7. Para usar R copiamos el siguiente link en el browser de nuestra computadora: http://lacalavera.cure.edu.uy:8787. Luego, simplemente nos logueamos con nuestro usuario y contraseña del servidor. 
