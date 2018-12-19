# Manuale per costruire TJBotCZ e collegare l'hardware

![Exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _**AVVISO PRIMA DI INIZIARE**_

 _1. PRESTARE ATTENZIONE MENTRE SI PIEGA  IL CARTONE. SE PIEGATO IN MANIERA SBAGLIATA, SERVIRÀ LA COLLA PER FISSARLO._
 
 _2. ATTENTI A NON SPORCARVI  LASERCUT CARTONE LASCIA FIOCCHI NERI SULLE VOSTRE MANI ._

(Si consiglia di pulire ogni parte con un fazzoletto di carta).

---

### Manuale-video 
E’ possibile seguire il manuale video originale per costruire TJBot. L'unica grande differenza consiste nel collegamento del LED. TJBotCZ utilizza LED RGB tradizionale che si appoggia su una piattaforma sotto la parte superiore (la testa) - guarda le foto sotto. Per fissare i LED, consigliamo di utilizzare Blue Tack o una gomma adesiva simile.

**Attenzione:**
* Piega il cartone nel modo corretto (su alcune parti c'è l'istruzione "piega su" o "piega giù" - quindi meglio prevenire che curare :)
* seguire passo per passo il  manuale video cosi non sarà necessario rimontarlo un’altra volta
  * in particolare quando si collegano le gambe per la stabilità
  * L’inserimento del servo


<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a>

### Quindi cosa c'è di diverso in TJBotCZ?

1. La parte che regge l'altoparlante.
2. LED RGB

E’ possibile guardare come costruire TJBot anche qui:

https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/

Per una maggiore durata del prodotto consigliamo di incollare alcune parti con la pistola per colla. In particolare le gambe e tutte le parti che tengono il Raspberry Pi sul fondo.



### Collegamento dell'hardware

L'immagine sotto mostra tutta la connettività che potrebbe servire per TJBot:
* adattatore di alimentazione
* HDMI per collegamento del monitor
* telecamera
* uscita audio jack per altoparlante
* connessione ethernet a internet (nel caso in cui non si usi WiFi)
* Slot USB per microfoni, mouse e tastiera
* pin su Raspberry Pi per il collegamento di LED RGB e servo

![Servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg)


**Pin GPIO**

Le Periferiche di Raspberry Pi sono collegate attraverso singoli pin. Ecco la legenda di tutti i pin:
![pin gpio](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png)


**Collegamento del servo ai pin GPIO**

Il servo usa 3 pin:
* 5V power / + (pin fisico 02)
* ground / - (pin fisico 14)
* GPIO 7 per i comandi (pin fisico 26) - può essere configurato (config.js - vedi porta-in-vita)


![Servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg)


**Collegamento del LED RGB ai pin GPIO**

LED RGB usa 4 pin:
* ground / - (pin fisico 09)
* GPIO 17 / R (pin fisico 11) - può essere configurato (config.js - vedi porta-in-vita)
* GPIO 27 / G (pin fisico 13) - può essere configurato (config.js - vedi porta-in-vita)
* GPIO 22 / B (pin fisico 15) - può essere configurato (config.js - vedi porta-in-vita)

![Servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg)


