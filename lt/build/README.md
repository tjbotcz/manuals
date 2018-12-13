# TJBot kūrimo ir įrangos sujungimo vadovas

---
![šauktukas](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _**PRANEŠIMAS PRIEŠ PRADŽIĄ**_ 

 _1. ATSARGIAI SULANKSTYKITE KARTONĄ. JEI SULANKSTYSITE NETEISINGAI, JUMS PRIREIKS KLIJŲ JOG TAI SUTVARKYTUMĖTE._
 
 _2. PASIRUOŠKITE IŠSIPURVINTI. KARTONAS PALIEKA JUODAS DĖMES ANT RANKŲ._

(Rekomenduojame kiekvieną dalį nuvalyti popierine servetėle.)
---

### Vaizdo vadovas
Čia yra originalus vaizdo vadovas, skirtas TJBot sukurti. Jūs galite jį sekti. Vienintelis  didelis skirtumas yra LED prijungimas. TJBot naudoja tradicinį RGB LED, kuris tiesiog padėtas ant platformos po viršutine dalimi (galva) - žr. toliau pateiktas nuotraukas. Norėdami sureguliuoti LED,mes siūlome naudoti "Blue Tack" arba panašią lipnią gumą.
**Būkite atsargus:**
* Lankstykite kartoną tinkamu būdu (ant kai kurių dalių, nurodytos instrukcijos "fold up" arba "fold down" - taigi geriau būti atsargiam :)
* laikykitės tvarkos nurodytos vaizdo vadove, kad po to neturėtumėte visko perdaryti.
  * Ypač prijungiant kojas stabilumui užtikrinti
  * įterpiant servo


<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a>

### Taigi kuo TJBot skiriasi?

1. Dalis kurioje laikomas garsiakalbis.
2. RGB LED

Geras gidas TJBot surinkimui yra čia:

https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/

Ilgaamžiškumui užtikrinti, rekomenduojame kai kurias dalis suklijuoti klijų-ginklu. Ypač kojas ir dalis laikančias Raspberry Pi apačioje.

### Įrenginio prijungimas

Žemiau pateiktame paveikslėlyje parodytos visos priemonės, kurių gali prireikti TJBot:
* maitinimo adapteris
* HDMI prijungimui prie kompiuterio ekrano
* fotoaparatas
* Lizdo garso išvestis garsiakalbiui
* "Ethernet" prisijungimas prie interneto (jei nenaudojate "Wi-Fi")
* USB lizdai mikrofonui, pelėms ir klaviatūrai
* Raspberry Pi jungtys, skirtos prijungti RGB LED ir servo


![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg)


**GPIO jungtys**

Periferiniai įrenginiai prie Raspberry Pi yra prijungti per atskiras jungtis. Čia yra legenda visoms jungtims:
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png)


**Prijungimas prie GPIO jungčių**

Servo naudoja 3 kaiščius:
* 5V galia / + (fizinis kaištis 02)
* žemė / - (fizinis kaištis 14)
* GPIO 7 komandoms (fizinis kaištis 26) - gali būti sukonfigūruotas (config.js - see bring-to-life)


![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg)


** RGB LED prijungimas prie GPIO jungčių**

RGB LED naudoja 4 kaiščius:
* žemė / - (fizinis kaištis 09)
* GPIO 17 / R (fizinis kaištis 11) - gali būti sukonfigūruotas (config.js - see bring-to-life)
* GPIO 27 / G (fizinis kaištis 13) - gali būti sukonfigūruotas (config.js - see bring-to-life)
* GPIO 22 / B (fizinis kaištis 15) - gali būti sukonfigūruotas (config.js - see bring-to-life)

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg)


