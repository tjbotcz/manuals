# Encender TJBot (con Raspberry Pi)

Elija el modo...
1. [Instalación rápida desde una configuración ya establecida](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#instalaci%C3%B3n-r%C3%A1pida-desde-una-configuraci%C3%B3n-ya-establecida)
2. [Instalación de cero para usuarios avanzados](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#empiece-desde-cero-como-usuario-avanzado)
3. Los siguientes links contienen temas de ayuda para instalar su TJBot.

    * [¿Cómo copiar archivos desde Windows a Raspberry-Pi usando la consola de windows.?](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#como-copiar-archivos-de-windows-a-raspberry-pi-utilizando-la-linea-de-comandos)
    * [¿Cómo copiar archivos desde Mac OS a Raspberry-Pi usando la consola (en Mac OS)?](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#como-copiar-archivos-desde-mac-os-a-la-raspberry-pi-utilizando-la-linea-de-comandos)
    * [¿Cómo copiar archivos desde Rasberry Pi a Mac OS usando la consola de comandos(v Mac Os)?](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#como-copiar-archivos-desde-rasberry-pi-a-mac-os-usando-la-linea-de-comando-para-mac-os)
    * [¿Cómo configurar la dirección IP de una Raspberry Pi’s?](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#como-configurar-la-direcci%C3%B3n-ip-de-raspberry-pi)
    * [¿Cómo cambiar el volumen de la Raspberry Pi’s usando la linea de comandos?](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#como-cambiar-el-volumen-de-raspberry-pi-mediante-la-linea-de-comando)
    * [Configuracion de la salida de audio a conector jack](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#configuracion-de-la-salida-de-audio-a-conector-jack)
    * [Adquiera mas espacio en su Tarjeta microSD](https://github.com/tjbotcz/manuals/tree/master/es/bring-to-life#adquiera-mas-espacio-en-su-tarjeta-microsd)
    
## Instalación rápida desde una configuración ya establecida. 

Por defecto, existe una configuración predeterminada si lo que desea es hacer funcionar su TJBot rápidamente. 

Que necesita:

*	Conexión a internet para descargar Raspbian OS y SW para instalar la imagen de la tarjeta.
*	Un ordenador con ranura para una tarjeta microSD o un lector de tarjetas.
*	Teclado USB, ratón USB.
*	LCD con puerto HDMI y cable HDMI.


Pasos:
1. Descargue la imagen  [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) y descomprimala.

2. Descargue y ejecute el programa necesario para instalar la Imagen de Raspbianu en la tarjeta microSD: https://etcher.io/ . Úselo para instalar la imagen en la tarjeta microSD, elija tjbotcz_lite.img, seleccione la microSD montada y ejecute.

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Inserte la tarjeta SD ya preinstalada en la Raspberry-Pi, conéctela al teclado, al ratón o con un cable de red RJ-45. La segunda opción es para conectar con WiFi (Si tiene WiFi tendrá que configurar la conexión desde su OS Raspbian GUI, Raspberry Pi recordará la configuración para el futuro.) Necesitará conexión a internet en el paso 4.

4. En el escritorio de la Raspbian hemos preparado un script que se llama "run-me-first.sh".  Ejecútelo en la terminal (consola). El Script descargará la ultima version de [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) desde internet e instalará los componentes necesarios.

5. Para poder conversar con TJBot, necesitará tener los siguientes servicios configurados en IBM Cloud:

* Watson Assistant (servicio para crear diálogos/chats)
* Speech to Text (servicio para pasar mensajes de voz a texto)
* Text to Speech (servicio para pasar texto a mensajes de voz)
* Visual Recognition (servicio para analizar imagenes o fotos)

  Proporcionar los servicions segun el manual de la carpeta ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Si tiene todos los servicios operativos puede continuar. Deberá de introducir los credenciales para cagda servicio en el archivo de configuración (credentials.js). Dado que los crendenciales son unas lineas muy largas, el mejor modo de introducirlas es conectando remotamente a TJBot desde el ordenador desde el cual tiene acceso a los servicios de Watson para copiarlos desde alli y pegarlos en el campo de credenciales. Para usuarios de MAC utilice el terminal, si utiliza Windows utilice lo siguiente [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy es un programa de acceso remoto y necesitará instalarlo primero. Usando el Terminal o PuTTy, conecte a TJBot (necesitará estar en la misma red conectado a la que está TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (introduzca la dirección IP de TJBot en el campo marcado):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Se le pedirá que ponga una contraseña. Por defecto, la contraseña es: **_raspberry_**.

7. En el terminal (o la consola en Windows) navegue hacia la carpeta con los archivos de configuración:

  ```
  cd Escritorio/tjbotcz_lite/configuration
  ```
8. Cree una copia de credentials.default.js y config.default.js y nombrelos credentials.js y config.js cada uno de ellos según corresonda. También puede hacer esto remotamente utilizando el Terminal o la consola de Windows:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. En el editor de texto llamado nano, inserte las credenciales necesarias para los servicios individuales.
  ```
  nano credentials.js
  ```
  Mire la imagen de abajo para saber que campos tienen que ser rellenados con los datos de credenciales de Watson Services. (no elimine las comillas).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Guarde y cierre el documento: CTRL+X, Y, Enter.
  
10. Y ahora, dé vida a TjBot! Vuelva a la carpeta Escritorio/tjbotcz_lite   .... y allá vamos!
  TJBot esta configurado para hablar en voz masculina por defecto y reacciona al nombre de Michael (Maikol fonéticamente). Esto quiere decir que únicamente va a reconocer frases en las que su nombre aparece. Para mas información sobre TJBotCZ lite y lo que hacer con él, visite el enlace [repository](https://github.com/tjbotcz/tjbotcz_lite).
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Empiece desde cero como usuario avanzado.

Raspberry-Pi usa Raspbian como Sistema Operativo, el cual está creado con Linux Debian.
El Sistema Operativo Raspbian estará en la microSD, para instalarlo allí va a necesitar:

*	Conexión a internet suficiente para descargar el Sistema Operativo y el Software para instalar la imagen de TJBot en la tarjeta.
*	Un ordenador con lector de tarjeta SD o microSD y una tarjeta SD o microSD.
*	Teclado y ratón USB.
*	LCD con puerto y cable HDMI.

Pasos:
1. Descargue Raspbian OS https://www.raspberrypi.org/downloads/ .

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Descargue el Software de instalación para poder ejecutar la imagen de Raspbian, for e.g. Etcher https://etcher.io/ y después instale Raspbian OS en su tarjeta microSD (click/seleccione el archivo descargado .img, por ultimo seleccione como destino la tarjeta SD y ejecútelo)!

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Introduzca la tarjeta microSD on el OS instalado en la Raspberry-PI. Conéctela con el teclado, el ratón o el cable RJ-45 (internet). La segunda opción es conectar con WiFi (si usa WiFi tendrá que configurar la conexión desde el OS Raspbian GUI, Raspberry Pi recordará la configuración para el futuro). Necesitará tener conectividad en el paso 5.

4. Permita la conexión para la Raspberry-Pi SSH, de modo que después pueda continuar con conexión a distancia con Raspberry-Pi a través del terminal (MAC) o PuTTY (Windows). In Terminal escriba:
```
sudo raspi-config
```
Se abrirá un menú.
Haga click en “Interfacing Options”.
Elija “SSH” y habilítelo haciendo click en "enable".
5. Abra el terminal y escriba:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
Este comando descargará un script del servidor, el cual ejecutará una guia interactiva en la consola de Windows. Con esta guía, configurará Raspberry Pi para TJBot:

* TJBot name (déjelo como raspberrypi)  - (Enter)
* IPv6 (disable) - (Si o Yes)
* Google DNS (enable) - (Si o Yes)
* settings local (language) (Si o Yes)
* update OS Raspbianu (Si o Yes)
* update to newer version of Node.js (No o N)
* connecting camera (Si o Yes)
* downloading original TJBot and test scenarios (Enter o Intro)
* configuring audio output (leave port for jack-audio enabled) (No o N)
* reboot (Si o Yes)

6. Instale node.js version 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. En el terminal abra la carpeta Escritorio:
```
cd Escritorio
```
8. Instale one de los programas TJBotCZ (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<name of tjbotcz program>.git
```
9. En el Terminal abra la nueva carpeta creada “tjbotcz_lite”, "tjbotcz" o "tjbotcz_iot":
```
cd <nombre de la carpeta sin los (sin los signos de mayor y menor que)>
```
10. Descargue dependencias definidas en el archivo package.json en la carpeta con el programa descargado en el paso 8:
```
npm install
```
11. Para poder chatear con TJBot, necesitará tener los siguientes servicios activos en IBM Cloud.

* Watson Assistant (servicio para crear diálogos/chats)
* Speech to Text (servicio para pasar mensajes de voz a texto)
* Text to Speech (servicio para pasar texto a mensajes de voz)
* Visual Recognition (servicio para analizar imagenes o fotos)

  Proporcionar los servicions segun el manual de la carpeta ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. Si tiene todos los servicios activos puede continuar. Necesitará introducir los credenciales para los servicios de manera individual en el archivo de configuración (credentials.js). Dado que los credenciales son bastante largos, la mejor forma de hacerlo es conectando remotamente con TJBot desde el ordenador desde el cual tiene acceso a los credenciales y desde alli copiar y pegarlos. Si es usuario de MAC utilice terminal, parausuarios de Windows, utilice PuTTy. [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy es un programa de acceso remoto y necesitará instalarlo primero. Utilizando el Terminal o con PuTTy, conecte a TJBot. (Necesitará estar en la misma red conectado a la que está TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (introduzca la dirección IP de TJBot en los campos marcados):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Se le pedirá que introduzca una contraseña, por defecto es: **_raspberry_**.

13. En el terminal (o en la consola de windows) navegue a la carpeta donde se encuentra el archivo de configuración:

  ```
  cd Escritorio/tjbotcz_lite/configuration
  ```
14. Cree una copia de los archivos credentials.default.js y config.default.js  y nómbrelos credentials.js y config.js según corresponda. Puede hacer esto también remotamente desde el terminal o la consola de Window:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. En un editor de texto llamado Nano, introduzca las credenciales para los servicios individuales Watson.
  ```
  nano credentials.js
  ```
  Vea la image de abajo para saber que campos deben de ser anotados con las credenciales de los servicios Watson. (no elimine las comillas).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Guarde y cierre el archivo: CTRL+X, Y, Enter.
  
16. Ahora, ya está todo listo para lanzar su TJBot. Vuelva a la carpeta Escritorio/tjbotcz_lite
  TJBot está configurado por defecto para hablar con voz masculina y si reacciona al nombre Michael (Maikol fonéticamente). Esto quiere decir, que únicamente reconocerá frases en las que se incluya su nombre. 
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Unos cuantos consejos que pueden ser útiles.

### Como copiar archivos de Windows a Raspberry Pi utilizando la linea de comandos: 
Abra la consola de windows y navegue hasta el directorio el cual tiene un archivo que quiere copiar. (cd = significa cambiar directorio). Ahora tendrá que verificar que PuTTy está instalado y funcionando C:\Program Files\PuTTY\pscp.exe. El ararchivo: “file.txt” es el nombre del archivo que desea copiar y “your_pi” es la dirección IP de su Raspberry Pi (solo se puede realizar en la misma conexión de red):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### Como copiar archivos desde Mac OS a la Raspberry Pi utilizando la linea de comandos:
Abra la linea de comandos y navegue hasta la ubicación del archivo que quiere copiar. (cd = significa cambiar directorio). Después utilice la siguiente linea de comando donde “file.txt” es el nombre del archivos que va a copiar y cambie “your_pi” a la dirección IP de su Raspberry Pi (solo se puede realizar en la misma conexión de red):

```
scp file.txt pi@your_pi:~/Escritorio/tjbotcz_lite
```


### Como copiar archivos desde Rasberry Pi a Mac OS usando la linea de comando (para Mac Os)
Si esta conectado a TJBot mediante SSH, desconectese primero:

```
logout
```

En el Terminal en Mac OS, utilice el siguiente comando para copiar archivos:

```
scp <username na Raspberry Pi>@<ip adresa Raspberry Pi>:/<dirección del archivo en Raspberry Pi> <dirección de destino de los archivos en Mac OS>
```

Ejemplo:

```
scp pi@192.168.1.10:/home/pi/Escritorio/tjbotcz_lite/config.js Usuarios/Miguel/Escritorio
```

Se le pedirá la contraseña de la Raspberry Pi.


### Como configurar la dirección IP de Raspberry Pi. 
Conecte con SSH PuTTy. Después utilice este comando:

```
sudo nano /etc/dhcpcd.conf
```

En el archivo abierto, busque la parte en la que pone "Static Address" e introduzca los valores correctos. (Dirección IP, dirección IP del router).



### Como cambiar el volumen de Raspberry Pi mediante la linea de comando: 
Conectar mediante SSH o PuTTy a la Raspberry Pi. La siguiente linea de codigo cambiará el volumen a 90%. El volumen debería de cambiar de forma immediata de modo que la diferencia entre 90% y 95% es notable.

```
amixer  sset PCM,0 90%
```

La siguiente opción es para hacer un atajo con el cual se puede cambiar el volumen fácilmente. En el editor nano abra el archivo .bashrc:

```
nano ~/.bashrc
```

Y al final del archivo agregue: 

```
# Incrementar volumen un 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Bajar volumen un 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
Reinicie Raspberry-Pi. Despues podrá escribir `volup`  o  `voldown`  en el Terminal y el volumen cambiara un 5% arriba o abajo.



### Configuracion de la salida de audio a conector jack
A veces puede suceder que no escuche a TJBot incluso si el volumen está al máximo, posiblemente el audio va a traves de HDMI y no esta conectado al altavoz mediante el conector "jack". Para conectarlo utilice el siguiente comando:

```
sudo amixer cset numid=3 1
```
El ultimo número especifica la salida (output) (0=auto, 1=jack, 2=HDMI)


### Adquiera mas espacio en su Tarjeta microSD
Si tiene 16GB microSD, debería de ser suficiente, pero si tiene 8gb despues de instalar todo le quedarán 2gb mas o menos, lo cual limitaría un poco la capacidad, puede desisntalar Wolfram y LibreOffice para tener un poco mas de espacio. No va a necesitar ninguno de esos programas para trabajar con TJBot en el futuro y obtendrá 1GB extra de espacio.

Para eliminar programas:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

---
