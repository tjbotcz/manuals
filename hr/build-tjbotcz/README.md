# Upute za izgradnju TJBotCZ-a i spajanje hardwarea

---
![exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _**OBAVIJEST PRIJE POČETKA IZGRADNJE**_ 

 _1. OBRATI PAŽNJU PRILIKOM SAVIJANJA KARTONA. AKO SE POGREŠNO SAVIJE, TREBATI ĆE TI LJEPILO DA TO POPRAVIŠ._
 
 _2. PRIPREMI SE NA PRLJAV POSAO. KARTON IZREZAN LASEROM OSTAVLJA CRNE MRLJE NA RUKAMA._

(Savjetujemo ti da svaki dio prebrišeš papirnatim ručnikom.)

---

### Video-upute
Ovo je izvorna video-uputa za gradnju TJBot-a, može se koristiti tijekom procesa. Ono što je jedinstveno i drugačije u spajanju je LED. TJBotCZ koristi tradicionalni RGB LED koji je samo spojen na platformu ispod gornjeg dijela (glave) - vidi sliku ispod. Za učvršćivanje LED-a preporučamo korištenje Blue Tacka ili slične ljepljive gume. 
 
**Budi pažljiv/a:** 
* pravilno savijaj karton (na nekim dijelovima postoji uputa “savij prema gore” ili "savij prema dolje” - pa bolje spriječiti, nego liječiti :) 
* drži se tijeka video upute, da izbjegneš ponovo sastavljanje     * pogotovo prilikom spajanja nogu za stabilnost i   * umetanja serva 
 
 
<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a> 
 
### Što je to drukčije kod TJBotCZ-a? 
 
1. Dio koji drži mikrofon. 
2. RGB LED 
 
Dobar vodič za sastavljanje TJBot-a se također može naći ovdje: 
 
https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/ 
 
Savjetujemo ti zalijepiti neke dijelove sa vrućim ljepilom, kako bi duže ostali spojeni. Posebice noge i neke dijelove koji drže Raspberry Pi pri dnu. 
 
### Spajanje hardwarea 
 
Slika ispod pokazuje sve dijelove za spajanje TJBot-a: 
* priključak za napajanje
* HDMI za spajanje monitora 
* kamera 
* jack audio izlaz za zvučnik 
* ethernet za spajanje na internet (u slučaju da ne koristiš WiFi) 
* USB utori za mikrofon, miš i tipkovnicu 
* pinovi na Raspberry Pi-u za spajanje RGB LEDa i serva 
 
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg) 
 
 
**GPIO (višenamjenski ulazno / izlazni ) pinovi** 
 
Svi periferni uređaji spojeni su na Raspberry Pi putem zasebnih pinova. Legenda svih pinova:  
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png) 
 
 
**spajanje serva na GPIO pinove** 
 
Servo koristi 3 pina: 
* 5V snage / + (fizički pin 02) 
* uzemljenje / - (fizički pin 14) 
* GPIO 7 za naredbe (fizički pin 26) - mora se konfigurirati u  datoteci za konfiguraciju TJbotCZ-a (config.js - vidi bring-to-life) 
 
 
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg) 
 
 
**spajanje RGB LED-a na GPIO pinove** 
 
RGB LED koristi 4 pina: 
* uzemljenje / - (fizički pin 09) 
* GPIO 17 / R (fizički pin 11) - može se konfigurirati u  datoteci za konfiguraciju (config.js - vidi bring-to-life) 
* GPIO 27 / G (v 13) - može se konfigurirati u  datoteci za konfiguraciju (config.js - vidi bring-to-life) 
* GPIO 22 / B (fizički pin 15) - može se konfigurirati u  datoteci za konfiguraciju (config.js - vidi  bring-to-life) 
 
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg) 
 
 
 


