# TwinPush: Actualización a Firebase

El presente documento contiene las instrucciones a seguir para actualizar el proyecto Android de notificaciones Push a Firebase, la nueva plataforma de Google que reemplaza a Google Cloud Messaging (GCM).

![](https://i.imgur.com/AyTX7k1.png?)

### ¿Qué es Firebase?

Firebase (también conocido como FCM) es la plataforma de Google que ahora incorpora el servicio de notificaciones Push y que ha reemplazado a la anterior Google Cloud Messaging (GCM). A nivel de notificaciones Push, el cambio de GCM a Firebase se trata de sencillamente de un *rebranding* o cambio de nombre comercial, lo que permite que ambas plataformas sean, por el momento, totalmente compatibles.

En la práctica esto significa que desde GCM se pueden enviar notificaciones a dispositivos registrados en Firebase, y viceversa. Esto facilita la actualización al nuevo sistema, ya que ambas plataformas pueden convivir sin problemas.

## 1. Importar el proyecto a Firebase

El primer paso a realizar es importar el proyecto desde la plataforma a Firebase. Para ello, de debe iniciar sesión con la cuenta de Google que es la propietaria del proyecto en la consola de desarrolladores y acceder a la [consola de Firebase](https://console.firebase.google.com/u/0/) y seleccionar la opción **Importar Proyecto de Google**.

![](https://imgur.com/75cVHUZ.png?)

Posteriormente basta con seleccionar el proyecto del listado y seleccionar **Añadir Firebase**.

## 2. Registrar la aplicación en Firebase

Una vez importado el proyecto, se debe crear la aplicación de Android asociada al mismo a través de la opción **Añadir aplicación**.

Se debe seleccionar aplicación de Android e introducir el número de paquete de la misma.

![](https://imgur.com/6wVeIJc.png)

Una vez creada la aplicación de Android, se puede descargar el archivo de configuración de Google `google-services.json` desde la sección de ajustes.

![](https://imgur.com/hY6xbTS.png)

Por último, en la sección **Mensajería en la nube** de la Configuración del proyecto, se puede acceder a las claves de servidor que se deben configurar en la plataforma de TwinPush para realizar los envíos a través de Firebase:

![](https://imgur.com/Nre79CN.png)

## 3. Eliminar dependencias de GCM

Las dependencias de la librería de GCM ya no son necesarias a partir de la versión 2.4 del SDK de TwinPush, que ya hace uso de Firebase para el registro y la recepción de mensajes en el sistema de notificaciones de Google.

Por ello, el primer paso si estamos actualizando de GCM a Firebase es eliminar las dependencias previas que tuviéramos de la librería de Google.

### Gradle

En principio no debería ser necesario tener una dependencia de la librería de GCM en gradle, ya que esto es gestionado automáticamente por TwinPush pero, si a pesar de ello está añadida, se puede **eliminar** del archivo gradle del módulo de la aplicación:

```
dependencies {
  compile "com.google.android.gms:play-services-gcm:8.4.0"
}
```

### Permisos

En las últimas versiones de TwinPush, los permisos de GCM eran gestionados automáticamente. No obstante, es posible que aún estén presentes en el archivo `AndroidManifest.xml` del proyecto. Puedes **eliminar** estos permisos:

```xml
<uses-permission android:name="android.permission.WAKE_LOCK" />
<permission android:name="<your-package-name>.permission.C2D_MESSAGE"
            android:protectionLevel="signature" />
<uses-permission android:name="<your-package-name>.permission.C2D_MESSAGE" />
```

### GCM Receiver

Con Firebase, la clase `GcmReceiver` ya se añade automáticamente, por lo que puedes **eliminarlo** del archivo `AndroidManifest.xml` del proyecto:

```xml
<receiver
    android:name="com.google.android.gms.gcm.GcmReceiver"
    android:exported="true"
    android:permission="com.google.android.c2dm.permission.SEND" >
    <intent-filter>
        <action android:name="com.google.android.c2dm.intent.RECEIVE" />
        <category android:name="com.example.gcm" />
    </intent-filter>
</receiver>
```

### Servicios

Los servicios de notificaciones Push declarados en el archivo `AndroidManifest.xml` también deben modificarse.

Deben **eliminarse** los siguientes servicios del nodo `application`:

```xml
<service
    android:name="com.twincoders.twinpush.sdk.services.NotificationIntentService"
    android:exported="false">
    <intent-filter>
        <action android:name="com.google.android.c2dm.intent.RECEIVE" />
    </intent-filter>
</service>
<service
	android:name="com.twincoders.twinpush.sdk.services.RegistrationIntentService"
    android:exported="false"/>
```

Y reemplazarse por los siguientes:

```xml
<service
    android:name="com.twincoders.twinpush.sdk.services.TwinPushInstanceIdService">
    <intent-filter>
        <action android:name="com.google.firebase.INSTANCE_ID_EVENT" />
    </intent-filter>
</service>

<service
    android:name="com.twincoders.twinpush.sdk.services.NotificationIntentService">
    <intent-filter>
        <action android:name="com.google.firebase.MESSAGING_EVENT" />
    </intent-filter>
</service>
```

**Nota:** Si se había estaba utilizando una personalización de la clase `NotificationIntentService`, debe declararse en lugar de la clase por defecto.

## 4. Actualizar TwinPush

Tras eliminar las dependencias de GCM se debe actualizar la integración de TwinPush. En la [documentación del SDK](http://developers.twinpush.com/developers/android) se puede consultar la información actualizada.

### Gradle

El primer paso es actualizar la dependencia de la librería de la plataforma en el archivo `build.gradle` del módulo de la aplicación:

	dependencies {
	    compile 'com.twinpush.android:sdk:2.4.2'
	}
	
### Método `setup`

Se han actualizado las opciones de configuración de TwinPush que pueden incluirse en el método setup.

Concretamente se han **eliminado** los siguientes parámetros del objeto `TwinPushOptions`:

- `gcmProjectNumber`: Ya no es necesario, la configuración del servicio de Push se realiza mediante el archivo de `google-services.json`.
- `notificationIcon`: La definición del icono para las notificaciones ahora se realiza a través de un recurso de tipo *drawable* llamado `ic_tp_notification`.

Por tanto, la configuración de TwinPush, que antes tenía esta forma:

```java
TwinPushOptions options = new TwinPushOptions();
options.twinPushAppId =     "7687xxxxxxxxxxxx";
options.twinPushApiKey =    "c5caxxxxxxxxxxxxxxxxxxxxxxxx1592";
options.gcmProjectNumber =  "66xxxxxxxxxx";
options.subdomain =         "mycompany";
options.notificationIcon =  R.drawable.my_notification_icon;
TwinPushSDK.getInstance(this).setup(options);  
```

Pasa a declararse de la siguiente manera:

```java
TwinPushOptions options = new TwinPushOptions();
options.twinPushAppId =     "7687xxxxxxxxxxxx";
options.twinPushApiKey =    "c5caxxxxxxxxxxxxxxxxxxxxxxxx1592";
options.subdomain =         "mycompany";
TwinPushSDK.getInstance(this).setup(options);  
```

Donde el icono pequeño se puede declarar en un archivo de recursos (p.e. `res/values/drawables.xml`):

```xml
<drawable name="ic_tp_notification">@drawable/my_notification_icon</drawable>
```

## 5. Incluir configuración de Firebase

Por último, es necesario configurar la aplicación con el archivo de ajustes que hemos descargado al crear el proyecto en Firebase.

Para ello, primero se debe incluir la ruta de Google Services en el archivo `build.gradle` **del proyecto**:

```
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:2.3.3'
        classpath 'com.google.gms:google-services:3.1.0' // Google services
    }
}
```
A continuación, se debe copiar el archivo `google-services.json` al directorio del módulo de la aplicación:

![](https://imgur.com/9TKUuhK.png)

Y por último se debe aplicar el plugin de Google Services, que cargará automáticamente la configuración del archivo JSON y la aplicará a la instancia por defecto de Firebase, que TwinPush utilizará para el registro y recepción de notificaciones Push.

**Al final** del archivo `build.gradle` de la aplicación se debe incluir la siguiente línea:

	// Google services plugin must be in the end of the file to avoid dependency conflicts
	apply plugin: 'com.google.gms.google-services'

**Nota:** Si el archivo de configuración `google-services.json` entra en conflicto con otro archivo existente, o se desea configurar Firebase sin hacer uso de él, TwinPush dispone de un método alternativo para hacerlo a través de recursos de tipo String ([ver documentación](http://developers.twinpush.com/developers/android#alternative-firebase-setup)).

##6. Prueba de envío

Una vez seguidos todos los pasos, se puede compilar la aplicación, registrar el dispositivo en TwinPush y realizar una prueba de envío.

Los envíos realizados desde TwinPush llegarán tanto a los dispositivos registrados mediante Firebase como a los anteriores, que hacen uso de GCM.

## Problemas comunes

### No encuentra las librerías del SDK 26 de Android

Si se está actualizando el SDK de Android a la versión 26 es posible que sea necesario incluir el nuevo repositorio de Maven de Google, ya que Android Studio ya no accede al mismo por defecto ([ver más](https://developer.android.com/topic/libraries/architecture/adding-components.html)).

Para resolverlo, basta abrir el archivo `build.gradle` **del proyecto** y añadir el repositorio de maven:

```
allprojects {
    repositories {
        jcenter()
        maven { url 'https://maven.google.com' }
    }
}
```

### No llegan las notificaciones

Si las notificaciones no llegan al dispositivo, puede deberse a alguno de los siguientes casos:

- El nombre del paquete no está correctamente configurado en la aplicación de Firebase o en los ajustes de la App en la consola de TwinPush
- La clave de envío de Firebase o GCM no está correctamente asignada en los ajustes de la App en la consola de TwinPush
- Los servicios no están correctamente declarados en el nodo `application` del archivo Manifest de la aplicación
- El archivo `google-services.json` usado para configurar Firebase no corresponde con la clave utilizada en los ajustes de la App en la consola de TwinPush.