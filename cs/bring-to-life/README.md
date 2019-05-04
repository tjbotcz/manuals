# Oživujeme TJBota na Raspberry-Pi
Vyberte si svoji cestu...
1. [Rychlé oživení z předpřipravené image](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#rychl%C3%A9-o%C5%BEiven%C3%AD-z-p%C5%99edp%C5%99ipraven%C3%A9-image)
2. [Oživení hezky od píky](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#o%C5%BEiven%C3%AD-hezky-od-p%C3%ADky)
3. Pár návodů, které se můžou hodit
    * [Kopírování z Windows na Raspberry Pi přes příkazovou řádku (ve Windows)](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#kop%C3%ADrov%C3%A1n%C3%AD-z-windows-na-raspberry-pi-p%C5%99es-p%C5%99%C3%ADkazovou-%C5%99%C3%A1dku)
    * [Kopírování z Mac OS na Raspberry Pi přes příkazovou řádku (v Mac OS)](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#kop%C3%ADrov%C3%A1n%C3%AD-z-mac-os-na-raspberry-pi-p%C5%99es-p%C5%99%C3%ADkazovou-%C5%99%C3%A1dku-v-mac-os)
    * [Kopírování z Rasberry Pi do Mac OS přes příkazovou řádku (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#kop%C3%ADrov%C3%A1n%C3%AD-z-rasberry-pi-do-mac-os-p%C5%99es-p%C5%99%C3%ADkazovou-%C5%99%C3%A1dku-v-mac-os)
    * [Nastavení pevné IP adresy na Raspberry Pi](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#nastaven%C3%AD-pevn%C3%A9-ip-adresy-na-raspberry-pi)
    * [Ovládání hlasitosti zvukového výstupu Raspberry Pi z příkazové řádky](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#hlasitost-raspberry-pi-z-p%C5%99%C3%ADkazov%C3%A9-%C5%99%C3%A1dky)
    * [Nastavení audio výstupu na jack](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#nastaven%C3%AD-audio-v%C3%BDstupu-na-jack)
    * [Uvolnění místa na SD kartě](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#uvoln%C4%9Bn%C3%AD-m%C3%ADsta-na-sd-kart%C4%9B)
    * [Klonování microSD Card](https://github.com/tjbotcz/manuals/tree/master/cs/bring-to-life#klonov%C3%A1n%C3%AD-microsd-karty-na-macos)
    * [Jak na dálku editovat soubory na TJBot.CZ přímo z VS Codu](https://github.com/tjbotcz/manuals/blob/master/cs/bring-to-life/README.md#jak-vzd%C3%A1len%C4%9B-editovat-soubory-na-tjbotovi-p%C5%99%C3%ADmo-z-vs-code)
    *  [Jak nastavit IP tlačítko na TJBotCZ](https://github.com/tjbotcz/manuals/blob/master/cs/bring-to-life/README.md#jak-nastavit-ip-tla%C4%8D%C3%ADtko)
	
	##  Rychlé oživení z předpřipravené image
	 Samozřejmě chcete, aby váš TJBot už fungoval. Proto jsme pro vás předem připravili image, kde jsme předem nastavili Raspbian for TJBot.CZ.
	 
	 
	 Budete k tomu potřebovat:
	   * připojení k internetu pro stažení Raspbian OS a SW pro nainstalování image na kartu.
      * počítač vybavený SD kartou, nebo micro SD čtečkou
      * USB klávesnice, USB myš
	   * LCD s HDMI portem a HDMI kabelem
	
	Kroky:
	
1. Stáhněte si předem připravenou [image TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) a rozbalte to.
	 
2. Stáhněte si a nainstalujte SW na instalaci image Raspbianu, např. Etcher: https://etcher.io/ a nainstalujte Raspbian OS na microSD kartu (vyberte stáhnutý tjbotcz_lite.img soubor, vyberte připojenou SD kartu , a…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Vložte nainstalovanou microSD kartu do Raspberry-Pi, připojte k němu HDMI monitor, klávesnici, myš a RJ-45 (ethernet) kabel na internet. Druhou možnosti je připojit se k internetu přes WiFi - pak musíte v grafickém prostředí OS Raspbianu nastavit připojení k WiFi, Raspberry Pi si toto připojení bude pamatovat. Připojení k internetu budete potřebovat pro krok 4.

4. Na Raspbian Desktop jsme připravili skript "run-me-first.sh". Spusťte ho ( dvouklikem). Pokud nepracujete přímo na Raspberry-Pi, ale jste k němu připojeni vzáleně přes terminál, tak můžete využít tento skript:

```
ssh pi@<IP Adresa> 'bash -s' < run-me-first.sh
```

Skript stáhne nejnovější verzi [TJBotCZ_lite programu](https://github.com/tjbotcz/tjbotcz_lite) z internetu a nainstaluje všechno potřebné.

5. Abychom mohli s TJBotem konverzovat, je potřeba mít připravené následující služby v IBM Cloudu:

* Watson Assistant (služba pomocí které se vytváří dialogy pro chat)
* Speech to Text (služba převádějící zvukový záznam na text)
* Text to Speech (služba převádějící text na zvuk)
* Visual Recognition (služba analyzující obrázky)

  Služby si zprovozněte podle návodu v sekci ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/cs/watson-services/README.md).

6. Pokud máte všechny služby připravené, tak vítejte zpět a můžeme pokračovat. Musíme zadat přihlašovací údaje k jednotlivým službám do konfiguračního souboru (credentials.js). Nejjednodušší cesta vede přes konfigurační stránku TJBota, kterou jsme připravili. Do prohlížeče zadejte: 
  
  ```
  http://<IP ADDRESS OF TJBOT>/
  ```
  ...a vyplňte potřebné údaje.
  
 (Musíte být na stejné sít jako je TJBot, jinak Vám stránka nepůjde otevřít.)
  

7. A teď, probuďte vašeho TJ Bota k životu!!! Abyste to mohli udělat, připojte se na dálku k 
k TJ Botovi, přesměrujte se na programovou složku a spusťte program. Můžete začít! 

   a. Pokud používáte Mac,  používejte terminál, pokud používáte Windows, použijte [PuTTy]( https://www.chiark.greenend.org.uk/-sqtatham/putty/latest.html). PuTTy je program, který umožňuje přístup na dálku a vy ho musíte nejdříve nainstalovat. Pomocí Terminálu nebo in PuTTY se připojíte k TJ Botovi (potřebujete být na stejné síti/WiFi jako TJBot): 
   MacOS:

   ```
   ssh pi<ipadresa>
   ```

   Windows( vložte IP adresu TJ do vyznačeného pole): 
   ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)
   
   Budete požádáni o heslo. Výchozí heslo je **_raspberry_**.
   
   b. přejděte zpět k folder Desktop/tjbotcz_lite 
   
   ```
   cd Desktop/tjbotcz_lite
   ```
   
   c. .... a spusťte program.
   
   ```
   sudo node tjbotcz_lite.js
   ```
   
   TJBotCZ je nastavený tak, aby mluvil mužským hlasem a reagoval na jméno Michael. 
   To znamená, že rozpozná pouze věty, které obsahují slovo Michael. Pro více informací o programu TJ a jak ho používat, navštivte tento [odkaz](https://github.com/tjbotcz/tjbotcz_lite). 
  
  ![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Oživení hezky od píky 


Raspberry-Pi využívá jako operační systém Raspbian, který je postaven na Debian Linuxu.
Celý Raspbian je pak na microSD kartě. Napřed tedy musíme na microSD kartu nahrát OS Raspbian. Budete k tomu potřebovat:

* připojení k internetu, aby sis mohl stáhnout Raspbian OS
* počítač se slotem na SD kartu a adaptér na microSD karty nebo čtečku SD/microSD karet
* USB klávesnici, USB myš
* LCD s HDMI vstupem a HDMI kabel

Postup:
1. Stáhněte si Raspbian OS z https://www.raspberrypi.org/downloads/

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Stáhněte si a nainstalujte SW na instalaci image Raspbianu - máme rádi [Etcher](https://www.balena.io/etcher/), který je jednoduchý a snadno se používá. Nainstalujte pomocí programu Etcher Raspbian OS na microSD kartu (vyberte stáhnutý .img soubor, vyberte připojenou SD kartu , a…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Vložte nainstalovanou microSD kartu do Raspberry-Pi, připojte k němu HDMI monitor, klávesnici, myš a eventuálně RJ-45 (ethernet) kabel na internet. Druhou možnosti je připojit se k internetu přes WiFi - pak musíte v grafickém prostředí nakonfigurovat WiFi (tj. připojit se) a Raspberry Pi si nastavení WiFi bude pamatovat i při dalším spuštění). Připojení k internetu budete potřebovat v kroku 5.

4. Na Raspberry-Pi je potřeba povolit SSH připojení, abychom se mohlí k TJBotovi připojit vzdáleně přes Terminal (Mac OS) nebo PuTTy (Windows). V Terminálu na Raspberry Pi napište: 
```
sudo raspi-config
```
Otevře se vám menu.
Vyberte “Interfacing Options”.
Vyberte “SSH” a povolte jej.

5. Otevřete Terminal na Raspberry Pi a spusťte následující příkaz:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
Tento příkaz si stáhne ze serveru skript, který spustí interaktivního průvodce běžícího v terminálu, pomocí kterého nakonfigurujete Raspberry Pi, aby bylo připraveno pro použití s TJBotem :

* TJBot name (ponechte raspberrypi)  - (Enter)
* nastavení  IPv6 (zvolte možnost vypnout) - (Y)
* nastavení google DNS (zvolte možnost povolit) - (Y)
* nastavení locale (jazyka) (Y)
* update OS Raspbianu (Y)
* update na novější verzi Node.js (N)
* nastavení připojení kamery (Y)
* stažení původního programu TJBota a testovacích scénářů (Enter)
* konfigurace zvukového výstupu (nechte port pro jack-audio povolený) (N)
* reboot (Y)

6. Nainstalujte node.js ve verzi 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```

7. Nainstalujte MPG123 přehrávač, abyste mohli přehrávat mp3 soubory (hlasový výstup TJBota).
```
sudo apt-get install mpg123
```

8. V terminálu otevřete adresář Desktop:
```
cd Desktop
```
9. Nainstalujte některý z programů pro TJBota (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<název_programu>.git
```
10. V terminálu otevřete nově vytvořený adresář “tjbotcz_lite”, "tjbotcz" nebo tjbotcz_iot":
```
cd <název_adresáře>
```
11. Dotáhněte potřebné závislosti programu, tak jak jsou definované v souboru package.json, který jste nainstalovali z gitu v kroku 8:
```
npm install
```
12. Abychom mohli s TJBotem konverzovat, je potřeba mít připravené následující služby v IBM Cloudu:

* Watson Assistant (služba pomocí které se vytváří dialogy pro chat)
* Speech to Text (služba převádějící zvukový záznam na text)
* Text to Speech (služba převádějící text na zvuk)
* Visual Recognition (služba analyzující obrázky)

  Služby si zprovozněte podle návodu v sekci ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/cs/watson-services/README.md).

13. Pokud máte všechny služby připravené, tak vítejte zpět a můžeme pokračovat. Musíme zadat přihlašovací údaje k jednotlivým službám do konfiguračního souboru. Protože přihlašovaí údaje jsou celkem dlouhé, je nejlepší se přihlásit k TJBotovi vzdáleně z počítače, kde jste si vytvářeli watson služby. Z Mac OS využijete Terminal, z Windows využijete [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), což je program pro vzdálený přístup, který si musíte nainstalovat. V Terminálu nebo přes PuTTy se připojte k TJBotovi (musíte být s počítačem na stejné síti/WiFi jako TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (do zvyrazněného pole zadejte IP adresu TJBota):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Budete vyzváni k zadání hesla. Výchozí heslo je: **_raspberry_**.

14. V otevřeném terminálu (cmd okně ve Windows) přejděte na adresář, kde jsou uloženy konfigurační soubory TJBota:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
15. Vytvořte si kopii souborů credentials.default.js a config.default.js a kopie pojmenujte credentials.js a config.js. Můžete to udělat vzdáleně přes příkazovou řádku (terminál/cmd okno):
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
16. V editoru (nano = název textového editoru v Raspbianu) vložte potřebné přihlašovací údaje k jednotlivým službám.
  ```
  nano credentials.js
  ```
  Na obrázku níže jsou vyznačena místa, kde je potřeba doplnit platné přihlašovací údaje z IBM Watson služeb.
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Uložení a zavření editoru: CTRL+X, Y, Enter.
  Podobným způsobem můžete aktualizovat nastavený soubor( config.js), kde můžete nastavit rod, hlas, jméno TJB, piny pro RGB LED atd. 
17. Tak a teď už jen spustit TJBota !!! Zpátky do adresáře Desktop/tjbotcz_lite ... a jedeme.
  TJBot je nakonfigurován, aby mluvil mužským hlasem a slyšel na jméno Michael (vyslovujte anglicky "Majkl"). To znamená, že bude rozpoznávat věty, které v sobě mají slovo Michael.

  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Pár návodů, které se můžou hodit

### Kopírování z Windows na Raspberry Pi přes příkazovou řádku
Otevřete si CMD line a otevřete adresář, kde máte soubor, který chcete kopírovat (příkaz cd = change directory). Pak použijte následující příkaz, kde zkontrolujte, zda máte nainstalované PuTTY aa zda platí cesta C:\Program Files\PuTTY\pscp.exe. “file.txt” je název kopírovaného souboru a místo “your_pi” dosaďte IP adresu vašeho Raspberry Pi (musí být na stejné síti):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### Kopírování z Mac OS na Raspberry Pi přes příkazovou řádku (v Mac OS)
Otevřete Terminal a otevřete adresář, kde máte soubor, který chcete kopírovat (příkaz cd = change directory). Pak použijte následující příkaz, kde “file.txt” je název kopírovaného souboru a místo “your_pi” dosaďte IP adresu vašeho Raspberry Pi (musí být na stejné síti):

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```


### Kopírování z Rasberry Pi do Mac OS přes příkazovou řádku (v Mac Os)
Pokud jste v SSH přihlášeni na TJBot Raspbian, tak se napřed odhlaste:

```
logout
```

V terminálu na Mac OS napište příkaz pro kopírování:

```
scp <username na Raspberry Pi>@<ip adresa Raspberry Pi>:/<celá cesta k souboru na Raspberry pi> <celá cesta k uložení na Mac OS>
```

Příklad:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

Pak budete vyzváni k zadání hesla do raspberry Pi.


### Nastavení pevné IP adresy na Raspberry Pi 
Připojte se přes SSH nebo PuTTY na Raspberry Pi. 

```
sudo nano /etc/dhcpcd.conf
```

Odkomentujte příslušnou část a upravte dle potřeby.



### Hlasitost Raspberry Pi z příkazové řádky
Připojte se přes SSH nebo PuTTY na Raspberry Pi. Následující kód nastaví hlasitost na 90%. Zdá se mi, že hlasitost se zvedá ne lineárně, takže rozdíl mezi 90 % a 95 % je markantní.

```
amixer  sset PCM,0 90%
```

Další možností je udělat si alias zkratku, kterou budete zesilovat/zeslabovat hlasitost. Otevřete si v nano editoru .bashrc

```
nano ~/.bashrc
```

a na konec souboru přidejte
```
# Increase volume by 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Decrease volume by 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
Restartujte Raspberry-Pi. Poté stačí v příkazové řádce vždy napsat  `volup`  nebo  `voldown`  a hlasitost se vždy zvýší/sníží o 5%.



### Nastavení audio výstupu na jack
Někdy se stává, že TJBota neslyšíte, i když máte hlasitost naplno. S největší pravděpodobností totiž jde audio do HDMI a nikoliv do připojeného reproduktoru. Pak použijte následující příkaz:

```
sudo amixer cset numid=3 1
```
Poslední číslo udává audio výstup (0=auto, 1=jack, 2=HDMI)


### Uvolnění místa na SD kartě
Pokud máte 16GB microSD kartu, tak jste asi v pohodě. Pokud máte 8GB kartu, se kterou se TJBot běžně dodává, tak vám po instalaci zbydou cca 2GB. Ideální kandidáti na smazání jsou Wolfram a LibreOffice. Ani jeden z těchto programů nebudete s TJBotem potřebovat a uvolní vám zhruba dodatečný 1GB místa na kartě.
Stačí do terminálu napsat:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

### Klonování microSD karty na MacOS
Připojte microSD kartu k svému MacBooku. První řádek z kódu uvedeného níže vám umožní zjistit jaké číslo disku (disk4 apod.) dostala microSD karta přidělěné systémem. Druhý řádek vytvoří na Desktopu MacBooku image microSD karty. 

```
diskutil list
sudo dd if=/dev/<disk number, e.g. disk4> of=~/Desktop/tjbotcz.img conv=sparse bs=1m
```

Vytváření image trvá, takže trpělivost. Pokud chcete zjistit stav vytváření image, stiskněte CTRL+T a v terminálu se vám ukáže kolik už je z image vytvořeno. Vytvořená image bude mít stejnou velikost jako je kapacita microSD karty (tj. 8GB nebo 16GB...).

### Jak vzdáleně editovat soubory na TJBotovi přímo z VS Code
Abyste mohli vzdáleně editovat soubory, potřebujete mít ve Visual Code Studio nainstalované rozšíření _Remote VS Code_ a zároveň na TJBotovi (resp. Raspberry Pi) nainstalovaný _rmate_.

Instalace  rmate (Raspberry Pi): 
Na Raspberry pi otevřete Terminal (nebo vzdáleně přes SSH/PuTTy) a spusťte následující příkaz:

```
sudo wget -O /usr/local/bin/rmate https://raw.githubusercontent.com/aurora/rmate/master/rmate
sudo chmod a+x /usr/local/bin/rmate
```

Pak ve Visual Code Studio otevřete okno Terminal a připojte se na Raspberry Pi:

```
ssh -R 52698:localhost:52698 pi@<ip adresa R-pi>
```

V okně Terminalu předfěte do složky obsahující soubor, který chcete editovat a spusťte: 

```
rmate <název souboru>
```

Soubor se Vám otevře ve Visual Code Studiu a můžete s ním snadno pracovat.

Tip: Pokud nechcete pokaždé zadávat  *ssh -R 52698:localhost:52698* *pi@<ip adresa R-pi>*, vytvořte si alias. Na MacOS vytvořte soubor .bash_profile přímo ve složce uživatele (pokud již soubor neexistuje) a napište do něj tento příkaz: 

```
alias tjpi='ssh -R 52698:localhost:52698 pi@<IP ADRESA TJBOTA>'
```
Pak vám bude stačit ve Visual Code Studiu napsat do okna Terminálu jen *tjpi* a jste připojeni na TJBota. IP adresu musíte samozřejmě změnit, kdykoliv TJBot (resp. Raspberry Pi) dostane přidělenu novou (DHCP).

### Jak nastavit IP tlačítko 
Tato funkcionalita je automaticky nainstalována jako součást předpřipravené image. Pokud jste oživili TJBota z předpřipravené image, nemusíte následující kroky procházet.

Co to dělá? Jakmile jste připojení na internet, můžete dostat informaci o tom, jakou má TJBot IP adresu stisknutím tlačítka. TJBot Vám adresu řekne, eventuálně ji zobrazí i na LCD displeji, pokud jej máte instalován. Instalace tlačítka je k dispozici v návodu ["build"](https://github.com/tjbotcz/manuals/tree/master/cs/build),  stejně jako i instalace LCD displeje.

Aby tlačítko automaticky fungovalo, přidejte na konec souboru .bashrc následující řádku (sudo nano ~/.bashrc):

```
sudo node ~/Desktop/tjbotcz_lite/ipButton.js
```
Po každém spuštění bude TJBot připraven Vám po stisknutí tlačítka přeříkat svoji IP adresu. 

---


