# Preguntas Frecuentes

## Dispositivos / Usuarios:
### Los dispositivos nuevos, no se registran en la Plataforma

En ocasiones los dispositivos registrados nuevos se marcan automáticamente como inactivos, esto podrás comprobarlo en la vista de "Dispositivos" del administrador.

Esto provoca que las notificaciones no se envíen a estos dispositivos. Muy probablemente se deba a un problema con los límites de tu licencia, informate sobre el funcionamiento de las [licencias de TwinPush aquí](#funcionamiento-de-las-licencias).




## Envío de Notificaciones:
### No recibo la notificación

**Comprobaciones iniciales**

Lo primero que debemos hacer es descargar el PDF de reporte de la notificación que no ha sido entregada al dispositivo, en este informe, disponible en la vista de detalle de la Notificación, podremos ver si ha ocurrido algún error que TwinPush haya identificado, los errores más comunes son:

* No tiene envíos: No existían destinatarios ( dispositivos activos ) para nuestro envío, por lo que deberemos comprobar los destinatarios y que se encuentren activos, esto podremos consultarlo en la vista de "Dispositivos" de el Admin Web.
* Token No válido o error de certificado: Estos errores son habituales en envíos a iOS, requiere revisar la configuración de certificados de nuestra Aplicación, validez, caducidad, etc...

Si en el informe de TwinPush está registrado el envío correctamente sin errores, los motivos principales por los que no se recibe una notificación son los siguientes:

* Dispositivo Inactivo, principalmente ocasionado por un problema con el límite de la licencia.
* Notificaciones no habilitadas en el dispositivo, debemos comprobar que tenemos habilitadas las notificaciones y volver a realizar la prueba.
* Problemas de conectividad en el dispositivo, en ocasiones tanto la falta de cobertura como una conexión a una red corporativa pueden ocasionar que las notificaciones no lleguen o lo hagan con cierto retraso.
* La notificación si ha llegado pero ha pasado desapercibida.

En general, siempre que tengamos problemas para determinar por qué una notificación no llega a un dispositivo en concreto, debemos comprobar la actividad de nuestro dispositivo: En la vista de "Dispositivos" podremos encontrar nuestro dispositivo, asociado a nuestro usuario, debemos percatarnos que esté efectivamente activo y tenga habilitadas las notificaciones.

Podemos incluso reinstalar la Aplicación y repetir el proceso de registro.

Si has seguido todos estos pasos y aun así el problema persiste, ponte en contacto en [support@twincoders.com](mailto:support@twincoders.com)



### No aparece notificación en el buzón de la Aplicación

TwinPush cuenta con un buzón por usuario, donde se podrán consultar las notificaciones de un usuario en concreto desde una Aplicación.

Si no visualizamos una campaña en el listado de notificaciones, lo más probable es que, en el momento del envío, no hayamos marcado la notificación para que se entregue en el buzón del usuario, requisito indispensable para que aparezca en el buzón posteriormente.


### El texto de la notificación no llega completo

El tamaño de las notificaciones está limitado por Apple y Google.

En primer lugar debemos tener en cuenta que el tamaño viene delimitado por todo lo que compone nuestra notificación, como el texto de la Push, así como la url, custom properties, etc... Si toda esta petición sobrepasa el límite establecido, TwinPush recortará el texto del mensaje para garantizar la entrega del mensaje a todos los sistemas operativos.

Es por esto que en ocasiones, el texto de la notificación se verá recortado.

Para solucionarlo, podremos intentar recortar espacio de la URL o acortar el mensaje para que llegue completo.


### No se visualiza el contenido Web de la notificación

La notificación llega pero el contenido web que debería visualizarse al abrir la notificación no abre en la Aplicación.

Si este es el problema deberemos hacer varias comprobaciones:

* Ver si la web destino carga correctamente en un navegador, en ocasiones el problema se debe a una sobrecarga en la Web destino provocada por las peticiones de los usuarios móviles en un momento dado.
* La Web tiene referencias a URL no seguras. En ciertos sistemas operativos, si la Web destino no es segura, no se abrirá dentro de nuestra aplicación, pudiendo obligarnos a abrirla en el navegador del dispositivo.

Si no visualizamos ningún contenido rico enviado, podríamos tener un problema de integración del Webview de la Aplicación y tendrás que ponerte en contacto con el equipo de desarrollo de tu Aplicación.


### Problemas al subir archivo de envío

TwinPush ofrece la posibilidad de cargar ficheros con el target de nuestra campaña.

El procesamiento del archivo de TwinPush maneja ciertos formatos y composiciones y debes seguir la [guía de creación de Archivos de envío](https://twincoders.atlassian.net/wiki/display/TWP/Import+target+file) para su correcto funcionamiento.




## Otras Preguntas
### No recibo emails de confirmación o invitación a una aplicación

TwinPush te enviará un correo electrónico para confirmar tu cuenta, cambiar tu contraseña, darte acceso como invitado a una Aplicación u otras acciones que lo requieran, en ocasiones, el correo se almacena en la carpeta Spam o queda bloqueado por un sistema de seguridad de tu empresa, si no recibes el email, ponte en contacto con nosotros en [support@twincoders.com](mailto:support@twincoders.com)


### No tengo acceso a los ajustes de la Aplicación

Unicamente el usuario administrador de la cuenta tiene acceso a los ajustes y configuración de la Aplicación, donde tendremos las claves de autenticación, gestión del equipo de usuarios, así como la configuración principal de la Aplicación.



## Funcionamiento de las licencias

TwinPush basa sus licencias en la contratación de un número de dispositivos activos.

Un dispositivo activo es aquel que se haya registrado en algún momento en la plataforma a través del acceso a la Aplicación y que haya accedido al menos una vez en un periodo de tiempo determinado. Por defecto, este periodo es de 6 meses, aunque este parámetro temporal es configurable por cuenta. 

Todo aquel dispositivo que lleve 6 meses sin registrar actividad pasará automáticamente a formar parte de los dispositivos inactivos, en cuyo caso dejará de recibir notificaciones, reportar estadísticas y contar como dispositivo dentro de licencia.

### Dispositivos fuera de licencia contratada
En el caso de que una cuenta sobrepase el número de dispositivos activos contratados, TwinPush marcará la cuenta como “fuera de licencia” y los dispositivos nuevos que se registren se marcarán como inactivos, esta comprobación se realiza semanalmente. 

De esta manera, los dispositivos activos serán aquellos que han mostrado actividad los últimos 6 meses y tengan una fecha de registro más antigua. 

### Configuración tiempo de actividad
Es posible configurar el periodo de tiempo sin actividad necesario para considerar un dispositivo como inactivo. Este periodo (en meses) se puede ajustar por cuenta. De este modo, es posible forzar que los dispositivos sin actividad se consideran inactivos antes en el tiempo. 

Este parámetro de configuración permitirá ajustar la cuenta para poder trabajar siempre con los más activos, pero se perderá la capacidad de comunicarse con los dispositivos menos activos, imposibilitando la realización de campañas para obtener recurrencia de estos usuarios. 
Si deseas cambiar este valor, deberás ponerte en contacto con[ support@twincoders.com](mailto:support@twincoders.com)