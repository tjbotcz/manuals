# Návod na zostavenie TJBotCZ a pripojenie hardvéru 

---
![exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _** UPOZORNENIE PREDTÝM NEŽ ZAČNETE**_ 

 _1. DÁVAJTE SI POZOR PRI SKLADANÍ KARTÓNU. AK HO POSKLADÁTE NESPRÁVNE, BUDETE HO MUSIEŤ PRILEPIŤ LEPIDLOM._
 
 _2. PRI PRÁCI SA ZAŠPINÍTE. LASEROM VYREZANÝ KARTÓN ZANECHÁVA NA RUKÁCH ČIERNE ŠKVRNY._

(Odporúčame vám utrieť každý diel papierovým obrúskom.)

---

### Videonávod
Tu je originálny video návod ako zostaviť TJBota, pokojne sa ním môžete riadiť. Jediným väčším rozdielom je pripojenie LED diódy. TJBotCZ používa klasickú RGB diódu, ktorá je iba položená na platforme pod vrchnou časťou (hlavou) - pozrite si fotografie nižšie. Ak chcete diódu upevniť, odporúčame použiť Blue Tack alebo podobnú lepiacu gumu na plagáty, tzv. žuvačku. 

**Dávajte si pozor:**
* poskladajte kartón správnym smerom (na niektorých častiach je pokyn "fold up" (ohni hore) alebo "fold down" (ohni dolu) - lepšie viackrát overiť, ako neskôr ľutovať :)
* držte sa postupu vo video návode, aby ste ho nemuseli neskôr prerábať 
  * hlavne keď pripájate nôžky pre stabilitu
  * servo vložte v určenej etape  


<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a>

### Čo je teda na TJBotCZ odlišné?

1. Diel pre uchytenie reproduktora.
2. RGB LED

Dobrý návod ako zostaviť TJBota je k dispozícii aj tu (v angličtine):

https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/

Pre dlhšiu životnosť odporúčame prilepiť niektoré časti lepiacou pištoľou, najmä nohy a chlopne držiace Raspberry Pi. 

### Pripájanie hardvéru

Obrázok nižšie znázorňuje všetky periférie, ktoré môžete pre pripojenie TJBota potrebovať:
* napájanie 
* HDMI pre pripojenie monitora
* camera 
* jack audio výstup pre reproduktor
* ethernet pre pripojenie na internet (v prípade, že nepoužívate WiFi)
* USB vstupy pre mikrofón, myš a klávesnicu
* PINy na Raspberry Pi pre pripojenie RGB LED a serva

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg)


**GPIO piny**

Periférie sa na Raspberry Pi pripájajú cez jednotlivé piny. Tu je schéma ku všetkým pinom:
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png)


**Pripájanie serva k GPIO pinom**

Servo používa 3 piny:
* 5V napätie / + (fyzický pin 02)
* uzemnenie / - (fyzický pin 14)
* GPIO 7 pre ovládanie serva (fyzický pin 26) - možno konfigurovať v konfiguračnom súbore TJBotCZ (config.js - pozri Oživenie)


![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg)


**Pripájanie RGB LED na GPIO piny**

RGB LED používa 4 piny:
* uzemnenie / - ( fyzický pin 09)
* GPIO 17 / R (fyzický pin 11) - možno konfigurovať v konfiguračnom súbore TJBotCZ (config.js - pozri Oživenie)
* GPIO 27 / G (fyzický pin 13) - možno konfigurovať v konfiguračnom súbore TJBotCZ (config.js - pozri Oživenie)
* GPIO 22 / B (fyzický pin 15) - možno konfigurovať v konfiguračnom súbore TJBotCZ (config.js - pozri Oživenie)

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg)


