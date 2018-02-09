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


[![](http://i.imgur.com/qzhBZ9Bl.png)](http://i.imgur.com/qzhBZ9B.png)


### Registro
Escribe tu correo electrónico y contraseña. Recuerda que al registrarte estas aceptando las [condiciones de uso](http://app.twinpush.com/res/terms-of-service-es.pdf).


[![](http://i.imgur.com/bTWYU92l.png)](http://i.imgur.com/bTWYU92.png)



### Recuperación de tu Contraseña
Escribe la dirección de correo que usaste para registrarte y en breve tiempo recibirás un correo con instrucciones para restaurar tu contraseña.


[![](http://i.imgur.com/oBKal8el.png)](http://i.imgur.com/oBKal8e.png)




## Aplicaciones
La primera vez que accedes, te pediremos que crees tu primera App, por el momento sólo será necesario el Nombre de tu App y un ícono para tu propia referencia. Más adelante podrás modificar estos parámetros. Al hacer clic en Crear App, estarás creando el espacio de trabajo para tu App.

* **Nombre para tu App**: al crear un nuevo nombre para tu app, intenta describirla tanto como te sea posible, una buena descripción ayudará a que sea facilmente identificable para ti y para tus compañeros. Ejemplo: Clientes Premium Europa Android Production.
* **Icono**: No necesariamente tiene que ser el mismo icono que usarás en el Market sirve para que puedas identificar rápidamente tu app.


[![](http://i.imgur.com/kg02TTel.png)](http://i.imgur.com/kg02TTe.png)



### Tu Primera App
El espacio de trabajo para tu App en TwinPush ya está creado y en la pantalla podrás ver el Dashboard o la Vista general de tu App. A continuación, deberás integrar el SDK de TwinPush en tus aplicaciones móviles y subir tu certificado para empezar a enviar notificaciones. Sigue las instrucciones del [SDK aquí](http://www.twinpush.com/quickstart). 


[![](http://i.imgur.com/CMETNINl.png)](http://i.imgur.com/CMETNIN.png)




### Tus Siguientes Apps
Una vez creada tu primera App, podrás añadir más Apps en cualquier momento. Si sólo tienes una App, deberás clicar en sobre el ícono o el nombre de tu primera App que se ubica en la barra superior y se desplegará un menú, elige la opción Todas las aplicaciones, a continuación obtendrás una pantalla con todas tus aplicaciones. Clicando sobre Nueva App podrás añadir más Apps. Si ya tienes más de una App, llegarás a esta pantalla al iniciar sesión. Clica sobre una App para entrar en la Vista general de la misma.

[![](http://i.imgur.com/NIiy0lDl.png)](http://i.imgur.com/NIiy0lD.png)




## Notificaciones
### Tu Primera Notificación
Para enviar notificiaciones, deberás acceder al Dashboard o Vista general de tu aplicación, clica sobre Push, en la barra lateral izquierda. Si es la primera vez que envías una notificación con esa aplicación verás una pantalla como la siguiente. Clica en Crear notificación:

[![](http://i.imgur.com/nqQ8oapl.png)](http://i.imgur.com/nqQ8oap.png)


o también sobre Crear nueva notificación arriba a la derecha. 

[![](http://i.imgur.com/EvNVdjxl.png)](http://i.imgur.com/EvNVdjx.png)


Si ya has enviado notificaciones con esa aplicación el botón Push te llevará a la siguiente pantalla. Desde aquí podras ver estadísticas de tus notificaciones enviadas, tus grupos de notificaciones, tus últimas notificaciones, tus campañas, etc. También podras reutilizar grupos, notificaciones o campañas, más adelante te explicaremos cómo. Para crear una nueva notificación desde esta pantalla, clica sobre Crear nueva notificación arriba a la derecha.


[![](http://i.imgur.com/UADyhoCl.png)](http://i.imgur.com/UADyhoC.png)


### Editor de Notificaciones
Al clicar sobre Crear nueva notificación entrarás en el Editor de notificaciones.


El editor de notificaciones se presenta como una serie de pestañas: Push, Contenido, Audiencia, Programación y Avanzado, llevándote por defecto a la primera pestaña, Push. También cuenta con una simulación, en la parte derecha de la pantalla, donde se muestra cómo se verá tu notificación al recibirla desde un dispositivo Android o iOS. 

Para enviar una notificación cualquiera, los campos mínimos que hay que completar son: la Alerta, bajo la pestaña Push, y al menos un Target, el resto de opciones del editor te ayudarán a enriquecer tus notificaciones, a realizar acciones cuando el usuario pulse sobre la notificación, a segmentar tus envíos y a programar la hora y el día en que quieres que se envíen tus notificaciones.


[![](http://i.imgur.com/M7bDRCAl.png)](http://i.imgur.com/M7bDRCA.png)



#### Push 
Utiliza la pestaña Push para componer tu notificación. La notificación en sí se envía en texto plano. Al componer el mensaje ten en cuenta que los smartphones con sistemas operativos no actualizados estan limitados a un tamaño de notificación de alrededor de 250 caracteres, en estos 250 caracteres están incluidos el texto plano de la notificación y el texto enriquecido o la URL, que se introducen en la pestaña *Content*.

Si quieres que tus notificaciones llegue correctamente a la mayoría de dispositivos, crea mensajes concisos y utiliza URL's cortas cuando puedas.

* **Título**: Es la primera línea de la notificación que aparecerá resaltada en los dispositivos.
* **Alerta**: Escribe aquí el cuerpo de tu mensaje en texto plano.
* **Buzón**: Marca este checkbox para que la notificación se almacene en el buzón de mensajes del usuario, de esta manera el usuario podrá consultarla cuando quiera.


[![](http://i.imgur.com/frfnqNhl.png)](http://i.imgur.com/frfnqNh.png)


#### Contenido
En Contenido podrás seleccionar qué acción adicional realizará la notificación cuando el usuario la abra, de esta manera, podrás enviar a tus usuarios una pantalla con texto enriquecido o una URL externa, adicional a la notificación. Esta función es muy útil en campañas en dónde la notificación lleva un mensaje que despierta el interés del usuario y que puede derivar en acciones inmediatas.

* **Ninguno**: Selecciona esta opción para que al abrir la notificación resulte en la apertura de tu App, de manera similar que si lo hiciera desde el ícono de tu App.
* **URL**: introduce una URL con una landing page que se abrirá en el smartphone al momento de abrir la notificación enviada.
* **HTML**: Define un mensaje en texto rico HTML, que podrá contener enlaces externos a URL's o imagenes que se presentará al usuario al momento de abrir la notificación.

[![](http://i.imgur.com/IuzlnQMl.png)](http://i.imgur.com/IuzlnQM.png)



#### Audiencia
Utiliza la pestaña Audiencia para seleccionar qué usuarios quieres que reciban esta notificación. Podrás enviar la notificación a todos los usuarios de tu App, a uno o más usuarios o dispositivos seleccionados manualmente, a tus segmentos, o también podrás importar un fichero que contenga una lista de usuarios o dispositivos.

* **Todos**: Seleccionando Todos, la notificación se enviará a todos los usuarios registrados en la plataforma y activos en el momento del envío.
* **Usuario**: Aquí podrás elegir uno o más usuarios o dispositivos escribiéndolos manualmente uno a uno, para ello, identifica a tus usuarios por su Alias, o a los dispositivos por su Device ID. Recuerda que un usuario tiene un Alias, pero puede tener uno o más dispositivos. 
* **Segmento**: Elige uno o más segmentos que previamente hayas creado en la sección Segmentos, escribe el nombre del segmento uno a uno en el cuadro de texto.
* **Archivo**: Importa un fichero CSV (.cvs) o de texto plano (.txt) con la lista de usuarios o dispositivos. Podrás personalizar el mensaje que enviarás a cada usuario o dispositivo. [Aquí](https://twincoders.atlassian.net/wiki/x/AgC7AQ) encontrarás las reglas para la creación del fichero.


[![](http://i.imgur.com/TMrf4aTl.png)](http://i.imgur.com/TMrf4aT.png)
    * *Filtrar por segmento*: Puedes añadir uno o más filtros por segmento al fichero de usuarios o dispositivos que importes, en ese caso, la notificación se enviará sólo a los usuarios o dispositivos que cumplan las condiciones de los segmentos.

[![](http://i.imgur.com/6iGQc4jl.png)](http://i.imgur.com/6iGQc4j.png)





#### Programación
En Programación eliges cuándo enviar tu notificación, también programar tu envío para que se realice a una hora o día determinados. Twinpush también pone a disposición una potente herramienta para programar campañas de marketing en Crear campaña. En una campaña podrás enviar una notificación, la que podrás repetir el número de veces que indiques, dentro de un periodo establecido. El periodo lo estableces tu mismo seleccionando la fecha de inicio y fin, o el número de días, el rango de horas, y los días de la semana. 

* **Ahora**: La notificación se enviará inmediatamente despues de clicar Enviar que encontrarás al pulsar Guardar y previsualizar.
* **Elegir fecha**: La notificación se enviará en el día y hora establecidos.


[![](http://i.imgur.com/8cIDa1ml.png)](http://i.imgur.com/8cIDa1m.png)

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

* **Grupo de notificaciones**: Añade esta notificación a un grupo existente o a un nuevo grupo, escribe el nombre del grupo aquí.
* **Velocidad de envío**: Elige la velocidad en que se distribuirá la notificación a tus usuarios.
* **Badge**: Escribe el badge que aparecerá en el Smartphone, por defecto +1 al número que ya tenga el ícono.
* **Sonido**: Elige el tono musical que sonará al recibir la notificación, en el caso que tu App disponga de varios sonidos.
* **Tags**: Envía al Smartphone el tipo de notificación que estas enviando, en el caso que tu App disponga de diferentes tipos.
* **Propiedades personalizadas**: Las propiedades añadidas a las notificaciones permiten enviar información (clave/valor) a la aplicación que puede ser interpretada para realizar ciertas acciones, como dirigir al usuario a una sección en concreto de la Aplicación o mostrar contenido o funcionalidades específicas.


[![](https://i.imgur.com/0K9uIkBl.png)](https://i.imgur.com/0K9uIkB.png)

* **Ajustes avanzados de iOS**: A partir de iOS 10 es posible enviar adjuntos en la propia notificación para mostrar al usuario imágenes, videos, audios... Que se mostrarán sin necesidad de abrir la Aplicación

[![](https://camo.githubusercontent.com/ffe9d4528c9e8a2d3bf35294b6e9fb731077bfcb/687474703a2f2f692e696d6775722e636f6d2f66526b55716b482e676966)](https://camo.githubusercontent.com/ffe9d4528c9e8a2d3bf35294b6e9fb731077bfcb/687474703a2f2f692e696d6775722e636f6d2f66526b55716b482e676966)


### Guardar y Previsualizar

Una vez hayas completado tu notificación, podrás salvarla y enviarla clicando sobre Guardar y previsualizar abajo a la derecha. TwinPush guardará tu notificación configurada y te mostrará una pantalla resumen. Comprueba que tu notificación este correcta y envíala con el boton Send. Si no lo está, podrás editarla con Edit, o borrarla con Delete. El botón Duplicate te será de gran utilidad para reutilizar notificaciones o para crear tus propias plantillas sobre las cuales puedas hacer variaciones sobre un duplicado de una plantilla original.


[![](http://i.imgur.com/CEWk6mol.png)](http://i.imgur.com/CEWk6mo.png)

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

[![](http://i.imgur.com/DoqbGUil.png)](http://i.imgur.com/DoqbGUi.png)

O también clica en Crear nuevo segmento arriba a la derecha.

[![](http://i.imgur.com/TkkJ3kfl.png)](http://i.imgur.com/TkkJ3kf.png)



Si ya tienes segmentos creados en tu aplicación verás la siguiente pantalla. Desde aquí obtendrás una rápida vista de todos tus segmentos, donde se muestra para cada uno de ellos, el número de dispositivos, el porcentaje de dispositivos objetivo del segmento (barra verde) sobre el universo de dispositivos totales (barra gris de fondo) y el tipo de filtrado del segmento: por posición, por propiedades del dispositivo o por estadísticas de uso. Para crear un nuevo segmento desde esta pantalla, clica sobre Crear nuevo segmento arriba a la derecha.

[![](http://i.imgur.com/ApWNVOnl.png)](http://i.imgur.com/ApWNVOn.png)




### Editor de Segmentos
Al clicar sobre Crear nuevo segmento entrarás en el Editor de Segmentos. El editor te llevará por defecto al filtro por Ubicación. El editor de segmentos se presenta como una lista de filtros sobre el margen izquierdo de la pantalla, que podrás ir añadiendo al segmento creado. Los filtros son de tres tipos: por Ubicación, por Datos de Usuario o por Datos del Dispositivo. En el centro de la pantalla encontrarás las opciones de configuración del filtro seleccionado. Sobre la derecha de la pantalla podrás añadir una condición a todos los filtros seleccionados y dar un nombre al segmento recién creado. 
Cada filtro que vas añadiendo al segmento se verá representado a través de un pequeño índice en su correspondiente sección. Este índice indica la cantidad total de filtros totales de esa sección. Así por ejemplo, si añades 2 idiomas distintos, el sub índice en la sección de idiomas será 2, y si añades 3 ciudades, el sub índice en ciudades será 3.

[![](http://i.imgur.com/CTDBoGIl.png)](http://i.imgur.com/CTDBoGI.png)


#### Filtros por Ubicación
TwinPush ofrece diferentes maneras de filtrar un grupo de usuarios de acuerdo a su ubicación: puedes crear uno o más geocercos, especificar uno o más países, estados, regiones, o ciudades, para ello clica sobre Coordenadas, País, Estado, Región o Ciudad.  

[![](http://i.imgur.com/naXogjpl.png)](http://i.imgur.com/naXogjp.png)



##### Creación de Geocercos
Los geocercos no son más que una superficie circular determinada por una coordenada que identifica el centro del círculo y un radio especificado en metros. Para crear un nuevo geocerco, clica sobre Coordenadas a la izquierda para seleccionar este tipo de filtro y luego sobre Añadir, en la parte superior derecha del mapa. En la pantalla te aparecerá un mapa como muestra la siguiente imagen. En esta pantalla deberás ubicar el marcador o POI en la posición deseada y elegir un radio con la barra deslizante de la parte inferior.  La región seleccionada aparecerá sombreada en el mapa. En la parte superior hay un cuadro de búsqueda, en él puedes escribir el nombre de la ciudad que te interesa, también podrás navegar sobre el mapa con el ratón. Una vez establecida la región de interés sobre el mapa, clica sobre Añadir abajo a la derecha.

[![](http://i.imgur.com/6CgZDVJl.png)](http://i.imgur.com/6CgZDVJ.png)


#### Filtros por Datos de Usuario
En esta sección podrás segmentar a tus usuarios de acuerdo a la información que tu aplicación haya obtenido del usuario. Para ello tu aplicación deberá registrar esta información en la plataforma Twinpush a través de los "Custom Properties", puedes ver cómo hacerlo en el manual descrito [aquí](http://www.twinpush.com/documentation/devices#post-set-custom-property). Por defecto Twinpush te ofrece información del idioma de tus usuarios.

[![](http://i.imgur.com/OduTrRwl.png)](http://i.imgur.com/OduTrRw.png)



Con los "Custom Properties" podrás segmentar a tus usuarios por: edad, género, ocupación, intereses o cualquier otra información que quieras personalizar. Para añadir un filtro, clica sobre Otras propiedades, y luego sobre Añadir arriba a la derecha, te aparecerá una pantalla como la siguiente. En ella podrás añadir un filtro sobre cualquiera de las propiedades que encontrarás en un menu desplegable.

[![](http://i.imgur.com/63WxCwNl.png)](http://i.imgur.com/63WxCwN.png)



#### Filtros por Datos del Dispositivo
TwinPush pone a tu disposición la información obtenida del dispositivo con el cual el usuario accede a tu aplicación. Información como: Plataforma (iOS o Android), Fabricante, Modelo, Versión del sistema, Version de tu App, etc. Podrás segmentar a tus usuarios añadiendo un filtro sobre dicha información.

[![](http://i.imgur.com/ywmGskIl.png)](http://i.imgur.com/ywmGskI.png)




##### Estadísticas de uso de tu App
TwinPush también te permite segmentar a tus usuarios según el tiempo que usan tu App. Con esta funcionalidad podrás crear campañas que incentiven el uso de tu App, pudiendo premiar a tus usuarios con ofertas exclusivas para ese segmento. Para añadir un filtro de uso de tu App, clica sobre Estadísticas de uso, y luego sobre Añadir, arriba a la dechecha, a continuación verás una pantalla como la siguiente. Podrás añadir un filtro sobre: el tiempo total de uso, el periodo de inactividad, el tiempo medio de uso diario o el tiempo transcurrido desde la instalación.

[![](http://i.imgur.com/syT86bBl.png)](http://i.imgur.com/syT86bB.png)

#### Segmentos a usuarios con valores NO coincidentes
TwinPush ofrece la posibilidad de crear condiciones destinadas a envíos de usuarios que NO cumplan ciertas condiciones.
Para establecerlo, basta con selecionar la propiedad y asignarle el valor negativo.

[![](https://i.imgur.com/wik5yH6l.png)](https://i.imgur.com/wik5yH6.png)


#### Resumen
Una vez establecidos tus filtros, podrás añadir una condición a todos ellos en la sección Resumen, a la derecha de la pantalla. Recuerda que cada filtro creado se mostrará con un sub indice en su sección. Selecciona entre "Cualquiera" o "Todas" en el menú desplegable.

* **cualquiera**: tu segmento incluirá a los usuarios que cumplan cualquiera de los filtros, por ejemplo: si has creado dos filtros por ubicación, uno en Madrid y otro en Barcelona, al seleccionar *cualquiera*, tu segmento incluirá a los usuarios con dispositivos ubicados en Madrid o en Barcelona, es decir, en ambas ubicaciones. La opción *cualquiera*, abre más tu segmento.
* **todas**: tu segmento incluirá a los usuarios que cumplan todos los filtros a la vez, por ejemplo has creado un filtro por ubicación en Madrid y otro filtro por plataforma iOS, al seleccionar *todas*, tu segmento incluirá a todos los usuario de iOS y a la vez ubicados en Madrid. La opción *todas* restringe más tu segmento.

Finalmente, dale un nombre a tu segmento y guárdalo clicando Crear Segmento.

[![](http://i.imgur.com/1b4AEHal.png)](http://i.imgur.com/1b4AEHa.png)



## Audiencia / Usuarios

TwinPush muestra los datos estadísticos más relevantes de tus usuarios, agrupados en tres bloques de información, Uso de la Aplicación, datos de Usuarios y datos de Dispositivos.
Para conocer más en detalle los datos de nuestros usuarios y tener la posibilidad de exportarlos para su estudio exhaustivo, deberemos hacerlo en la vista de ["Dispositivos"](#dispositivos)

### Uso de la Aplicación:

**Plataforma**: Número de dispositivos por plataforma, iOS o Android.

**Datos de Uso**: Gráficas por tiempos de uso de la Aplicación.

* Ha usado la Aplicación más de ...
* Ha usado la Aplicación menos de ...
* Ha usado la Aplicación de media más de ...
* Ha instalado la Aplicación hace menos de ...
* No ha usado la aplicación desde hace ...


[![](http://i.imgur.com/yPlwCdWl.png)](http://i.imgur.com/yPlwCdW.png)



### Propiedades de Usuario:
Mediante la [Integración de la "custom properties" en el SDK](http://developers.twinpush.com/quickstart), TwinPush es capaz de recibir y mostrar los datos relativos a las propiedades de los usuarios, estas gráficas se configuran automáticamente según el tipo de propiedad.

[![](http://i.imgur.com/wL83pgPl.png)](http://i.imgur.com/wL83pgP.png)



### Datos de Dispositivo:
Los datos de dispositivo que se muestran gráficamente son:

* **Idioma** en el que está el dispositivo configurado.
* **Fabricante** del dispositivo.

[![](http://i.imgur.com/yMS4Mall.png)](http://i.imgur.com/yMS4Mal.png)



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

[![](http://i.imgur.com/qiBMdlVl.png)](http://i.imgur.com/qiBMdlV.png)



Al hacer click sobre uno de los dispositivos se mostrará un modal con toda la información relativa a este dispositivo, además de la información general, se mostrará:

#### Información del Dispositivo:
* Fabricante
* Modelo
* Código de dispositivo:
* Versión del Sistema Operativo
* Versión de la App
* Versión del SDK

#### Información de Localización:
Siempre que se haya realizado una [integración del SDK](http://developers.twinpush.com/quickstart) con la geolocalización activa de dispositivos, TwinPush mostrará información relativa a la ubicación del mismo.

* País
* Estado
* Ciudad

#### Datos de Usuario (Custom Properties):
El [SDK](http://developers.twinpush.com/quickstart) permite el registro de propiedades de usuario en TwinPush que también se mostrarán en la vista de Dispositivos.

[![](http://i.imgur.com/vqfEe5Ol.png)](http://i.imgur.com/vqfEe5O.png)



### Exportación:
TwinPush permite la Descarga de toda nuestra base de usuarios mediante la Exportación de un fichero CSV que contiene toda la información de cada uno de los registros de dispositivos.

Al tratarse de una tarea "pesada" TwinPush ofrece la posibilidad de descargarse siempre el último fichero generado así como lanzar el proceso de nuevo para actualizar el fichero.

[![](http://i.imgur.com/D3bhOful.png)](http://i.imgur.com/D3bhOfu.png)



## Ajustes

En la pestaña de Ajustes tendremos acceso a los parámetros de configuración de nuestra Aplicación, las claves de autenticación para la integración o la gestión de equipo.

### Detalle de Aplicación:
Podremos modificar los datos principales de nuestra Aplicación, tales como:

* **Nombre**: Nombre de la Aplicación que se muestra en TwinPush.
* **Zona horaria**: Modificar la zona horaria por defecto de nuestra aplicación, esto influirá en el envío de notificaciones y la programación horaria de las campañas, aun así, en cada campaña podremos definir una zona horaria única para esta campaña.
* **Icono**: Subir imagen con el icono que identificará nuestra Aplicación en TwinPush.
* **Badge number**: Este parámetro configura el número que aparece encima del icono de nuestra aplicación en los dispositivos iOS. Siendo por defecto +1.
* **Buzón por defecto**: Esta casilla habilita el uso por defecto del buzón, almacenando todas las notificaciones nuevas en cada buzón de usuario.

[![](http://i.imgur.com/KDkEUntl.png)](http://i.imgur.com/KDkEUnt.png)



### Claves de Autenticación:

En esta vista también podremos consultar nuestras claves de autenticación con el servidor, necesarias para la integración del [SDK de TwinPush](http://developers.twinpush.com/quickstart) en las aplicaciones.

* **Subdominio**: Mostrará el subdominio que debemos configurar en la integración del SDK, customizado en el caso de clientes Enterprise.
* **Application ID**: Identificador de Aplicación de TwinPush.
* **API Key**: Parámetro de autenticación para la Aplicación y su conexión con el servidor de TwinPush.
* **API Key Creator**: Parámetro de autenticación para la creación y envío de notificaciones desde otro servidor.


[![](http://i.imgur.com/cANApZkl.png)](http://i.imgur.com/cANApZk.png)



### Gestión de Equipo:
TwinPush permite la gestión de las personas que tendrán acceso a tu aplicación. La invitación se realiza introduciendo el email de la persona a la que deseemos dar acceso y TwinPush se encargará de enviar un email al invitado indicándole los pasos a seguir para acceder a la aplicación.

[![](http://i.imgur.com/9JLxmO3l.png)](http://i.imgur.com/9JLxmO3.png)


#### Roles de usuario
Hay tres roles de usuarios que el propietario o los administradores de la cuenta puede elegir para cada miembro de su equipo: Invitado, Usuario o Administrador.


**Invitado**: los usuarios invitados tienen acceso a:

* Información de audiencia.
* Listado de dispositivos registrados.
* Estadísticas de las notificaciones push.

**Usuario**:  los usuarios con el rol de usuario, además tienen acceso completo a:

* Gestión de segmentos, pueden crear y editar los segmentos existentes.
* Envío de notificaciones push, pueden crear, editar, enviar notificaciones y crear, editar y activar campañas.

**Administrador**:  los usuarios administradores tienen el control total de la aplicación y pueden además acceder a:

* Ajustes de aplicación, incluyendo la consulta de API Keys y configuración de APNS o FCM/GCM.
* Claves de autenticación, para autenticar el acceso de la App móvil (SDK) y el API de TwinPush.
* Gestión del equipo, pueden invitar nuevos usuarios, editar roles de usuarios existentes y revocar accesos de otros usuarios.

[![](http://i.imgur.com/98u3GDAl.png)](http://i.imgur.com/98u3GDA.png)



### Configuración FCM (GCM) y APNS:

En la vista de Ajustes de TwinPush también dispondremos del acceso a la configuración de los certificados para el acceso a los servicios de [APNS de Apple](http://help.apple.com/xcode/mac/current/#/dev11b059073) y [FCM de Google](https://developers.google.com/cloud-messaging/), necesarios para el envío de Notificaciones Push a dispositivos. Estos datos deberán ser proporcionados por el equipo de desarrollo de la Aplicación, más información sobre esta configuración en la [documentación de integración del SDK](http://developers.twinpush.com/quickstart).


[![](http://i.imgur.com/xhMUPMwl.png)](http://i.imgur.com/xhMUPMw.png)

El acceso a los servicios de mensajería de Google se realiza por el **API Key** que puede ser el proporcionado por el Servicio Firebase Cloud Messaging (FCM) o también por el anterior servicio Google Cloud Messaging (GCM). Para configurar el API Key es necesario desplegar el menu y seleccionar la plataforma adecuada, pegar el API Key y el nombre del Paquete y darle al botón Actualizar App.

[![](https://i.imgur.com/0B1QppDl.png)](https://i.imgur.com/0B1QppD.png)


Los servicios de mensajería de Apple se acceden con el **certificado APNS** que caduca anualmente y debe renovarse, o por **token** que no caduca. 

[![](https://i.imgur.com/GUnIotZl.png)](https://i.imgur.com/GUnIotZ.png)

TwinPush mantiene un control sobre la fecha de caducidad de tu certificado APNS, mostrando una alerta cuando reste poco tiempo para su caducidad, evitando errores de certificado no válido, que provocaría errores de envío a dispositivos iOS.



**Subir Certificado APNS:** En la subida del certificado de APNS (fichero .p12) debemos tener en cuenta marcar nuestro certificado como "Desarrollo" si estamos compilando una versión de pruebas desde nuestro entorno o de "Producción" Si ya es una aplicación que va dirigida al Store.


[![](http://i.imgur.com/U1gFV0bl.png)](http://i.imgur.com/U1gFV0b.png)

**Token:** Similarmente al APNS, el token (fichero .p8) se debe tener en cuenta si es para Desarrollo o Producción. 

[![](http://i.imgur.com/zmcIDCFl.png)](http://i.imgur.com/zmcIDCF.png)