# Návod na sestavení robota TJBotCZ a zapojení hardwaru

---
![exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _**DVĚ UPOZORNĚNÍ NA ZAČÁTEK**_ 

 _1. POZOR PŘI SESTAVOVÁNÍ Z KARTONU. POKUD JEJ ZLOMÍTE NA ŠPATNOU STRANU, NEOBEJDETE SE UŽ BEZ LEPIDLA._
 
 _2. PŘIPRAVTE SE NA TO, ŽE SE UMAŽETE. LASEREM ŘEZANÝ KARTON ČERNÍ._

(Doporučujeme každý vylouplý díl otřít papírovým kapesníkem)

---

### Videonávod
Zde je originální video návod, jak správně složit TJBota. Lze podle něj postupovat. Větší rozdíl je pouze v připevnění LED diody. TJBotCZ používá obyčejnou RGB diodu, která je položena pod vrchním dílem (viz fotografie níže). K připevnění diody doporučujeme použít lepící gumu na plakáty "žvýkačku". 

**Na co si dát pozor:**
* ohýbejte karton na správnou stranu (na některých dílech je pomocný nápis fold up (ohni nahoru) nebo fold down (ohni dolů) - platí dvakrát měř, jednou řež
* dodržujte sled kroků z video návodu
  * zejména u příčné přepážky mezi nohama
  * vložení serva ve správný čas


<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a>

### V čem se tedy liší TJBotCZ?

1. Díl pro uchycení reproduktoru.
2. RGB LED

Dobrý popis pro složení TJBota je také na této adrese (v angličtině):

https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/

Pro lepší výdrž doporučujeme některá místa slepit tavící pistolí. Zejména nohy a chlopně držící Raspberry Pi.

### Zapojení hardwaru

Na obrázku níže jsou popsány všechny periferie, které můžete k připojení TJBota potřebovat:
* napájení
* HDMI pro připojení monitoru
* camera
* jack audio výstup pro připojení reproduktoru
* ethernet pro připojení na internet (pokud nevyužíváte WiFi)
* USB vstupy pro připojení mikrofonu, myši a klávesnice
* piny na Raspberry Pi pro připojení RGB LED a serva

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg)


**GPIO piny**

Periferie se k Raspberry Pi připojují na jednotlivé piny. Schéma jednotlivých pinů:
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png)


**Připojení serva na GPIO piny**

Servo využívá piny celkem 3 piny:
* 5V napětí / + (fyzický pin 02)
* uzemnění / - (fyzický pin 14)
* GPIO 7 pro ovládání serva (fyzický pin 26) - lze nastavit v konfiguračním souboru TJBotCZ (config.js - viz oživení)


![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg)


**Připojení RGB LED na GPIO piny**

RGB LED využívá celkem 4 piny:
* uzemnění / - (fyzický pin 09)
* GPIO 17 / R (fyzický pin 11) - lze nastavit v konfiguračním souboru TJBotCZ (config.js - viz oživení)
* GPIO 27 / G (fyzický pin 13) - lze nastavit v konfiguračním souboru TJBotCZ (config.js - viz oživení)
* GPIO 22 / B (fyzický pin 15) - lze nastavit v konfiguračním souboru TJBotCZ (config.js - viz oživení)

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg)

