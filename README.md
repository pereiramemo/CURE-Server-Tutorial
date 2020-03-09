# CURE-Server-Tutorial


1. Configuramos la ["Virtual Private Network" (VPN)](https://es.wikipedia.org/wiki/Red_privada_virtual) siguiendo los pasos de este [enlace](http://wiki.cure.edu.uy/index.php/Como_configurar_conexi%C3%B3n_VPN).
2. Bajamos e instalamos el programa [PuTTY](https://www.putty.org) que nos permitira conectarnos vis "Secure Shell" (SSH) al servidor.
3. Una vez instalado, nos conectamos de con el siguiente comando:

```
ssh -X usuario@lacalavera.cure.edu.uy
```
4. Luego de ingresar la contraseña estaremos logueados en el servidor (pero sin interfase grafica). [Aca](https://fortinux.gitbooks.io/humble_tips/content/usando_la_linea_de_comandos/) hay un tutorial basico para usar la linea de comando.

5. Para conectarnos con una interfase grafica (i.e., ver la pantalla del servidor), debemos usar el ["Virtual Network Computing" (VNC)](https://es.wikipedia.org/wiki/VNC). Para esto, primero tenemos que instalar un cliente de VNC en nuestra computadora (creo que PuTTY se podria usar para esto) y luego vamos a correr el siguiente comando desde el servidor, para iniciar el VNC server:
```
vncserver :1 -geometry 1400x1000

```
### Explorar en windows ...

6. Para copiar archivos: [rsync](https://kyup.com/tutorials/copy-files-rsync-ssh/) o PuTTY.

### Explorar en windows ...

7. Para usar R copiamos el siguiente link en el browser de nuestra computadora: http://lacalavera.cure.edu.uy:8787. Luego, simplemente nos logueamos con nuestro usuario y contraseña del servidor. 
