# Prikelkite TJBot gyvenimui (Raspberry Pi)

Pasirinkite save kelią...
1. [Greitai pradėti naudojantis jau sukurtu atvaizdu](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2. [Pradėti nuo nulio kaip PRO](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3. Keletas patarimų, kurie gali praversti 
    * [Kaip kopijuoti failus iš Windows į Raspberry Pi naudojantis komandine eilute](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line)
    * [Kaip kopijuoti failus iš Mac OS į Raspberry Pi naudojant komandinę eilutę ("Mac OS")](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os)
    * [Kaip kopijuoti failus iš Rasberry Pi į Mac OS, naudojant komandinę eilutę (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-rasberry-pi-to-mac-os-using-command-line-v-mac-os)
    * [Kaip nustatyti "Raspberry Pi" IP adresą](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address)
    * [Kaip pakeisti "Raspberry Pi" talpą naudojant komandinę eilutę](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line)
    * [Garso išvesties prijungimas prie lizdo](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)
    * [Gaukite daugiau laisvos vietos "microSD" kortelėje](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)
    
## Greitai pradėti naudojantis jau sukurtu atvaizdu 

Akivaizdu, kad nekantraujate kuo greičiau paleisti ir pradėti naudoti TJBot. Dėl šios priežasties, paruošėme jau sukurtą atvaizdą, kuriame Raspbian yra iš anksto sukonfigūruotas naudojimui su TJBot.

Jums reikės:

*	Interneto ryšio, had galėtumėte atsisiųsti Raspbian OS ir SW bei įdiegtumėte atvaizdą kortelėje.
*	Kompiuterio su SD/ microSD kortelės lizdu arba  SD/microSD skaitytuvu.
*	USB klaviatūros, USB pelės.
*	LCD su HDMI prievadu ir HDMI kabeliu.


Žingsniai:
1. Atsisiųskite parengtą [TJBot atvaizdą](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) ir jį išskleiskite.

2. Atsisiųskite ir įdiekite SW, kad įdiegtumėte Raspbian atvaizdą į microSD kortelę, pvz. Etcher: https://etcher.io/ . Naudokite tai, jei norite įdiegti atsiųstą vaizdą į microSD kortelę (pasirinkite tjbotcz_lite.img failą, pasirinkite reikiamą microSD kortelę ir…	blykst!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Įstatykite iš anksto įdiegtą microSD kortelę į Raspberry-Pi, sujunkite ją su klaviatūra, pelyte arba su RJ-45 (ethernet) interneto kabeliu. Antrasis variantas yra prijungti jį per WiFi (Jei naudosite WiFi jums reikia sukonfigūruoti ryšį iš OS Raspbian GUI, Raspberry Pi prisimins šį nustatymą ateičiai). Jums reikės jungties 4 veiksmui atlikti.

4. Raspbian darbastalyje mes paruošėme scenarijų "run-me-first.sh". Paleiskite jį (dukart spustelėkite ir paleiskite terminalą). Scenarijus iš interneto atsisiųs naujausią [TJBot_lite programos] versiją (https://github.com/tjbotcz/tjbotcz_lite) ir įdiegs būtinas priklausomybes.

5. Kad galėtume kalbėtis su TJBot mes turime turėti šias IBM Cloud apibrėžtas paslaugas:

* Watson Asistentas (paslauga, skirta dialogams/pokalbiams kurti)
* Kalba į tekstą (paslauga konvertuojanti balso failus į tekstinius failus)
* Tekstas į kalbą (paslauga, konvertuojanti tekstą į balsą)
* Vizualinis atpažinimas (paslauga analizuojanti nuotraukas)

  Paslaugų teikimas remiantis vadovu nurodytu aplanke ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Jei turite visas suteiktas paslaugas, tuomet sveiki sugrįžę, tęskime toliau. Jums reikia įvesti atskirų paslaugų įgaliojimus į konfigūracijos failą (credentials.js). Kadangi įgaliojimai yra gana ilgos eilutės, geriausias būdas juos įvesti yra prisijungiant nuotoliniu būdu pie TJBot iš kompiuterio, kuriame sukūrėte  Watson paslaugas ir nukopijuojant juos. Jei esate Mac vartotojas, naudokite terminalą, jei esate Windows vartotojas, naudokite [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy yra nuotolinės prieigos programa, kurią turite įdiegti pirmiausiai. Naudodamiesi Terminal arba PuTTy prisijunkite prie TJBot (turite naudoti tą patį tinklą/WiFi kaip ir TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (įveskite TJBot IP adresą į paryškintą laukelį):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Jūsų paprašys įvesti slaptažodį. Numatytasis slaptažodis yra: **_raspberry_**.

7. Terminale (arba Windows cmd lange) eikite į aplanką su konfigūracijos failais:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
8. Sukurkite failų credentials.default.js ir config.default.js  kopijas ir atitinkamai įvardinkite jas kaip credentials.js ir config.js. Tai galite padaryti ir per terminalo cmd langą:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. Teksto redaktoriuje, pavadintame "nano", įterpkite reikiamus įgaliojimus į atskiras paslaugas.
  ```
  nano credentials.js
  ```
 Žiūrėkite žemiau esantį paveikslėlį apie vietas, kurias reikia užpildyti Watson paslaugų patvirtinimo duomenimis (neištrinkite kabučių).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Failo uždarymas ir išsaugojimas: CTRL+X, Y, Enter.
  
10. O dabar, prikelkite TJBot gyvenimui!!! Grįžkite atgal į aplanką Desktop/tjbotcz_lite ... ir pradėkime.
  TJBot yra sukonfigūruotas kalbėti vyrišku balsu ir reaguoja kai į jį kreipiamasi Michael vardu. Tai reiškia, had jis atpažins tik tuos sakinius, kuriuose yra vardas Michael. Daugiau informacijos apie TJBotCZ lite programą ir su tuo susijusius veiksmus rasite šioje nuorodoje [repository](https://github.com/tjbotcz/tjbotcz_lite).
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Pradėkite nuo nulio kaip PRO

Raspberry-Pi naudoja Raspbian kaip operacinę sistemą, kuri yra sukurta Debian Linux.
Tuomet, visas Raspbian yra microSD kortelėje. Taigi pirmiausiai turime įdiegti OS Raspbian microSD kortelę. Mums reikės:

*	Interneto ryšio, kad galėtume atsisiųsti Raspbian OS ir SW bei įdiegti atvaizdą kortelėje.
*	kompiuteris su SD/ microSD kortelės lizdu arba SD/microSD skaitytuvu
*	USB klaviatūra, USB pelė
*	LCD su HDMI prievadu ir HDMI kabeliu.

Žingsniai:
1. Atsisiųskite Raspbian OS https://www.raspberrypi.org/downloads/ .

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Atsisiųskite ir įdiekite SW, kad įdiegtumėte vaizdą Raspbian, pvz. Etcher https://etcher.io/ ir įdiekite Raspbian OS į microSD kortelę (spustelėkite/pasirinkite atsisiųstą .img failą, tuomet, prijungiate SD kortelę, ir…Blykst!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Įstatykite įrašytą microSD kortelę į Raspberry-Pi, prijunkite ją su klaviatūra, pele arba su RJ-45 (Ethernet) interneto kabeliu. Antras būdas yra prijungti jį per WiFi (Jei naudosite WiFi kuris yra naudojamas OS Raspbian GUI konfigūravimui, Raspberry Pi prisimins šį nustatymą ir ateityje). Jums reikės ryšio 5 žingsniui atlikti.

4. Leiskite Raspberry-Pi SSH prisijungti, kad vėliau galėtumėte tęsti su Raspberry-Pi naudodamiesi nuotoliniu ryšiu per terminalą arba PuTTY (Windows). Terminale rašykite:
```
sudo raspi-config
```
Atsidarys meniu.
Pasirinkite “Interfacing Options”.
Pasirinkite ir įjunkite “SSH”.
5. Atidarykite terminalą ir paleiskite:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
Ši komanda atsiųs scenarijų iš serverio, kuris terminalo lange paleis interaktyvų vadovą. Su šiuo vadovu jūs sukonfigūruosite Raspberry Pi skirtą TJBot:

* TJBot vardas (palikite raspberrypi)  - (Enter)
* IPv6 (išjungti) - (Y)
* Google DNS (įjungti) - (Y)
* nustatymai vietos (kalba) (Y)
* atnaujinkite OS Raspbianu (Y)
* atnaujinkite Node.js į naujesnę versiją (N)
* prijunkite kamerą (Y)
* atsisiųskite originalų TJBot ir pabandykite scenarijus (Enter)
* garso išvesties konfigūravimas (palikite prievadą su įjungtu jack-audio) (N)
* perkraukite (Y)

6. Įdiekite node.js versiją 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. Terminale atidarykite aplanką "Desktop":
```
cd Desktop
```
8. Įdiekite vieną iš TJBot programų (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<name of tjbotcz program>.git
```
9. Terminale atidarykite naujai sukurtą aplanką “tjbotcz_lite”, "tjbotcz" arba tjbotcz_iot":
```
cd <name of the folder>
```
10. Atsisiųskite priklausomybes, apibrėžtas failų pakete package.json kartu su programa atsisiųsta atliekant 8 žingsnį:
```
npm install
```
11. Norėdami kalbėtis su TJBot, turime turėti toliau įvardijamas paslaugas apibrėžtas IBM Cloud:

* Watson Asistentas (paslauga, skirta dialogams/pokalbiams kurti)
* Kalba į tekstą (paslauga pakeičianti balso failą į tekstinį failą)
* Tekstas į kalbą (paslauga keičianti tekstą į balsą)
* Vizualinis atpažinimas (paslauga analizuojanti nuotraukas)

  Paslaugų teikimas pagal vadove nurodytą informaciją aplanke ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. Jei turite visas reikalingas paslaugas, tuomet sveiki sugrįžę, galime tęsti toliau. Jums reikia įvesti atskirų paslaugų įgaliojimus į konfigūracijos failą (credentials.js). Kadangi įgaliojimai yra gana ilgos eilutės, geriausias būdas juos įvesti yra prisijungiant nuotoliniu būdu prie TJBot iš kompiuterio, kuriame sukūrėte Watson paslaugas ir nukopijuoti-perkelti jas. Jei esate Mac vartotojas, nuadokite terminalą, jei naudojate Windows, naudokite [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy yra nuotolinės prieigos programa, kurią turite įdiegti pirmiausiai. Naudodamiesi Terminalu arba PuTTy prisijunkite prie TJBot (turite būti tame pačiame tinkle/WiFi kaip ir TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (įveskite TJBot IP adresą į paryškintą laukelį):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Jūsų bus paprašyta įvesti slaptažodį. Numatytasis slaptažodis yra: **_raspberry_**.

13. Terminale (arba cmd lange Windows) eikite į aplanką su konfigūracijos failais:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
14. Sukurkite failų credentials.default.js ir config.default.js kopiją ir atitinkamai pavadinkite juos credentials.js ir config.js. Tai galima atlikti ir nuotoliniu būdu per terminalą/CMD langą:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. Teksto redaktoriuje pavadintame nano, įterpkite reikiamus įgaliojimus atskiroms paslaugoms.
  ```
  nano credentials.js
  ```
  Žiūrėkite žemiau esantį paveikslėlį norėdami sužinoti vietas, kurias reikia užpildyti Watson paslaugų patvirtinimo duomenimis (neištrinkite kabučių).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Failo uždarymas ir išsaugojimas: CTRL+X, Y, Enter.
  
16. O dabar, prikelkite TJBot gyvenimui !!! Grįžkite atgal į aplanką Desktop/tjbotcz_lite ... ir tęskime.
  TJBot yra sukonfigūruotas kalbėti vyrišku balsu ir reaguoja į vardą Michael. Tai reiškia , had jis atpažins tik tuos sakinius, kuriuose yra vardas Michael.   ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Galintys praversti patarimai

###  Kaip kopijuoti failus iš "Windows" į "Raspberry Pi" naudojant komandinę eilutę. Atidarykite CMD eilutę ir adresą. Ten rasite failą, kurį norite nukopijuoti (cd = pakeisti katalogą).  Tada naudokite kitą komandų eilutę, kur pirmiausia turite patikrinti, ar PuTTY jau yra įdiegtas, ir patikrinkite, ar C: \ Program Files \ PuTTY \ pscp.exe. veikia. Toliau įvardijamas failas: “file.txt” yra skirtas įvardinti kopijuojamus failus, todėl jūsų “your_pi” turi būti pakeistas į Raspberry Pi IP addresą ( Tai turi būti atliekama tame pačiame tinkle):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### Kaip kopijuoti failus iš Mac OS į Raspberry Pi naudojant komandinę eilutę ("Mac OS")
Atidarykite CMD eilutę ir adresatą. Ten yra failas, kurį norite nukopijuoti (cd = pakeisti katalogą). Tada naudokite kitą komandinę eilutę, kurioje "file.txt" yra skirtas įvardinti kopijuojamus failus, todėl jūsų "your_pi" turi būti pakeistas į Raspberry Pi IP adresą (tai turi būti atliekama tame pačiame tinkle):

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```


### Kaip kopijuoti failus iš Rasberry Pi į Mac OS, naudojant komandinę eilutę (v Mac os)
Jei esate prisijungę prie TJBot per SSH, iš pradžių atsijunkite:

```
logout
```

Terminale "Mac OS" naudokite komandą nukopijuoti failams:

```
scp <username na Raspberry Pi>@<ip adresa Raspberry Pi>:/<full path to file on Raspberry pi> <full path to where files is to be saved on Mac OS>
```

Pavyzdžiui:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

Jūsų paprašys Raspberry Pi slaptažodžio.


### Kaip nustatyti Raspberry Pi IP adresą
Prisijunkite prie Raspberry Pi per SSH arba "PuTTy". Tada naudokite komandą:

```
sudo nano /etc/dhcpcd.conf
```

Atsidariusiame faile pakeiskite dalį su statiniu adreso nustatymu ir įveskite teisingas reikšmes (IP adresas, maršrutizatoriaus IP adresas).



### Kaip pakeisti Raspberry Pi garso lygį naudojant komandinę eilutę
Prisijunkite per SSH arba PuTTY prie Raspberry Pi. Kita kodo eilutė pakeis jo garso lygį iki 90%. Garsa lygis turėtų būti keičiamas nelinijiniu būdu, todėl skirtumas tarp 90% ir 95% yra pastebimas.

```
amixer  sset PCM,0 90%
```
Kitas variantas yra sukurti trumpinį, kuris gali pakeisti garso lygį. Nano redaktoriuje atidarykite .bashrc failą:

```
nano ~/.bashrc
```

Ir failo pabaigoje pridėkite

```
# Increase volume by 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Decrease volume by 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
Iš naujo paleiskite Raspberry-Pi. Tuomet galite tiesiog parašyti  `volup`  arba  `voldown`  terminale ir garsumas keisis į viršų/žemyn per 5%.



### Garso išvesties nustatymas prie lizdo
Kartais jūs negalite išgirsti TJBot net jei garsumo lygis yra maksimalus. Tokiu atveju, greičiausiai garsas sklinda į HDMI, o ne į prijungtą garsiakalbį (per lizdą). Norėdami nustatyti išėjimą į lizdo jungtį, naudokite šiuos parametrus:


```
sudo amixer cset numid=3 1
```
Paskutinis numeris nurodo išėjimą (0 = automatinis, 1 = lizdas, 2 = HDMI)


### Gaukite daugiau laisvos vietos microSD kortelėje
Jei turite 16 GB microSD kortelę, jums jos turėtų pakakti. Tačiau, jei turite 8GB kortelę, po įdiegimo, jums liks tik maždaug 2 GB laisvos vietos. Norėdami atlaisvinti daugiau vietos, galite pašalinti Wolfram ir LibreOffice. Šių programų darbui su TJBot jums nereikės. Sutaupysite 1 GB laisvos vietos.

Norėdami pašalinti programas:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

---
