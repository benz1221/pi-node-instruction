# Nivel especializado

- Los puertos necesitan abrirse en dos lugares: en tu router  y en el firewall de la PC donde tienes instalado el nodo. 

- El router debe apuntar a la PC donde tengas instalado el nodo. 

- El firewall de la PC debe permitir **conexiones entrantes a Docker**, por lo menos en el rango de puertos **31400-31409**.

# Solución de Problemas

### ¿Al ingresar a [http://127.0.0.1:31400](http://127.0.0.1:31400) desde la PC donde tienes instalado el nodo funciona?
 
- La página debe responder con un "OK FROM PORT 31400". 

- Si no, entonces hay un problema en la PC y no en el router. 
  - (¿firewall?, ¿antivirus?)
  - Una de dos: o el puerto de escucha del contenedor de Docker no está ejecútandose o el firewall esta bloqueando el puerto. 

- **Nota:** la dirección 127.0.0.1 es la *Dirección IP local* de cada computadora. Es por eso que esta dirección debe funcionar para todos. 

### Comprueba que los puertos de tu PC esten abiertos usando herramientas externas.

Ejemplo: Ingresa a [yougetsignal.com/tools/open-ports/](http://yougetsignal.com/tools/open-ports/) y escribe **31400** en el campo de texto donde dice **Port Number** y luego das clic en el botón **Check**.

Visita tu IP pública: Obtén tu dirección IP pública desde la misma página (campo de texto que dice **Remote Address**); cópiala e ingresala en tu navegador. Antes de visitarla debes añadir el número de puerto al final de la misma. Ve si tu navegador obtiene una respuesta. Ejemplo de dirección que debes visitar http://123.45.67.89:31400 (sustituye la dirección IP por la tuya [lo que está antes de los dos puntos [:] )

### Windows firewall: ¿como abrir puertos?:

- Ve al Panel de Control -> Sistema y Seguridad -> Windows Firewall.
- Selecciona Configuración Avanzada -> Elige Reglas de Entrada en el panel de la izquierda.
- Haz clic con el botón derecho en Reglas de Entrada -> Seleccionar Nueva regla.
- Añade TCP, "31400-31409" y haz clic en Siguiente.
- Selecciona "Permitir la conexión" en la siguiente ventana. Haz clic en Siguiente.
- Selecciona el tipo de red y haz clic en Siguiente.
- Nombrala "Pi Network" y haz clic en Finalizar.


### Revisar si los puertos están abiertos o escuchando

- En Windows, abre el CMD. (https://www.howtogeek.com/235101/10-ways-to-open-the-command-prompt-in-windows-10/)
- Escribe "**_netstat -aon_**" o "**_netstat -aon | findstr 3140_**"
- Revisa que los puertos desde el **31400** al **31409** estén "escuchando".

### Cambiar los puertos con el celular como punto de acceso (Hotspot) (no es posible)
La mayoría de las veces la dirección IP que obtienes con tu conexión móvil ya está bajo un **NAT** de tu proveedor. Básicamente está dentro de una red privada con una sola dirección IP pública para que se conecten varias personas. Por lo tanto, el router de tu proveedor ISP bloquea las solicitudes y no puedes hacer nada al respecto. Necesitas una _dirección IP pública_ para poder recibir solicitudes en puertos específicos.