# Oživujeme TJBota na Raspberry-Pi
Vyberte si svoji cestu...
1. [Rychlé oživení z předpřipravené image](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#rychl%C3%A9-o%C5%BEiven%C3%AD-z-p%C5%99edp%C5%99ipraven%C3%A9-image)
2. [Oživení hezky od píky](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#o%C5%BEiven%C3%AD-hezky-od-p%C3%ADky)

## <a name="faststart"></a>Rychlé oživení z předpřipravené image 

Určitě se už nemůžete dočkat až TJBota oživíte. Proto jsme pro vás připravili již hotovou image, na které je předkonfigurovaný Raspbian, připravený pro provoz TJBota. 

Budete potřebovat:

* připojení k internetu, aby sis mohl stáhnout Raspbian OS
* počítač se slotem na SD kartu a adaptér na microSD karty nebo čtečku SD/microSD karet
* USB klávesnici, USB myš
* LCD s HDMI vstupem a HDMI kabel

Postup:
1. Stáhněte si předpřipravenou [image TJBota](https://drive.google.com/open?id=1LJBOGV22bPoveNz0kiXSYCnW8kOh20xo) .

2. Stáhněte si a nainstalujte SW na instalaci image Raspbianu, např. Etcher: https://etcher.io/ a nainstalujte Raspbian OS na microSD kartu (vyberte stáhnutý tjbotcz_lite.img soubor, vyberte připojenou SD kartu , a…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Vložte nainstalovanou microSD kartu do Raspberry-Pi, připojte k němu HDMI monitor, klávesnici, myš a RJ-45 (ethernet) kabel na internet. Druhou možnosti je připojit se k internetu přes WiFi - pak musíte v grafickém prostředí OS Raspbianu nastavit připojení k WiFi, Raspberry Pi si toto připojení bude pamatovat. Připojení k internetu budete potřebovat pro krok 4.

4. Na Desktopu máte připravnený skript "run-me-first.sh", který spusťte (dvojklik a execute in terminal). Skript vám stáhne z internetu nejnovější verzi programu TJBotCZ_lite a dotáhne potřebné závislosti.

5. Abychom mohli s TJBotem konverzovat, je potřeba mít připravené následující služby v IBM Cloudu:

* Watson Assistant (služba pomocí které se vytváří dialogy pro chat)
* Speech to Text (služba převádějící zvukový záznam na text)
* Text to Speech (služba převádějící text na zvuk)
* Visual Recognition (služba analyzující obrázky)

  Služby si zprovozněte podle návodu v sekci ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/cs/watson-services/README.md).

6. Pokud máte všechny služby připravené, tak vítejte zpět a můžeme pokračovat. Musíme zadat přihlašovací údaje k jednotlivým službám do konfiguračního souboru. Protože přihlašovaí údaje jsou celkem dlouhé, je nejlepší se přihlásit k TJBotovi vzdáleně z počítače, kde jste si vytvářeli watson služby. Z Mac OS využijete Terminal, z Windows využijete [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), což je program pro vzdálený přístup, který si musíte nainstalovat. V Terminálu nebo přes PuTTy se připojte k TJBotovi (musíte být s počítačem na stejné síti/WiFi jako TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (do zvyrazněného pole zadejte IP adresu TJBota):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Budete vyzváni k zadání hesla. Výchozí heslo je: **_raspberry_**.

7. V otevřeném terminálu (cmd okně ve Windows) přejděte na adresář, kde jsou uloženy konfigurační soubory TJBota:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
8. Vytvořte si kopii souborů credentials.default.js a config.default.js a kopie pojmenujte credentials.js a config.js. Můžete to udělat vzdáleně přes příkazovou řádku (terminál/cmd okno):
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. V editoru (nano = název textového editoru v Raspbianu) vložte potřebné přihlašovací údaje k jednotlivým službám.
  ```
  nano credentials.js
  ```
  Na obrázku níže jsou vyznačena místa, kde je potřeba doplnit platné přihlašovací údaje z IBM Watson služeb.
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Uložení a zavření editoru: CTRL+X, Y, Enter.
  
10. Tak a teď už jen spustit TJBota !!! Zpátky do adresáře Desktop/tjbotcz_lite ... a jedeme.
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---


## <a name="fulljourney"></a>Oživení hezky od píky 


Raspberry-Pi využívá jako operační systém Raspbian, který je postaven na Debian Linuxu.
Celý Raspbian je pak na microSD kartě. Napřed tedy musíme na microSD kartu nahrát OS Raspbian. Budete k tomu potřebovat:

* připojení k internetu, aby sis mohl stáhnout Raspbian OS
* počítač se slotem na SD kartu a adaptér na microSD karty nebo čtečku SD/microSD karet
* USB klávesnici, USB myš
* LCD s HDMI vstupem a HDMI kabel

Postup:
1. Stáhněte si Raspbian OS z https://www.raspberrypi.org/downloads/

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Stáhněte si a nainstalujte SW na instalaci image Raspbianu, např. Etcher: https://etcher.io/ a nainstalujte Raspbian OS na microSD kartu (vyberte stáhnutý .img soubor, vyberte připojenou SD kartu , a…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Vložte nainstalovanou microSD kartu do Raspberry-Pi, připojte k němu HDMI monitor, klávesnici, myš a eventuálně RJ-45 (ethernet) kabel na internet. Druhou možnosti je připojit se k internetu přes WiFi - pak musíte v grafickém prostředí OS Raspbianu nastavit připojení k WiFi, Raspberry Pi si toto připojení bude pamatovat.
4. Povolte na Raspberry-Pi SSH připojení, aby se šlo na Raspberry-Pi připojit vzdálěně přes terminál nebo PuTTY (Windows). Do Terminálu napište:
```
sudo raspi-config
```
Otevře se vám menu
Vyberte “Interfacing Options”.
Vyberte “SSH” a povolte jej.
5. Otevřete Terminal a spusťte následující příkaz:
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
7. V terminálu otevřete adresář Desktop:
```
cd Desktop
```
8. Nainstalujte některý z programů pro TJBota (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<název_programu>.git
```
9. V terminálu otevřete nově vytvořený adresář “tjbotcz_lite”, "tjbotcz" nebo tjbotcz_iot":
```
cd <název_adresáře>
```
10. Dotáhněte potřebné závislosti programu, tak jak jsou definované v souboru package.json, který jste nainstalovali z gitu v kroku 8:
```
npm install
```
11. Abychom mohli s TJBotem konverzovat, je potřeba mít připravené následující služby v IBM Cloudu:

* Watson Assistant (služba pomocí které se vytváří dialogy pro chat)
* Speech to Text (služba převádějící zvukový záznam na text)
* Text to Speech (služba převádějící text na zvuk)
* Visual Recognition (služba analyzující obrázky)

  Služby si zprovozněte podle návodu v sekci ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/cs/watson-services/README.md).

12. Pokud máte všechny služby připravené, tak vítejte zpět a můžeme pokračovat. Musíme zadat přihlašovací údaje k jednotlivým službám do konfiguračního souboru. Protože přihlašovaí údaje jsou celkem dlouhé, je nejlepší se přihlásit k TJBotovi vzdáleně z počítače, kde jste si vytvářeli watson služby. Z Mac OS využijete Terminal, z Windows využijete [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), což je program pro vzdálený přístup, který si musíte nainstalovat. V Terminálu nebo přes PuTTy se připojte k TJBotovi (musíte být s počítačem na stejné síti/WiFi jako TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (do zvyrazněného pole zadejte IP adresu TJBota):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Budete vyzváni k zadání hesla. Výchozí heslo je: **_raspberry_**.

13. V otevřeném terminálu (cmd okně ve Windows) přejděte na adresář, kde jsou uloženy konfigurační soubory TJBota:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
14. Vytvořte si kopii souborů credentials.default.js a config.default.js a kopie pojmenujte credentials.js a config.js. Můžete to udělat vzdáleně přes příkazovou řádku (terminál/cmd okno):
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. V editoru (nano = název textového editoru v Raspbianu) vložte potřebné přihlašovací údaje k jednotlivým službám.
  ```
  nano credentials.js
  ```
  Na obrázku níže jsou vyznačena místa, kde je potřeba doplnit platné přihlašovací údaje z IBM Watson služeb.
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Uložení a zavření editoru: CTRL+X, Y, Enter.
  
16. Tak a teď už jen spustit TJBota !!! Zpátky do adresáře Desktop/tjbotcz_lite ... a jedeme.
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

