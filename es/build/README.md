# Manual para crear TJBotCz y conectar el hardware
---
![exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) 
_**AVISO ANTES DE EMPEZAR**_
_1. PRESTE ATENCI”N CUANDO DOBLE EL CART”N, SI LO DOBLA MAL, NECESITAR¡ UN PEGAMENTO PARA ARREGLARLO.
 _2. PREP¡RASE PARA ENSUCIARSE. EL CORTE LASER DEL CART”N DEJA MANCHAS NEGRAS EN SUS MANOS. (Os recomendamos limpiar cada parte con un paÒuelo de papel.)

### VÌdeo-manual
AquÌ est· el VÌdeo-manual original para construir el TJBot. Puede seguirlo. La ˙nica diferencia que hay es en conectar el LED. TJBOtCZ utiliza RGB LED tradicional  el cual est· sobre una plataforma debajo de la parte superior (la cabeza) ñ mire las fotos abajo. Para reparar el LED, recomendamos utilizar una masilla adhesiva reutilizable (®Blue Tack®) o una goma pegajosa similar.

**Tenga cuidado.**
* Doble el cartÛn de una manera correcta (en algunas partes hay instrucciones "doble arribaì o "doble abajoì ñ m·s vale prevenir que lamentar :)
* siga las instrucciones en el vÌdeo manual para que luego no tenga que volver a montarlo de nuevo
  * especialmente cuando conecte las piernas para la estabilidad
  * insertando el servomecanismo
<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a>
### Entonces,  øQuÈ es diferente en TJBotCz?
1. Parte sosteniendo el altavoz
2. RGB LED
Buenas instrucciones de como montar el TJBot est·n disponibles tambiÈn aquÌ:
https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/
Para una resistencia mayor, recomendamos pegar algunas partes con pistola de pegamento.  
Especialmente las piernas y las partes que sostienen la Raspberry Pi en la parte inferior.

### Conectando el hardware 
La imagen abajo muestra toda la conectividad que puede necesitar para TJBot:
* adaptador de corriente
* HDMI para conectar el monitor
* c·mara
* salida de audio jack para altavoz
* ethernet que se conecta a internet (en caso de que no use Wifi)
* Ranuras USB para micrÛfono, ratÛn y teclado
* pins en Raspberry Pi para conectar RGB LED y el servomecanismo. Pines en Raspberry Pi para conectar RGB LED y el servomecanismo.
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg)

**GPIO pins**
Los perifÈricos a Raspberry Pi est·n conectados a travÈs de pines individuales. AquÌ est· la leyenda de todos los pines:
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png)
** Conectando el servomecanismo a GPIO pines** 
El servomecanismo utiliza 3 pines:
* 5V power / + (physical pin 02)
* de tierra / - (physical pin 14)
* GPIO 7 para comandos (pin fÌsico 26) - se puede configurar (config.js ñ mira ®Encender TJBot®)
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg)

**Conectando RGB LED a GPIO pines**
RGB LED usa 4 pines:
* de tierra / - (physical pin 09)
* GPIO 17 / R (physical pin 11) ñ puede ser configurado (config.js - see bring-to-life)
* GPIO 27 / G (physical pin 13) ñ puede ser configurado (config.js - see bring-to-life)
* GPIO 22 / B (physical pin 15) ñ puede ser configurado (config.js - see bring-to-life)

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg)



