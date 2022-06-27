# Preguntas Frecuentes

## Dispositivos / Usuarios:
### Los dispositivos nuevos, no se registran en la Plataforma

En ocasiones los dispositivos registrados nuevos se marcan automáticamente como inactivos, esto podrás comprobarlo en la vista de "Dispositivos" del administrador.

[![](https://i.imgur.com/1DK9lQ7l.png)](https://i.imgur.com/1DK9lQ7.png)

Esto provoca que las notificaciones no se envíen a estos dispositivos. Muy probablemente se deba a un problema con los límites de tu licencia, informate sobre el funcionamiento de las [licencias de TwinPush aquí](#funcionamiento-de-las-licencias).


## Envío de Notificaciones:

### ¿Cuál es el límite de caracteres para los mensajes push?

Actualmente el límite en el tamaño del título o la alerta para una notificación push es de 500 caracteres, pero hay que también tener en cuenta el tamaño máximo del _payload_ (información completa de la notificación) que se envía a los servicios de Google y Apple. Este _payload_ incluye toda la información de la notificación, desde título y alerta, hasta propiedades personalizadas o la URL de contenido rico. Y tiene un tamaño máximo total de 2KB para iOS y 4KB para Android. Cada caracter suele ocupar 1B, así que es difícil alcanzar este límite haciendo un uso razonable. Aún así, es recomentable utilizar URLs cortas en la medida de lo posible para alejar más este límite.

El tamaño máximo del texto o del título de una notificación, por lo tanto, quedaría más determinado por lo que puede mostrar la pantalla de un teléfono o tablet (una notificación demasiado larga no se podría mostrar completa en la pantalla). Estos tamaños son (aproximadamente):

* **Título:** hasta 40 caracteres
* **Texto:** 40 caracteres con la pantalla bloqueada y hasta 200 en el centro de notificaciones de iOS y entre 40 y 500 (si se usan las notificaciones con texto grande, que es el comportamiento por defecto de TwinPush) en Android

### No recibo la notificación

**Comprobaciones iniciales**

Lo primero que debemos hacer es descargar el PDF de reporte de la notificación que no ha sido entregada al dispositivo, disponible en la vista de detalle de la Notificación.

[![](https://i.imgur.com/yMdCHnWl.png)](https://i.imgur.com/yMdCHnW.png)

En este informe podremos ver si ha ocurrido algún error que TwinPush haya identificado, los errores más comunes son:

* **No tiene envíos:** No existían destinatarios (dispositivos activos ) para nuestro envío, por lo que deberemos comprobar los destinatarios y que se encuentren activos, esto podremos consultarlo en la vista de "Dispositivos" de el Admin Web.
* **BadDeviceToken o Token No válido o error de certificado:** Estos errores son habituales en envíos a dispositivos iOS, requiere revisar la configuración de certificados de Apple APNS de nuestra Aplicación, en la sección de ajustes. Debes comprobar la validez del Certificado, o que se esté utilizando el Certificado correcto: Desarrollo o Producción (check Distribución marcado), según sea el caso y corregirlo si fuera necesario.

[![](https://i.imgur.com/n5QbpHUl.png)](https://i.imgur.com/n5QbpHU.png)


Si en el informe de TwinPush está registrado el envío correctamente sin errores, los motivos principales por los que no se recibe una notificación son los siguientes:

* **Dispositivo Inactivo:** principalmente ocasionado por un problema con el límite de la licencia de TwinPush [aquí](#funcionamiento-de-las-licencias).
* **Notificaciones no habilitadas en el dispositivo:** debemos comprobar que tenemos habilitadas las notificaciones y volver a realizar la prueba. Cuando el usuario decide no aceptar notificaciones de tu App en su móvil, aparecerá desmarcado el check de Push en la lista de Dispositivos y no recibirá notificaciones aunque podrá encontrarlas en el Buzón de notificaciones, siempre que tengas integrada esta funcionalidad en tu App.

[![](https://i.imgur.com/VX9lwPHl.png)](https://i.imgur.com/VX9lwPH.png)


* Problemas de conectividad en el dispositivo, en ocasiones tanto la falta de cobertura como una conexión a una red corporativa pueden ocasionar que las notificaciones no lleguen o lo hagan con cierto retraso.
* La notificación si ha llegado pero ha pasado desapercibida.

En general, siempre que tengamos problemas para determinar por qué una notificación no llega a un dispositivo en concreto, debemos comprobar la actividad de nuestro dispositivo: En la vista de "Dispositivos" podremos encontrar nuestro dispositivo, asociado a nuestro usuario (Alias), debemos percatarnos que esté efectivamente **activo y tenga habilitadas las notificaciones**.

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


## Mensajes de Error

En la siguiente tabla se describen los principales mensajes de error que devuelven las Plataformas de Notificaciones de Google (FCM), Apple (APNS) y Huawei (HMS) y que TwinPush retransmite como respuesta a sus peticiones. Estos mensajes, también se podrían encontrar en los informes descargables en la vista de una Notificación.

| Mensaje | Descripción |
|---------|-------------|
| <strong>NotRegistered</strong><br/>Warning - FCM | Un token de registro existente puede dejar de ser válido en diversas situaciones, como las siguientes:<br>* Si la app cliente deja de estar registrada en FCM.<br>* Si se anula el registro de la app cliente automáticamente, lo cual puede ocurrir si el usuario desinstala la app. Por ejemplo, en iOS, esto sucede si el servicio de comentarios de APNS informó que los tokens de APNS no son válidos.<br>* Si el token de registro caduca (por ejemplo, porque Google decidió actualizar los tokens de registro o porque caducó el token de APNS de un dispositivo con iOS).<br>* Si la app cliente se actualiza, pero la nueva versión no está configurada para recibir mensajes.<br>En todos estos casos, debes quitar este token de registro del servidor de apps y dejar de utilizarlo para enviar mensajes. |
| <strong>Unregistered</strong><br/>Warning - APNS | El token de Dispositivo está inactivo para el entorno especificado. |
| <strong>MismatchSenderId</strong><br/>Error - FCM | Un token de registro está asociado con un determinado grupo de emisores. Cuando una app cliente se registra para FCM, debe especificar qué remitentes tienen autorización para enviar mensajes. Debes utilizar el ID de uno de esos remitentes cuando envíes mensajes a la app cliente. Si cambias a otro diferente, los tokens de registro existentes no funcionarán. |
| <strong>DeviceTokenNotForTopic</strong><br/>Error - APNS | El token del dispositivo no coincide con el entorno especificado. |
| <strong>InvalidPackageName</strong><br/>Error - FCM | Asegúrate de que el mensaje se haya dirigido a un token de registro cuyo nombre de paquete coincida con el valor que se pasa en la solicitud. |
| <strong>InvalidParameters</strong><br/>Error - FCM | Comprueba que los parámetros proporcionados tienen el nombre y el tipo correctos. |
| <strong>InvalidRegistration</strong><br/>Error - FCM | Revisa el formato del token de registro que pasaste al servidor. Asegúrate de que coincida con el token de registro que la app cliente recibe cuando se registra en Firebase Notifications. No lo trunques ni agregues caracteres adicionales. |
| <strong>CERTIFICATE\_EXPIRED</strong><br/>Error - APNS | OPENSSL\_internal:SSLV3\_ALERT\_CERTIFICATE_EXPIRED<br/> El certificado APNS de Apple ha expirado. |
| <strong>BadDeviceToken</strong><br/>Error - APNS | EL token del dispositivo especificado era malo. Compruebe que la petición contenga un token válido y que el token coincida con el entorno. |
| <strong>MissingRegistration</strong><br/>Error - FCM | Verifica que la solicitud contenga un token de registro (en el registration\_id, si es un mensaje de texto sin formato, o en los campos to o registration\_ids en JSON). |
| <strong>80000000</strong><br/>Error - HMS | Éxito. Sin errores. |
| <strong>80100000</strong><br/>Error - HMS | Algunos tokens se enviaron correctamente. Los tokens identificados como token ilegales son aquellos que no se pudieron enviar. Solución: Comprueba estos tokens en el valor de retorno. |
| <strong>80100001</strong><br/>Error - HMS | Algunos parámetros del token son incorrectos. Solución: Comprueba los parámetros del token como se indica en la respuesta. |
| <strong>80100002</strong><br/>Error - HMS | El número de tokens debe ser 1 cuando se envía un mensaje de sincronización. Solución: Comprueba el campo del token en la petición. |
| <strong>80100003</strong><br/>Error - HMS | Estructura de mensaje incorrecta. Solución: Verifica los parámetros en la estructura del mensaje como se indica en la respuesta. |
| <strong>80100004</strong><br/>Error - HMS | El tiempo de expiración del mensaje es anterior a la hora actual. Solución: Verifica el campo de mensaje <strong>ttl.</strong> |
| <strong>80100013</strong><br/>Error - HMS | El campo de mensaje <strong>collapse\_key</strong> es inválido. Solución: Comprueba el campo de mensaje <strong>collapse\_key</strong>. |
| <strong>80100016</strong><br/>Error - HMS | El mensaje contiene información sensible. Solución: Comprueba si el mensaje contiene palabras sensibles. |
| <strong>80200001</strong><br/>Error - HMS | Error de autenticación de OAuth. Solución: No se pudo autenticar el token de acceso del parámetro de autorización del encabezado HTTP de la petición. Asegúrate de que el token de acceso sea el correcto. |
| <strong>80200003</strong><br/>Error - HMS | El token de OAuth expiró. Solución: El token de acceso del parámetro de autorización del encabezado HTTP de la petición expiró. Solicita un nuevo token de acceso. |
| <strong>80300002</strong><br/>Error - HMS | La aplicación actual no tiene permisos para enviar notificaciones push. Solución: Comprueba el permiso de envío de notificaciones push de la presente aplicación. |
| <strong>80300007</strong><br/>Error - HMS | Todos los tokens son inválidos. Solución: Verifica el parámetro del token. |
| <strong>80300008</strong><br/>Error - HMS | El tamaño del cuerpo del mensaje supera el valor por defecto. Solución: Reduce el tamaño del cuerpo del mensaje. |
| <strong>80300010</strong><br/>Error - HMS | El número de tokens en el cuerpo del mensaje supera el valor por defecto. Solución: Reduce el número de tokens y envíalos en lotes. |
| <strong>81000001</strong><br/>Error - HMS | Error interno del sistema. Solución: Comunícate con el soporte técnico de HUAWEI Push Kit. |
