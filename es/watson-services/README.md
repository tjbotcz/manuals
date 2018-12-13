# IBM Cloud: Servicios de Watson

Para darle vida a TJBot necesitarà los servicios de Watson que estan disponibles en IBM Cloud. 

Al  encender e instalar TJBot, le dara el poder de:

* Escuchar: Utlizando el Servicio de Habla a Texto, convirtiendo archivos de voz a texto que puedan ser procesados mas adelante. 

* Hablar: Utlizando el Servicio de Texto a Habla, convirtiendo texto a archivos de voz que TJBot utilizara para hablar.

* Ver: Utlizando el Servicio de Reconocimiento Visual, analizando fotografìas, para que el TJBot pueda decirle què es lo que ve. 

* Charlar: Utlizando el Servicio de Asistente de Watson, creando dialogos lògicos para que tenga una charla de alta calidad con el TJBot.

Para que acceder a estos servicios necesitara tener una cuenta en IBM Cloud (la inscripciòn es gratuita). Puede acceder a los servicios en la version “ligera” ,que es gratuita. Todo servicio tiene sus credenciales, las cuales necesitara ingresar en el archivo de configuracion de TJBotCZ (credentials.js).

Empecemos creando los servicios y anotemos al detalle las credenciales. 


## Inscripciòn en IBM Cloud

Puede inscribirse en IBM Cloud en www.bluemix.net.

La inscripción es gratuita. (no necesita tarjeta de credito) y le permite acceder a los servicios necesarios en la version Ligera, dicha version es suficiente para nuestros requerimientos. Puede acceder a todos los servicios en la pestana ¨Catalogo¨
 

## Servicio de Habla a Texto 

En ¨Catalogo¨ busque _**Habla a Texto**_ y pinche “Crear”. Se abrirà una nueva pàgina de servicios de configuraciòn.  Pinche el ìcono ¨Mostrar¨ y podrà ver las credenciales de este servicio (nombre de usuario y contrasena). Ingresara estas credenciales en el archivo de configuracion de TJBotCZ (credenciales.js)

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Servicios de Texto a Habla 

En ¨Catàlogo¨ busque _**Texto a Habla**_ y pinche ¨Crear¨. Se abrira una nueva pagina de servicios de configuraciòn. Pinche el icono ¨Mostrar¨ y podrà ver las credenciales de este servicio (nombre de usuario y contrasena). Ingresara estas credenciales en el archivo de configuracion de TJBotCZ  (credentials.js). 

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Servicio de Reconocimiento Visual 

En ¨catalogo¨buscar ** Reconocimiento Visual** pinche en ¨Crear¨. Se abrira una nueva pagina de servicios de configuracion. Pinche el ìcono  ¨Mostrar¨ y podrà ver las credenciales de este servicio. Ingresara estas credenciales en el archivo de configuracion de TJBotCZ  (credentials.js). En el caso de que estos servicios tambien sean llamados API KEY, entonces necesitaras: ![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)


## Servicios del Asistente Watson 

El asistente de Watson es una herramienta para crear dialogos (charlas). Para empezar ràpidamente hemos preparado un dialogo simple que puedes importar al servicio, antes que puedas crear tu propia charla. 

[Descargue el diálogo aquí](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). 

En catàlogo 

En "Catalog" busque por _**Watson Assisstant**_ y haga click en "Crear". Una nueva pagina de configuracion de servicios se abrirá. Pinchando en el botón “Lanzar” se abrirá una nueva ventana para crear chats, seleccione “Workspace” y allí encontrará un icono para importar el archivo con el diálogo descargado (vea la imagen abajo).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

Despues de importar el diálogo, un Workspace serà creado. Un icono parecido a una serpiente le llevará al apartado en el cual se deben de introducir los credenciales de TjBot. (credentials.js). En el caso de Watson Assisstant hay 3 credenciales: workspace id, nombre de usuario y contraseña.

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)

