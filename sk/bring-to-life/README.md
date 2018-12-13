# Oživenie TJBota na Raspberry Pi

Zvoľte si postup...
1. [Rýchle oživenie z pripraveného obrázku](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2. [Začnite od piky ako profík](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3. Pár návodov, ktoré sa môžu hodiť 

    * [Ako skopírovať súbry z Windowsu na Raspberry Pi použitím príkazového riadku (vo Windows)]https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line)
    * [Ako skopírovať súbory z Mac OS na Raspberry Pi použitím príkazového riadku (v Mac OS)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os)
    * [Ako skopírovať súbory z Rasberry Pi na Mac OS použitím príkazového riadku (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-rasberry-pi-to-mac-os-using-command-line-v-mac-os)
    * [Ako nastaviť pevnú IP adresu na Raspberry Pi](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address)
    * [Ako ovládať hlasitosť zvukového výstupu Raspberry Pi použitím príkazového riadku](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line)
    * [Nastavenie audio výstupu na jack](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)
    * [Ako získať viac miesta na microSD karte ](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)
    
## Rýchle oživenie z pripraveného obrázku

Určite sa už nemôžete dočkať chvíle, keď TJBota oživíte. Preto sme pripravili hotový obrázok (image), na ktorom je predkonfigurovaný Raspbian, pripravený pre spustenie TJBota.

Budete potrebovať:

*	pripojenie k internetu, aby ste si mohli stiahnuť Raspbian OS
*	počítač so slotom na SD kartu a adaptér na microSD karty alebo čítačku SD/microSD kariet
*	USB klávesnicu, USB myš
*	LCD so vstupom HDMI a kábel HDMI.


Postup:
1. Stiahnite si predpripravený image [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) a rozbaľte ho.

2. Stiahnite si a nainštalujte SW na inštaláciu Raspbianu, napr. Etcher: https://etcher.io/ . Nainštalujte Raspbian OS na kartu microSD (vyberte stiahnutý súbor tjbotcz_lite.img, zvoľte pripojenú microSD kartu, a…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Vložte nainštalovanú microSD kartu do Raspberry-Pi, pripojte k nemu HDMI monitor, klávesnicu, myš a RJ-45 (ethernet) kábel na internet. Druhou možnosťou je pripojiť sa na internet cez WiFi (ak používate WiFi, musíte v grafickom prostredí OS Raspbian nastaviť pripojenie k Wifi, Raspberry Pi si toto pripojenie bude pamätať). Pripojenie na internet budete potrebovať pre krok 4.

4. Na desktope Raspbian máte pripravený script "run-me-first.sh".  Spustite ho (dvojklik a execute in terminal). Script vám stiahne z internetu najnovšiu verziu programu [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) a nainštaluje potrebné závislosti.

5. Na to, aby bolo možné s TJBotom konverzovať, bude potrebné mať pripravené nasledovné služby v IBM Cloud:

* Watson Assistant (službu na vytváranie dialógov/chatov)
* Speech to Text (službu prepisujúcu hlasový súbor do textového súboru)
* Text to Speech (službu prevádzajúcu text na zvuk)
* Visual Recognition (službu analyzujúcu obrázky)

  Služby uvediete do prevádzky podľa návodu v sekcii ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Ak už máte všetky služby pripravené, vitajte späť a môžeme pokračovať. Teraz budete musieť zadať prihlasovacie údaje k jednotlivým službám do konfiguračného súboru (credentials.js). Keďže sú prihlasovacie údaje dosť dlhé, najlepšie je prihlásiť sa k TJBotovi na diaľku, z počítača, kde ste si vytvárali služby Watson a skopírovať ich. Ak používate Mac OS, použijete Terminal, ak používate Windows, použijete [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy je program pre vzialený prístup, ktorý si musíte najskôr nainštalovať. Použite teda Terminal alebo PuTTy a pripojte sa na TJBot (váš počítač musí byť na rovnakej sieti/WiFi ako TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (do zvýrazneného políčka zadajte IP adresu TJBota):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Dostanete výzvu na zadanie hesla. Východiskové heslo je: **_raspberry_**.

7. V otvorenom termináli (alebo cmd okne vo Windows) prejdite na adresár, kde sú uložené konfiguračné súbory TJBota:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
8. Vytvorte si kópiu súboru credentials.default.js a súboru config.default.js a kópie pomenujte credentials.js a config.js. Môžete to urobiť na diaľku cez príkazový riadok (terminál/CMD okno):
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. V editore nano (textový editor v Rasbiane) vložte potrebné prihlasovacie údaje k jednotlivým službám.
  ```
  nano credentials.js
  ```
  Na obrázku nižšie sú vyznačené miesta, kde je potrebné doplniť platné prihlasovacie údaje z IBM Watson služieb (jednoduché úvodzovky nevymazávajte).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Uloženie a zatvorenie editoru: CTRL+X, Y, Enter.
  
10. A teraz TJBota oživte !!! Vráťte sa do adresára Desktop/tjbotcz_lite ... a ide sa na to! 
  TJBot je nakonfigurovaný tak, aby dokázal hovoriť mužským hlasom a aby reagoval na meno Michael (vyslovuj "Majkl"). Znamená to, že bude rozpoznávať jedine vety, ktoré obsahujú slovo Michael. Pre viac informácii o TJBotCZ lite programe a ako s ním pracovať viď [repository](https://github.com/tjbotcz/tjbotcz_lite).
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Začnite od piky ako profík   

Raspberry-Pi využíva ako operačný systém Raspbian, ktorý je postavený na Debian Linuxe.
Celý Raspbian je potom na karte microSD. Najskôr teda musíme na kartu microSD nahrať OS Raspbian. Budeme k tomu potrebovať:

*	pripojenie na internet, aby ste si mohli stiahnuť Raspbian OS 
*	počítač so slotom na SD kartu a adaptér na microSD karty alebo čítačku kariet SD/microSD
*	USB klávesnicu, USB myš
*	LCD so vstupom HDMI a kábel HDMI.

Postup:
1. Stiahnite si Raspbian OS z https://www.raspberrypi.org/downloads/ .

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Stiahnite si a nainštalujte SW na inštaláciu obrázku Raspbianu, napr. Etcher https://etcher.io/ , potom nainštalujte Raspbian OS na kartu microSD (vyberte stiahnutý súbor .img, zvoľte pripojenú SD kartu, a…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Vložte nainštalovanú kartu microSD do Raspberry-Pi, pripojte k nemu HDMI monitor, klávesnicu a myš a eventuálne RJ-45 (ethernet) kábel na internet. Druhou možnosťou je pripojiť sa na internet cez WiFi (ak používate WiFi, musíte v grafickom prostredí OS Raspbian nastaviť pripojenie k Wifi, Raspberry Pi si toto pripojenie bude pamätať). 

4. Na Raspberry-Pi povoľte pripojenie SSH, aby bolo neskôr možné pripojiť sa na Raspberry-Pi na diaľku cez terminál alebo cez PuTTY (Windows). Do Terminálu napíšte:
```
sudo raspi-config
```
Otvorí sa menu.
Zvoľte “Interfacing Options”.
Zvoľte “SSH” a povoľte ho.
5. Otvorte Terminál a spusťte nasledovný príkaz:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
Tento príkaz si stiahne zo serveru skript, ktorý spustí interaktívneho sprievodcu fungujúceho v terminále. Pomocou tohto sprievodcu nakonfigurujete Raspberry Pi pre TJBot:

* TJBot name (ponechajte raspberrypi)  - (Enter)
* nastavenie IPv6 (zvoľte možnosť vypnúť) - (Y)
* nastavenie Google DNS (zvoľte možnosť povoliť) - (Y)
* lokálne nastavenie (jazyk) (Y)
* update na novšiu verziu OS Raspbianu (Y)
* update na novšiu verziu Node.js (N)
* nastavenie pripojenia kamery (Y)
* stiahnutie pôvodného programu TJBota a testovacích scenárov(Enter)
* konfigurácia zvukového výstupu (nechajte port pre jack-audio povolený) (N)
* reboot (Y)

6. Nainštalujte node.js vo verzii 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. V termináli otvorte adresár Desktop:
```
cd Desktop
```
8. Nainštalujte niektorý z programov pre TJBotCZ (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<name of tjbotcz program>.git
```
9. V terminále otvorte novovytvorený adresár “tjbotcz_lite”, "tjbotcz" alebo tjbotcz_iot":
```
cd <name of the folder>
```
10. Dotiahnite potrebné závislosti programu tak, ako sú definované v súbore package.json, ktorý ste nainštalovali z gitu v kroku 8:
```
npm install
```
11. Na to, aby bolo možné s TJBotom konverzovať, bude potrebné mať pripravené nasledovné služby v IBM Cloud:

* Watson Assistant (službu na vytváranie dialógov/chatov)
* Speech to Text (službu prepisujúcu hlasový súbor do textového súboru)
* Text to Speech (službu prevádzajúcu text na zvuk)
* Visual Recognition (službu analyzujúcu obrázky)

  Služby uvediete do prevádzky podľa návodu v sekcii ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. Ak už máte všetky služby pripravené, vitajte späť a môžeme pokračovať. Teraz budete musieť zadať prihlasovacie údaje k jednotlivým službám do konfiguračného súboru (credentials.js). Keďže sú prihlasovacie údaje dosť dlhé, najlepšie je prihlásiť sa k TJBotovi na diaľku, z počítača, kde ste si vytvárali služby Watson a skopírovať ich. Ak používate Mac OS, použijete Terminal, ak používate Windows, použijete [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy je program pre vzdialený prístup, ktorý si musíte najskôr nainštalovať. Použite teda Terminal alebo PuTTy a pripojte sa na TJBot (váš počítač musí byť na rovnakej sieti/WiFi ako TJBot): 

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (do zvýrazneného políčka zadajte IP addresu TJBota):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Dostanete výzvu na zadanie hesla. Východiskové heslo je: **_raspberry_**.

13. V otvorenom terminále (alebo cmd okne vo Windows) prejdite na adresár, kde sú uložené konfiguračné súbory TJBota:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
14. Vytvorte si kópiu súboru credentials.default.js a súboru config.default.js a kópie pomenujte credentials.js a config.js. Môžete to urobiť na diaľku cez príkazový riadok (terminál/CMD okno):
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. V editore nano (textový editor v Rasbiane) vložte potrebné prihlasovacie údaje k jednotlivým službám.
  ```
  nano credentials.js
  ```
   Na obrázku nižšie sú vyznačené miesta, kde je potrebné doplniť platné prihlasovacie údaje z IBM Watson služieb.
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Uloženie a zatvorenie editoru: CTRL+X, Y, Enter.
  
16. A teraz TJBota oživte !!! Vráťte sa do adresára Desktop/tjbotcz_lite ... a ide sa na to! 
  TJBot je nakonfigurovaný tak, aby dokázal hovoriť mužským hlasom a aby reagoval na meno Michael (vyslovuj "Majkl"). Znamená to, že bude rozpoznávať jedine vety, ktoré obsahujú slovo Michael.
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Pár návodov, ktoré sa môžu hodiť 

### Kopírovanie z Windows na Raspberry Pi použitím príkazového riadku 
Otvorte si CMD line a adresár, kde máte súbor, ktorý chcete kopírovať (cd = change directory). Potom použite nasledujúci príkaz, kde skontrolujete, či už máte nainštalované PuTTY a či platí cesta C:\Program Files\PuTTY\pscp.exe. Pomenovanie “file.txt” je názov kopírovaného súboru a namiesto “your_pi” dosaďte IP adresu vášho Raspberry Pi (musí byť na rovnakej sieti):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### Kopírovanie z Mac OS na Raspberry Pi použitím príkazového riadku (v Mac OS)
Otvorte terminál a adresár, kde máte súbor, ktorý chcete kopírovať (cd = change directory). Potom použite nasledujúci príkaz, kde “file.txt” je názov kopírovaného súboru a namiesto “your_pi” dosaďte IP adresu vášho Raspberry Pi (musí byť na rovnakej sieti):

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```


### Kopírovanie z Rasberry Pi do Mac OS použitím príkazového riadku (v Mac Os)
Pokiaľ ste v SSH prihlásený na TJBot, tak sa najskôr odhláste:

```
logout
```

V Terminále na Mac OS napíšte príkaz pre kopírovanie:

```
scp <username na Raspberry Pi>@<ip adresa Raspberry Pi>:/<celá cesta k súboru na Raspberry pi> <celá cesta k uloženiu na Mac OS>
```

Príklad:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

Potom dostanete výzvu na zadanie hesla do Raspberry Pi.


### Nastavenie pevnej IP adresy na Raspberry Pi
Pripojte sa cez SSH alebo PuTTy na Raspberry Pi. Potom použite príkaz:

```
sudo nano /etc/dhcpcd.conf
```

V otvorenom súbore odkomentujte časť s nastavením statickej adresy a zadajte správne hodnoty (IP adresu, IP adresu routera).



### Hlasitosť Raspberry Pi použitím príkazového riadku 
Pripojte sa cez SSH alebo PuTTY na Raspberry Pi.  Nasledujúci kód nastaví hlasitosť na 90%. Zdá sa, že hlasitosť sa zvyšuje nelineárne, takže rozdiel medzi 90 % a 95 % je markantný.

```
amixer  sset PCM,0 90%
```

ďalšou možnosťou je vytvoriť si alias skratku, ktorou sa bude meniť hlasitosť. V nano editore si otvorte súbor .bashrc:

```
nano ~/.bashrc
```

a na koniec súboru pridajte 

```
# Increase volume by 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Decrease volume by 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
Reštartujte Raspberry-Pi. Potom stačí v príkazovom riadku napísať `volup`  alebo  `voldown` a hlasitosť sa vždy zvýši/zníži o 5%.



### Nastavenie audio výstupu na jack
Niekedy sa stáva, že TJBota nepočujete, aj keď máte hlasitosť nastavenú na maximum. S najväčšou pravdepodobnosťou totiž audio smeruje do HDMI a nie do pripojeného reproduktoru (cez jack). Na nastavenie audio výstupu na jack, použite nasledujúci príkaz:

```
sudo amixer cset numid=3 1
```
Posledné číslo udáva audio výstup (0=auto, 1=jack, 2=HDMI)


### Uvoľnenie miesta na karte microSD
Pokiaľ máte microSD kartu 16GB, malo by všetko prebiehať hladko. Ak máte kartu 8GB, s ktorou sa TJBot bežne dodáva, tak vám po inštalácii zostane približne 2GB. Ideálni kandidáti na zmazanie sú Wolfram a LibreOffice, získate tak viac miesta. Ani jeden z týchto programov nebudete s TJBotom potrebovať. Uvoľní sa vám približne 1GB miesta na karte.

Na vymazanie programov stačí napísať:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

---
