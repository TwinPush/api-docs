Manual de TwinPush
===========================

**TwinPush** es una Plataforma de Marketing Mobile que permite enviar Notificaciones Push a Smartphones. TwinPush ofrece un nuevo Canal de Comunicación Directa entre tu Empresa y tus Usuarios.

Si ya has creado tu Aplicacion Móvil integrando nuestros SDK Android o iOS, pueden empezar en esta sección. Si no lo has hecho todavía, te enseñaremos cómo en nuestra sección Developers.

Regístrate para obtener tu cuenta TwinPush en [app.twinpush.com](https://app.twinpush.com/), crea el espacio de trabajo para tu App, sube tu certificado CGCM de Google o APNS de Apple y empieza a enviar notificaciones Push. Puedes regresar y revisar nuestro Manual de Usuario cuando lo necesites.

¿Problemas? visita nuesta Sección de Preguntas Frecuentes o Contáctanos, estaremos felices de ayudarte con TwinPush.

## Registro e inicio de sesión
Si no tienes una cuenta en TwinPush, puedes registrarte en [app.twinpush.com](https://app.twinpush.com/). Los clientes Enterprise, disponen de un subdominio personalizado para el acceso: [tuempresa.twinpush.com](mailto:info@twincoders.com), contacta con nosotros para obtener tu propio sub-dominio.

Desde esta pantalla podrás:

1. **Registrarte como nuevo usuario** en: Crear una cuenta de TwinPush
2. **Recuperar tu contraseña** en: ¿Has olvidado la contraseña?
3. **Iniciar sesión en TwinPush** con tu usuario y contraseña, si ya te has registrado previamente.


[![](https://i.imgur.com/j1RPtbDl.png)](https://i.imgur.com/j1RPtbD.png)

### Registro
Escribe tu correo electrónico y contraseña. Recuerda que al registrarte estas aceptando las [condiciones de uso](https://app.twinpush.com/res/terms-of-service-es.pdf).

[![](https://i.imgur.com/LWlppqTl.png)](https://i.imgur.com/LWlppqT.png)


### Recuperación de tu Contraseña
Escribe la dirección de correo que usaste para registrarte y en breve tiempo recibirás un correo con instrucciones para restaurar tu contraseña.

[![](https://i.imgur.com/GXDfEmOl.png)](https://i.imgur.com/GXDfEmO.png)

### Introducir OTP

Si tienes activada la autenticación en 2 factores, tendrás que introducir un código de 6 dígitos de un único uso (también llamado OTP) para poder iniciar sesión tras introducir tu contraseña correctamente. La manera de obtener este código depende del método de autenticación escogido (ver [más adelante](#autenticaci-n-en-2-factores)).

![](https://i.imgur.com/8IyiBYH.png)

También tienes la opción de **Recordar este dispositivo** para que no se solicite introducir OTP en el navegador actual durante cierto periodo de tiempo (puede variar según entorno).

En el caso de que hayas extraviado el dispositivo con la app *Authenticator* necesaria para iniciar sesión, deberás ponerte en [contacto con soporte](mailto:support@twincoders.com).

## Mi cuenta

Desde el menú de usuario, pulsando sobre la imagen de perfil en la barra de navegación, se puede acceder a la sección de Mi cuenta.

![](https://i.imgur.com/X5bcAqe.png)

En esta página tendremos las opciones de Editar perfil, consultar el detalle de accesos o gestionar la autenticación en 2 factores.

![](https://i.imgur.com/GuYjJNc.png)

### Editar perfil

Por defecto TwinPush obtendrá tu nombre de usuario en la plataforma a partir de tu email, y la imagen se extraerá del avatar establecido en Gravatar.

Puedes cambiar el nombre de usuario pulsando en "Editar perfil" e introduciendo el nuevo. Tiene un límite de 30 caracteres.

Para cambiar la imagen de perfil, debes acceder a [gravatar.com](http://gravatar.com), una plataforma de terceros que ofrece a través de API imágenes de perfil enlazadas a un email.

### Detalle de accesos

En esta sección puramente informativa podrás revisar información sobre el último login a la plataforma, incluyendo el detalle de la fecha y la IP de origen, así como tu IP actual y el número total de inicios de sesión.

### Autenticación en 2 factores

Desde esta sección tienes la opción de activar la Autenticación en 2 factores para añadir para añadir una capa adicional de protección adicional a tu cuenta de TwinPush. Al activarla se solicitará un código de acceso de un único uso, además de tu contraseña, en cada inicio de sesión.

Dispones de dos opciones para la autenticación en dos factores, según el método para obtener el código de un único uso (también llamado OTP) para el inicio de sesión: recibirlo a través de **email** o generarlo  mediante **App de autenticación**.

#### Email

Utilizando la autenticación de dos factores mediante email, cada vez que quieras iniciar sesión recibirás un código de 6 dígitos a través de correo electrónico. Para activarlo, debes incluir del mismo modo el código OTP recibido por email.

En el caso de no recibir el correo pasados unos minutos, puedes revisar la bandeja de spam, comprueba también que la dirección de email es correcta, que no tienes filtros de entrada en el buzón o algún otro motivo que pueda estar rechazando el mensaje. Para volver a intentar el envío, puedes cerrar la ventana modal y volver a abrirla para realizar el reenvío.

#### App de autenticación

Dispones de la opción es generar un código mediante una app de autenticación en tu teléfono móvil (normalmente conocidas como *Authenticator*). Esto tiene la ventaja de que no requiere acceso al correo electrónico ni conexión a internet en el dispositivo que genera la OTP.

![](https://i.imgur.com/tZOrcpB.png)

Para configurarlo, basta con utilizar instalar una de las aplicaciones compatibles, como por ejemplo [Google Authenticator](https://support.google.com/accounts/answer/1066447?hl=es&co=GENIE.Platform%3DAndroid), [Microsoft Authenticator](https://www.microsoft.com/es-es/security/mobile-authenticator-app) o [Authy](https://authy.com/download/).

Una vez escogida e instalada la app *Authenticator*, deberás escanear el código QR mostrado en pantalla, o introducir manualmente la clave de autenticación. Después, introduce el código generado por la aplicación y pulsa en Activar para confirmar.

Es importante que canceles la autenticación en dos factores si vas a dejar de tener acceso a la aplicación Authenticator actual, ya que podrías perder el acceso a tu cuenta si no.

#### Cancelar autenticación

Puedes eliminar el método de autenticación si quieres reemplazarlo por otro o dejar de utilizarlo. Al desactivarlo se borrará también el registro de dispositivos recordados.

## Aplicaciones

La primera vez que accedes, te pediremos que crees tu primera App, por el momento sólo será necesario el Nombre de tu App y un ícono para tu propia referencia. Más adelante podrás modificar estos parámetros. Al hacer clic en Crear App, estarás creando el espacio de trabajo para tu App.

* **Nombre para tu App**: al crear un nuevo nombre para tu app, intenta describirla tanto como te sea posible, una buena descripción ayudará a que sea facilmente identificable para ti y para tus compañeros. Ejemplo: Clientes Premium Europa Android Production.
* **Icono**: No necesariamente tiene que ser el mismo icono que usarás en el Market sirve para que puedas identificar rápidamente tu app.


[![](https://i.imgur.com/kg02TTel.png)](https://i.imgur.com/kg02TTe.png)



### Tu Primera App
El espacio de trabajo para tu App en TwinPush ya está creado y en la pantalla podrás ver el Dashboard o la Vista general de tu App. A continuación, deberás integrar el SDK de TwinPush en tus aplicaciones móviles y subir tu certificado para empezar a enviar notificaciones. Sigue las instrucciones del [SDK aquí](https://developers.twinpush.com/developers). 


[![](https://i.imgur.com/jRaQHctl.png)](https://i.imgur.com/jRaQHct.png)


### Inicio o Dashboard
La pantalla de Inicio te ofrece una vista general de la evolución de tu App. En ella podrás ver gráficamente cómo se van registrando los Dispositivos en tu App, las Notificaciones que vas enviando, la Actividad que van desarrollando tus Usuarios en tu App y cómo van reaccionando tus Usuarios a tus Notificaciones. Puedes seleccionar el rango de tiempo de visualización arriba a la derecha.

[![](https://i.imgur.com/z2OsIHzl.png)](https://i.imgur.com/z2OsIHz.png)


### Tus Siguientes Apps
Una vez creada tu primera App, podrás añadir más Apps en cualquier momento. Si sólo tienes una App, deberás clicar en sobre el ícono o el nombre de tu primera App que se ubica en la barra superior y se desplegará un menú, elige la opción Todas las aplicaciones, a continuación obtendrás una pantalla con todas tus aplicaciones. Clicando sobre Nueva App podrás añadir más Apps. Si ya tienes más de una App, llegarás a esta pantalla al iniciar sesión. Cuando llegues a tener muchas Apps en tu cuenta dispondrás de una cajita de búsqueda para que puedas acceder rápidamente a cualquiera. Clica sobre una App para entrar en la Vista general de la misma.

[![](https://i.imgur.com/NIiy0lDl.png)](https://i.imgur.com/NIiy0lD.png)


## Notificaciones
### Tu Primera Notificación
Para enviar notificiaciones, deberás acceder al Dashboard o Vista general de tu aplicación, clica sobre Push, en la barra lateral izquierda. Si es la primera vez que envías una notificación con esa aplicación verás una pantalla como la siguiente. Clica en Crear notificación:

[![](https://i.imgur.com/nqQ8oapl.png)](https://i.imgur.com/nqQ8oap.png)


o también sobre Crear nueva notificación arriba a la derecha. 

[![](https://i.imgur.com/EvNVdjxl.png)](https://i.imgur.com/EvNVdjx.png)


Si ya has enviado notificaciones con esa aplicación el botón Push te llevará a la siguiente pantalla. Desde aquí podras ver estadísticas de tus notificaciones enviadas, tus grupos de notificaciones, tus últimas notificaciones, tus campañas, etc. También podras reutilizar grupos, notificaciones o campañas, más adelante te explicaremos cómo. Para crear una nueva notificación desde esta pantalla, clica sobre Crear nueva notificación arriba a la derecha.


[![](https://i.imgur.com/4shkHVTl.png)](https://i.imgur.com/4shkHVT.png)


### Editor de Notificaciones
Al clicar sobre Crear nueva notificación entrarás en el Editor de notificaciones.


El editor de notificaciones se presenta como una serie de pestañas: Push, Contenido, Audiencia, Programación y Avanzado, llevándote por defecto a la primera pestaña, Push. También cuenta con una simulación, en la parte derecha de la pantalla, donde se muestra cómo se verá tu notificación al recibirla desde un dispositivo Android o iOS. 

Para enviar una notificación cualquiera, los campos mínimos que hay que completar son: la Alerta, bajo la pestaña Push, y al menos un Target, el resto de opciones del editor te ayudarán a enriquecer tus notificaciones, a realizar acciones cuando el usuario pulse sobre la notificación, a segmentar tus envíos y a programar la hora y el día en que quieres que se envíen tus notificaciones.


[![](https://i.imgur.com/JDS3z9wl.png)](https://i.imgur.com/JDS3z9w.png)



#### Push 
Utiliza la pestaña Push para componer tu notificación. La notificación en sí se envía en texto plano. Al componer el mensaje ten en cuenta que los smartphones con sistemas operativos no actualizados estan limitados a un tamaño de notificación de alrededor de 250 caracteres, en estos 250 caracteres están incluidos el texto plano de la notificación y el texto enriquecido o la URL, que se introducen en la pestaña *Contenido*.

TwinPush también soporta el envío de emojis tanto en el título del mensaje como en el cuerpo del mensaje, sólo tienes que habilita en tu Ordenador el teclado de emojis y podrás enviarlos.

Si quieres que tus notificaciones llegue correctamente a la mayoría de dispositivos, crea mensajes concisos y utiliza URL's cortas cuando puedas.

* **Título**: Es la primera línea de la notificación que aparecerá resaltada en los dispositivos.
* **Alerta**: Escribe aquí el cuerpo de tu mensaje en texto plano.
* **Buzón**: Marca este checkbox para que la notificación se almacene en el buzón de mensajes del usuario, de esta manera el usuario podrá consultarla cuando quiera.

[![](https://i.imgur.com/frfnqNhl.png)](https://i.imgur.com/frfnqNh.png)


#### Contenido
En Contenido podrás seleccionar qué acción adicional realizará la notificación cuando el usuario la abra, de esta manera, podrás enviar a tus usuarios una pantalla con texto enriquecido o una URL externa, adicional a la notificación. Esta función es muy útil en campañas en dónde la notificación lleva un mensaje que despierta el interés del usuario y que puede derivar en acciones inmediatas.

* **Ninguno**: Selecciona esta opción para que al abrir la notificación resulte en la apertura de tu App, de manera similar que si lo hiciera desde el ícono de tu App.
* **URL**: introduce una URL con una landing page que se abrirá en el smartphone al momento de abrir la notificación enviada.
* **HTML**: Define un mensaje en texto rico HTML, que podrá contener enlaces externos a URL's o imagenes que se presentará al usuario al momento de abrir la notificación.

[![](https://i.imgur.com/IuzlnQMl.png)](https://i.imgur.com/IuzlnQM.png)



#### Audiencia
Utiliza la pestaña Audiencia para seleccionar qué usuarios quieres que reciban esta notificación. Podrás enviar la notificación a todos los usuarios de tu App, a uno o más usuarios o dispositivos seleccionados manualmente, a tus segmentos, o también podrás importar un fichero que contenga una lista de usuarios o dispositivos.

* **Todos**: Seleccionando Todos, la notificación se enviará a todos los usuarios registrados en la plataforma y activos en el momento del envío.
* **Usuario**: Aquí podrás elegir uno o más usuarios o dispositivos escribiéndolos manualmente uno a uno, para ello, identifica a tus usuarios por su Alias, o a los dispositivos por su Device ID. Recuerda que un usuario tiene un Alias, pero puede tener uno o más dispositivos. También podrás seleccionar rapidamente un grupo de Dispositivos 
* **Por propiedad**: de acuerdo a los valores que tienen una determinada *propiedad* y además añadirle filtros por segmento con el fin de extraer una audiencia muy personalizada. Recuerda que las propiedades o "Custom Properties" las defines tu mismo en tu propia App y registras en TwinPush, y que una Propiedad puede ser cualquier información que te interese capturar de tus usuarios, como por ejemplo: edad, género, ocupación, intereses o cualquier otra información

[![](https://i.imgur.com/zY3EeNYl.png)](https://i.imgur.com/zY3EeNY.png)


* **Segmento**: Elige uno o más segmentos que previamente hayas creado en la sección Segmentos, escribe el nombre del segmento uno a uno en el cuadro de texto.
* **Archivo**: Importa un fichero CSV (.cvs) o de texto plano (.txt) con la lista de usuarios o dispositivos. Podrás personalizar el mensaje que enviarás a cada usuario o dispositivo. [Aquí](https://developers.twinpush.com/faq/es#importar-fichero-de-destino) encontrarás las reglas para la creación del fichero.

    * *Filtrar por segmento*: Puedes añadir uno o más filtros por segmento al fichero de usuarios o dispositivos que importes, en ese caso, la notificación se enviará sólo a los usuarios o dispositivos que cumplan las condiciones de los segmentos.

[![](https://i.imgur.com/6iGQc4jl.png)](https://i.imgur.com/6iGQc4j.png)





#### Programación
En Programación eliges cuándo enviar tu notificación, también programar tu envío para que se realice a una hora o día determinados. Twinpush también pone a disposición una potente herramienta para programar campañas de marketing en Crear campaña. En una campaña podrás enviar una notificación, la que podrás repetir el número de veces que indiques, dentro de un periodo establecido. El periodo lo estableces tu mismo seleccionando la fecha de inicio y fin, o el número de días, el rango de horas, y los días de la semana. 

* **Ahora**: La notificación se enviará inmediatamente despues de clicar Enviar que encontrarás al pulsar Guardar y previsualizar.
* **Elegir fecha**: La notificación se enviará en el día y hora establecidos.


[![](https://i.imgur.com/8cIDa1ml.png)](https://i.imgur.com/8cIDa1m.png)

* **Crear campaña**: Se enviará la misma notificación repetida un número de veces dentro del periodo establecido, pudiendo establecer los límites de envíos a un mismo dispositivo en un periodo de tiempo.

Esta configuración permite establecer un periodo de tiempo entre dos fechas donde TwinPush realizará los envíos de manera automática, comprobando los dispositivos que cumplen con las condiciones establecidas.

 * **Fecha de inicio y fin de campaña**: Día que la campaña pasará a estar activa, y por lo tanto TwinPush comprobará periodicamente (máximo cada 30 minutos) qué dispositivos deben ser notificados. Así como el día de fin de campaña.
 * **Horario**: Horario de actividad de la campaña.
 * **Días de la semana**: Permite seleccionar los días de la semana que la campaña debe ser envíada.
 * **Límites**: Se deben establecer los límites de envíos por cada dispositivo. Número de envíos totales, frecuencia mínima y el tiempo mínimo entre dos notificaciones a un mismo dispositivo.


[![](https://i.imgur.com/yE7QKjAl.png)](https://i.imgur.com/yE7QKjA.png)


#### Avanzado
En Avanzado, podemos establecer la velocidad de envío de la notificación y también interactuar con la aplicación residente en el smartphone.
Podrás asociar esta notificación a un determinado grupo, de esta manera podrás agrupar tus notificaciones por campañas, periodos, productos, clientes objetivo o lo que tu quieras.

La velocidad de envío es útil cuando se quiere enviar una notificación que conlleve a una acción en enlaces externos a un número elevado de usuarios. Es posible que el pico de tráfico generado por ese gran número de usuarios en ese instante repercuta en la disponibilidad de los servicios de los enlaces externos, perjudicando la experiencia del usuario. TwinPush nos permite distribuir en el tiempo el envío de una misma notificación a un gran número de usuarios. 

Podremos interactuar con la App residente en el Smartphone del usuario, pudiendo alterar el número de Badge de la App, (el badge es el número que aparece en el ícono de la App), el tono musical que sonará al recibir la notificación o la etiqueta que identifica en la App el tipo de notificación recibida, pudiendo configurar en la Aplicaciones acciones concretas según el Tag recibido.

* **Nombre**: Pon el nombre que quieras darle, para uso interno, para que puedas identificar tus propias campañas más facilmente.
* **Grupo de notificaciones**: Añade esta notificación a un grupo existente o a un nuevo grupo, escribe el nombre del grupo aquí.
* **Velocidad de envío**: Elige la velocidad en que se distribuirá la notificación a tus usuarios.
* **Badge**: Escribe el badge que aparecerá en el Smartphone, por defecto +1 al número que ya tenga el ícono.
* **Sonido**: Elige el tono musical que sonará al recibir la notificación, en el caso que tu App disponga de varios sonidos.
* **Tags**: Envía al Smartphone el tipo de notificación que estas enviando, en el caso que tu App disponga de diferentes tipos.
* **Propiedades personalizadas**: Las propiedades añadidas a las notificaciones permiten enviar información (clave/valor) a la aplicación que puede ser interpretada para realizar ciertas acciones, como dirigir al usuario a una sección en concreto de la Aplicación o mostrar contenido o funcionalidades específicas.


[![](https://i.imgur.com/gCMX9JDl.png)](https://i.imgur.com/gCMX9JD.png)



* **Ajustes avanzados de iOS**: A partir de iOS 10 es posible enviar adjuntos en la propia notificación para mostrar al usuario imágenes, videos, audios... Que se mostrarán sin necesidad de abrir la Aplicación

[![](https://camo.githubusercontent.com/ffe9d4528c9e8a2d3bf35294b6e9fb731077bfcb/687474703a2f2f692e696d6775722e636f6d2f66526b55716b482e676966)](https://camo.githubusercontent.com/ffe9d4528c9e8a2d3bf35294b6e9fb731077bfcb/687474703a2f2f692e696d6775722e636f6d2f66526b55716b482e676966)


### Guardar y Previsualizar

Una vez hayas completado tu notificación, podrás salvarla y enviarla clicando sobre Guardar y previsualizar abajo a la derecha. TwinPush guardará tu notificación configurada y te mostrará una pantalla resumen. Comprueba que tu notificación este correcta y envíala con el boton Enviar. Si no lo está, podrás editarla con Edit, o borrarla con Delete. El botón Duplicate te será de gran utilidad para reutilizar notificaciones o para crear tus propias plantillas sobre las cuales puedas hacer variaciones sobre un duplicado de una plantilla original.


[![](https://i.imgur.com/CEWk6mol.png)](https://i.imgur.com/CEWk6mo.png)

_Atención_: sólo en el caso que hayas seleccionado a "Todos" en tu audiencia, antes de enviar la Notificación TwinPush solicitará tu confirmación, una vez confirmes la notificación se enviará:

[![](https://i.imgur.com/zp8r3t0l.png)](https://i.imgur.com/zp8r3t0.png)

### Detalle de Campaña Enviada
Al clicar sobre una de las campañas podremos ver toda la información relativa al envío.

Estadísticos de la campaña

* **Dispositivos Alcanzados**: Número de dispositivos objetivo de la campaña.
* **Total de envíos Push**: Número de dispostiivos a los que se le ha realizado un envío de notificación Push.
* **Ratio de Apertura**: % de dispositivos que ha abierto la notificación desde la pantalla principal del teléfono o desde el centro de notificación.
* **Impacto en la Retención**: % de mejora en la retención de la Aplicación ( usuarios que han accedido a la Aplicación en ese momento) comparado conla media de accesos de usuarios en los últimos 30 días previos al envío.
* **Descarga de CSV con resultados de la campaña**: Generación y descarga de un fichero CSV con los resultados de los envío, usuarios impactados, sus datos y las aperturas recibidas.

[![](https://i.imgur.com/1WZ3vKLl.png)](https://i.imgur.com/1WZ3vKL.png)



## Segmentos
TwinPush incluye una potente herramienta para segmentar a los usuarios de tu App. Con esta herramienta podrás crear segmentos de usuarios según su ubicación, según las características de su dispositivo como marca, modelo o versión de su sistema, según el perfil de uso de tu aplicación o la información del usuario como su idioma u otra información que tu aplicación haya obtenido del usuario y la haya registrado en la plataforma a través de los "Custom Properties", como por ejemplo: edad, género, ocupación, intereses o cualquier otra información. 



### Tu Primer Segmento
Para crear segmentos, accede al Dashboard o Vista general de tu aplicación y clica sobre Segmentos en la barra lateral izquierda. Si es la primera vez que crear un segmento en esa aplicación, verás una pantalla como la siguiente. 

[![](https://i.imgur.com/DoqbGUil.png)](https://i.imgur.com/DoqbGUi.png)

O también clica en Crear nuevo segmento arriba a la derecha.

[![](https://i.imgur.com/TkkJ3kfl.png)](https://i.imgur.com/TkkJ3kf.png)



Si ya tienes segmentos creados en tu aplicación verás la siguiente pantalla. Desde aquí obtendrás una rápida vista de todos tus segmentos, donde se muestra para cada uno de ellos, el número de dispositivos, el porcentaje de dispositivos objetivo del segmento (barra verde) sobre el universo de dispositivos totales (barra gris de fondo) y el tipo de filtrado del segmento: por posición, por propiedades del dispositivo o por estadísticas de uso. Para crear un nuevo segmento desde esta pantalla, clica sobre Crear nuevo segmento arriba a la derecha.

[![](https://i.imgur.com/mzb26tDl.png)](https://i.imgur.com/mzb26tD.png)


### Editor de Segmentos
Al clicar sobre Crear nuevo segmento entrarás en el Editor de Segmentos. El editor te llevará por defecto al filtro por Ubicación. El editor de segmentos se presenta como una lista de filtros sobre el margen izquierdo de la pantalla, que podrás ir añadiendo al segmento creado. Los filtros son de tres tipos: por Ubicación, por Datos de Usuario o por Datos del Dispositivo. En el centro de la pantalla encontrarás las opciones de configuración del filtro seleccionado. Sobre la derecha de la pantalla podrás añadir una condición a todos los filtros seleccionados y dar un nombre al segmento recién creado. 
Cada filtro que vas añadiendo al segmento se verá representado a través de un pequeño índice en su correspondiente sección. Este índice indica la cantidad total de filtros totales de esa sección. Así por ejemplo, si añades 2 idiomas distintos, el sub índice en la sección de idiomas será 2, y si añades 3 ciudades, el sub índice en ciudades será 3.

[![](https://i.imgur.com/P1wCBq5l.png)](https://i.imgur.com/P1wCBq5.png)

#### Filtros por Ubicación
TwinPush ofrece diferentes maneras de filtrar un grupo de usuarios de acuerdo a su ubicación: puedes crear uno o más geocercos, especificar uno o más países, estados, regiones, o ciudades, para ello clica sobre Coordenadas, País, Estado, Región o Ciudad.  

[![](https://i.imgur.com/naXogjpl.png)](https://i.imgur.com/naXogjp.png)



##### Creación de Geocercos
Los geocercos no son más que una superficie circular determinada por una coordenada que identifica el centro del círculo y un radio especificado en metros. Para crear un nuevo geocerco, clica sobre Coordenadas a la izquierda para seleccionar este tipo de filtro y luego sobre Añadir, en la parte superior derecha del mapa. En la pantalla te aparecerá un mapa como muestra la siguiente imagen. En esta pantalla deberás ubicar el marcador o POI en la posición deseada y elegir un radio con la barra deslizante de la parte inferior.  La región seleccionada aparecerá sombreada en el mapa. En la parte superior hay un cuadro de búsqueda, en él puedes escribir el nombre de la ciudad que te interesa, también podrás navegar sobre el mapa con el ratón. Una vez establecida la región de interés sobre el mapa, clica sobre Añadir abajo a la derecha.

[![](https://i.imgur.com/6CgZDVJl.png)](https://i.imgur.com/6CgZDVJ.png)


#### Filtros por Datos de Usuario
En esta sección podrás segmentar a tus usuarios de acuerdo a la información que tu aplicación haya obtenido del usuario. Para ello tu aplicación deberá registrar esta información en la plataforma Twinpush a través de los "Custom Properties", puedes ver cómo hacerlo en el manual descrito [aquí](https://developers.twinpush.com/developers/api?class=sidebar-header#post-set-custom-property). Por defecto Twinpush te ofrece información del idioma de tus usuarios.

[![](https://i.imgur.com/OduTrRwl.png)](https://i.imgur.com/OduTrRw.png)



Con los "Custom Properties" podrás segmentar a tus usuarios por: edad, género, ocupación, intereses o cualquier otra información que quieras personalizar. Para añadir un filtro, clica sobre Otras propiedades, y luego sobre Añadir arriba a la derecha, te aparecerá una pantalla como la siguiente. En ella podrás añadir un filtro sobre cualquiera de las propiedades que encontrarás en un menu desplegable.

[![](https://i.imgur.com/63WxCwNl.png)](https://i.imgur.com/63WxCwN.png)



#### Filtros por Datos del Dispositivo
TwinPush pone a tu disposición la información obtenida del dispositivo con el cual el usuario accede a tu aplicación. Información como: Plataforma (iOS o Android), Fabricante, Modelo, Versión del sistema, Version de tu App, etc. Podrás segmentar a tus usuarios añadiendo un filtro sobre dicha información.

[![](https://i.imgur.com/ywmGskIl.png)](https://i.imgur.com/ywmGskI.png)




##### Estadísticas de uso de tu App
TwinPush también te permite segmentar a tus usuarios según el tiempo que usan tu App. Con esta funcionalidad podrás crear campañas que incentiven el uso de tu App, pudiendo premiar a tus usuarios con ofertas exclusivas para ese segmento. Para añadir un filtro de uso de tu App, clica sobre Estadísticas de uso, y luego sobre Añadir, arriba a la dechecha, a continuación verás una pantalla como la siguiente. Podrás añadir un filtro sobre: el tiempo total de uso, el periodo de inactividad, el tiempo medio de uso diario o el tiempo transcurrido desde la instalación.

[![](https://i.imgur.com/syT86bBl.png)](https://i.imgur.com/syT86bB.png)

#### Segmentos a usuarios con valores NO coincidentes
TwinPush ofrece la posibilidad de crear condiciones destinadas a envíos de usuarios que NO cumplan ciertas condiciones.
Para establecerlo, basta con selecionar la propiedad y asignarle el valor negativo.

[![](https://i.imgur.com/wik5yH6l.png)](https://i.imgur.com/wik5yH6.png)


#### Resumen
Una vez establecidos tus filtros, podrás añadir una condición a todos ellos en la sección Resumen, a la derecha de la pantalla. Recuerda que cada filtro creado se mostrará con un sub indice en su sección. Selecciona entre "Cualquiera" o "Todas" en el menú desplegable.

* **cualquiera**: tu segmento incluirá a los usuarios que cumplan cualquiera de los filtros, por ejemplo: si has creado dos filtros por ubicación, uno en Madrid y otro en Barcelona, al seleccionar *cualquiera*, tu segmento incluirá a los usuarios con dispositivos ubicados en Madrid o en Barcelona, es decir, en ambas ubicaciones. La opción *cualquiera*, abre más tu segmento.
* **todas**: tu segmento incluirá a los usuarios que cumplan todos los filtros a la vez, por ejemplo has creado un filtro por ubicación en Madrid y otro filtro por plataforma iOS, al seleccionar *todas*, tu segmento incluirá a todos los usuario de iOS y a la vez ubicados en Madrid. La opción *todas* restringe más tu segmento.

Finalmente, dale un nombre a tu segmento y guárdalo clicando Crear Segmento.

[![](https://i.imgur.com/1b4AEHal.png)](https://i.imgur.com/1b4AEHa.png)



## Dispositivos

En la vista de "Dispositivos", TwinPush permite la consulta de toda nuestra base de Usuarios y sus datos. 


La vista muestra los dispositivos con actividad más reciente registrada, así como un buscador por Alias para realizar una busqueda de un usuario en concreto. En tabla principal mostramos la información más relevante sobre el dispositivo:

* **Push**: Este campo mostrará un check cuando el usuario haya aprobado recibir notificaciones Push en su dispositivo.
* **Activo**: Este campo mostrará un check cuando el usuario sea activo (Haya registrado actividad al menos una vez en los últimos 6 meses).
* **Alias**: Muestra el alias asociado al dispositivo.
* **Plataforma**: Mostrará un icono de el sistema Operativo, iOS o Android, así como la versión del mismo.
* **Device ID**: Identificador interno del dispositivo en TwinPush.
* **Fecha de Registro**: Fecha de primer registro del dispositivo.
* **Fecha de última apertura**: Fecha de ultima apertura de la Aplicación.

[![](https://i.imgur.com/1q0oBlJl.png)](https://i.imgur.com/1q0oBlJ.png)


Al clicar sobre cualquiera de los dispositivos se mostrará un modal con toda la información relativa a este dispositivo, además de la información general, se mostrará:

#### Información del Dispositivo:
* Fabricante
* Modelo
* Código de dispositivo:
* Versión del Sistema Operativo
* Versión de la App
* Versión del SDK

Un botón permitirá ver las notficaciones enviadas y recibidas por el Dispositivo.

##### Notificaciones Recibidas:
Al clicar sobre el botón Ver notificaciones recibidas, la vista cargará nuevamente la información del dispositivo y también todas las notificaciones enviadas al mismo. Para cada notificación, padrás ver la siguiente información:

* Tipo: Simple o Rica
* Nombre / Mensaje: título de la notificación
* Creación: fecha y hora de creación
* Envío push: fecha y hora de envío
* Confirmación: fecha y hora de confirmación de recepción de Push
* Apertura: fecha y hora en la que el usuario la abrió
* Buzón: si se guardó o no en el buzón del usuario

[![](https://i.imgur.com/86Olyd2l.png)](https://i.imgur.com/86Olyd2.png)


#### Información de Localización:
Siempre que se haya realizado una [integración del SDK](https://developers.twinpush.com/developers) con la geolocalización activa de dispositivos, TwinPush mostrará información relativa a la ubicación del mismo.

* País
* Estado
* Ciudad

#### Datos de Usuario (Custom Properties):
El [SDK](https://developers.twinpush.com/developers) permite el registro de propiedades de usuario en TwinPush que también se mostrarán en la vista de Dispositivos.

[![](https://i.imgur.com/YGhcmOpl.png)](https://i.imgur.com/YGhcmOp.png)


### Exportación:
TwinPush permite la Descarga de toda nuestra base de usuarios mediante la Exportación de un fichero CSV que contiene toda la información de cada uno de los registros de dispositivos.

Al tratarse de una tarea "pesada" TwinPush ofrece la posibilidad de descargarse siempre el último fichero generado así como lanzar el proceso de nuevo para actualizar el fichero.

[![](https://i.imgur.com/D3bhOful.png)](https://i.imgur.com/D3bhOfu.png)



## Ajustes

En la pestaña de Ajustes tendremos acceso a los parámetros de configuración de nuestra Aplicación, las claves de autenticación para la integración o la gestión de equipo.

### Detalle de Aplicación:
Podremos modificar los datos principales de nuestra Aplicación, tales como:

[![](https://i.imgur.com/z9lhwvwl.png)](https://i.imgur.com/z9lhwvw.png)

* **Nombre**: Nombre de la Aplicación que se muestra en TwinPush.

* **Zona horaria**: Modificar la zona horaria por defecto de nuestra aplicación, esto influirá en el envío de notificaciones y la programación horaria de las campañas, aun así, en cada campaña podremos definir una zona horaria única para esta campaña.

* **Icono**: Subir imagen con el icono que identificará nuestra Aplicación en TwinPush.

* **Badge number**: Este parámetro configura el número que aparece encima del icono de nuestra aplicación en los dispositivos iOS. Siendo por defecto +1.

* **Valores por defecto**:
    * Incluir por defecto las notificaciones nuevas en el buzón de usuario: esta casilla habilita el uso por defecto del buzón, almacenando todas las notificaciones nuevas en cada buzón de usuario.
    * Notificaciones con "contenido mutable" activado por defecto: marcando esta casilla se habilitará el uso de contenido mutable en notificaciones a dispositivos iOS, siempre que se haya desarrollado una apropiada integración con TwinPush.

* **Velocidad máxima de envío**: Aquí puedes ajustar la velocidad máxima de envío de notificaciones. Este parámetro afectará al menú desplegable de velocidad de envío en la configuración avanzada de Notificaciones:
    * Inmediata: no hay restricciones en la velocidad de envío.
    * Rápida: velocidad de envío limitada a 100.000 por minuto.
    * Normal: velocidad de envío limitada a 10.000 por minuto.
    * Lenta: Velocidad de envío limitada a 1.000 por minuto. 

* **Permitir envíos broadcast**: Los envíos broadcast permiten realizar un envío masivo a todos los dispositivos de tu App con una sola Notificación. Este parámetro permite restringir esta función según tus necesidades:
    * Desde API y consola web: se permite crear y enviar notificaciones broadcast tanto desde el API como desde la consola web.
    * Solo desde API: se permite crear y enviar notificaciones broadcast solamente desde el API y no será posible desde la consola web.
    * Solo desde consola web: se permite crear y enviar notificaciones broadcast solamente desde la consola web y no será posible hacerlo desde el API.
    * No permitir: no se permite crear ni enviar notificaciones de este tipo.

* **IPs de acceso a la consola permitidas**: Indica aquí la **lista blanca de direcciones IPs públicas** que podrán acceder a la Consola Web de TwinPush. Escribe cada dirección IP, y seguidamente pulsa la tecla Intro antes de escribir la siguiente IP. Borra una IP configurada pulsando sobre la X a la izquierda. Podrás utilizar notación CIDR para rangos de subredes. TwinPush siempre te va a sugerir tu propia dirección IP actual y también las direcciones IP's que hayas configurado en otras APPs de tu cuenta de TwinPush. Cuando hayas completado la lista blanca, pulsa sobre el botón Actualizar.

[![](https://i.imgur.com/IMRAF2Cl.png)](https://i.imgur.com/IMRAF2C.png)


**Importante:** Las direcciones IPs de la lista deben ser las IPs públicas o externas, no se utilizan IPs privadas o de red interna.
Si tu propia IP es dinámica, lo cual ocurre en la mayoría de los casos, asegúrate de incluir el rango de IPs públicas que utiliza tu organización.


### Claves de Autenticación:

En esta vista también podremos consultar nuestras claves de autenticación con el servidor, necesarias para la integración del [SDK de TwinPush](https://developers.twinpush.com/developers) en las aplicaciones.

* **Subdominio**: Mostrará el subdominio que debemos configurar en la integración del SDK, customizado en el caso de clientes Enterprise.
* **Application ID**: Identificador de Aplicación de TwinPush.
* **API Key**: Parámetro de autenticación para la Aplicación y su conexión con el servidor de TwinPush.
* **API Key Creator**: Parámetro de autenticación para la creación y envío de notificaciones desde otro servidor.


[![](https://i.imgur.com/cANApZkl.png)](https://i.imgur.com/cANApZk.png)



### Gestión de Equipo:
TwinPush permite la gestión de las personas que tendrán acceso a tu aplicación. La invitación se realiza introduciendo el email de la persona a la que deseemos dar acceso y TwinPush se encargará de enviar un email al invitado indicándole los pasos a seguir para acceder a la aplicación.

[![](https://i.imgur.com/9JLxmO3l.png)](https://i.imgur.com/9JLxmO3.png)


#### Roles de usuario
Hay cuatro roles de usuarios que el propietario o los administradores de la cuenta puede elegir para cada miembro de su equipo: Invitado, Redactor, Usuario o Administrador.


**Invitado**: los usuarios invitados tienen acceso a:

* Al Dashboard de inicio.
* Listado de dispositivos registrados.
* Listado de las notificaciones push.

**Redactor**: los usuario redactores, además tienen acceso a:

* Gestión de segmentos, pueden crear y editar los segmentos existentes.
* Creación de notificaciones push, pueden crear o editar notificaciones y pueden crear o editar campañas, no obstante no podrán ni enviar las notificaciones ni activar campañas.

**Usuario**:  los usuarios con el rol de usuario, además pueden:

* Envío de notificaciones push, pueden enviar notificaciones y activar campañas.

**Administrador**:  los usuarios administradores tienen el control total de la aplicación y pueden además acceder a:

* Visualizar contenido protegido
* Ajustes de aplicación, incluyendo la consulta de API Keys y configuración de FCM, HMS o APNS.
* Claves de autenticación, para autenticar el acceso de la App móvil (SDK) y el API de TwinPush.
* Gestión del equipo, pueden invitar nuevos usuarios, editar roles de usuarios existentes y revocar accesos de otros usuarios.

[![](https://i.imgur.com/OlK5Z19l.png)](https://i.imgur.com/OlK5Z19.png)


### Servicios de Notificaciones:

Esta sección de configuración de servicios Push permite gestionar los tokens de acceso y certificados necesarios para enviar notificaciones a través de los servicios de Apple, Google y Huawei. Es crucial completar y mantener actualizada esta configuración, ya que de no hacerlo, el envío de notificaciones puede fallar, afectando la comunicación con los usuarios finales.

#### Estado

El estado ayuda a visualizar rápidamente los servicios que ya han sido configurados o si alguno de los servicios requiere atención.

[![](https://i.imgur.com/kfOyD8hl.png)](https://i.imgur.com/kfOyD8h.png)


* **Configurado**: Indica que se ha completado la configuración del servicio. Es importante destacar que TwinPush no realiza ninguna validación de los datos introducidos, por lo tanto, el estado "Configurado" no garantiza que los datos sean correctos.

* **Advertencia**: Indica que la configuración ingresada requiere atención. Esto puede deberse a que el certificado .p12 del Servicio APNS de Apple está dentro de los 30 días de su fecha de expiración o a que actualmente se está utilizando la API FCM Heredada (legacy) de Google la cual ya ha sido declarado obsoleta.

* **No configurado**: Indica que no se han introducido datos para la configuración del servicio.

**Nota 1**: Solo los usuarios con el rol de Administrador podrán editar la configuración de los servicios.


**Nota 2**: Ahora, los iconos de Apple, Android y Huawei mostrados en cada App en la vista de **Aplicaciones** indican que esos son servicios de Notificaciones han sido configurados para dicha App.


[![](https://i.imgur.com/zHiiKn8l.png)](https://i.imgur.com/zHiiKn8.png)



#### Configuración FCM, HMS y APNS

Para poder enviar notificaciones Push a través de TwinPush, es necesario configurar los Certificados o Claves de acceso necesarios de los servicios [APNs de Apple](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html), [FCM de Google](https://firebase.google.com/docs/cloud-messaging/) y [HMS Servicios Móviles de Huawei](https://developer.huawei.com/consumer/en/hms/). Estos Certificados o Claves deberán ser proporcionados por el equipo de desarrollo de la Aplicación. más información en la [documentación de integración del SDK](https://developers.twinpush.com/developers). 

#### Apple Push Notification Service (APNs)

TwinPush ofrece dos manera de autenticación contra los servicios de Apple: autenticación basada en token (.p8) o por certificado .p12. Selecciona el método de autenticación en el menú desplegable. [Ver la documentación de APNs](https://developer.apple.com/documentation/usernotifications/registering-your-app-with-apns)

[![](https://i.imgur.com/m8DD9c5l.png)](https://i.imgur.com/m8DD9c5.png)



* **Autenticación por certificado .p12**: Sube el fichero del certificado e introduce la contraseña correspondiente y el ID de Paquete de la aplicación. Por último, debemos tener en cuenta de marcar la casilla "aplicación tiene certificado de distribución" sólo si hemos compilando una version de "Producción" dirigida al Store.

[![](https://i.imgur.com/V0sYXzxl.png)](https://i.imgur.com/V0sYXzx.png)


**Nota**: Ten en cuenta que el certificado .p12 debe renovarse anualmente. TwinPush mantiene un control sobre la fecha de caducidad de tu certificado APNS, mostrando una alerta cuando reste poco tiempo para su caducidad, evitando errores de certificado no válido, que provocaría errores de envío a dispositivos iOS. Ten en cuenta que TwinPush no te enviará ningún correo electrónico cuando tu certificado esté a punto de caducar.



* **Autenticación basada en token**: Sube el fichero de la clave de autenticación Token (fichero .p8), e introduce el ID de la clave de autenticación, el ID de equipo y el ID del paquete. Finalmente, marca la casilla "aplicación tiene certificado de distribución" sólo si estamos compilando una version de "Producción" dirigida al Store.

[![](https://i.imgur.com/iTPEEUbl.png)](https://i.imgur.com/iTPEEUb.png)


**Nota**: la clave de autenticación por Token .p8, no tiene caducidad.


#### Firebase Cloud Messaging (FCM)

TwinPush gestiona dos métodos para acceder a los servicios de mensajería de Google Firebase Cloud Messaging (FCM) el primero, por API Key llamado "Heredada" (Legacy) o el segundo por fichero JSON llamado "HTTP v1". Selecciona el método en el menú desplegable.

[![](https://i.imgur.com/YKTflurl.png)](https://i.imgur.com/YKTflur.png)


* **API Key "Heredada"**: sólo hay que pegar el API Key y el nombre del Paquete en las casillas correspondientes y darle al botón "Actualizar". 

[![](https://i.imgur.com/UQtso1Tl.png)](https://i.imgur.com/UQtso1T.png)


**Importante**: Los usuarios de API Key heredada deberán migrar al método "HTTP v1" antes del 20 de Junio de 2024.


* **HTTP v1**: Sólo sube el fichero JSON con la clave privada de la cuenta de servicio de la [consola de Firebase](https://console.firebase.google.com/) y pulsa el botón "Actualizar".

[![](https://i.imgur.com/T2YgqgVl.png)](https://i.imgur.com/T2YgqgV.png)


**Importante**: Comprobar que la API de Firebase Cloud Messaging (V1) esté habilitada en el Proyecto.

[![](https://i.imgur.com/cvkZqcsl.png)](https://i.imgur.com/cvkZqcs.png)



#### Huawei Mobile Services (HMS)


Para enviar notificaciones Push usando los servicios móviles de Huawei (HMS), será necesario obtener en la [consola AppGallery Connect](https://developer.huawei.com/consumer/en/console#/serviceCards/) de Huawei, en la sección Credenciales, el **Identificador cliente Huawei** así como la **Clave cliente Huawei** del proyecto y pegarlos en las casillas correspondientes y pulsar el botón "Actualizar".

[![](https://i.imgur.com/ufchj7El.png)](https://i.imgur.com/ufchj7E.png)

