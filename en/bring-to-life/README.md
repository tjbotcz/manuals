# Bringing TJBota to life (on Raspberry Pi)
Choose your path...
1. [Faststart from ready-made image](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#rychl%C3%A9-o%C5%BEiven%C3%AD-z-p%C5%99edp%C5%99ipraven%C3%A9-image)
2. [Start from scratch like a PRO](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#o%C5%BEiven%C3%AD-hezky-od-p%C3%ADky)
3. Some how-tos that may come handy

    * [Kopírování z Windows na Raspberry Pi přes příkazovou řádku (ve Windows)](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#kop%C3%ADrov%C3%A1n%C3%AD-z-windows-na-raspberry-pi-p%C5%99es-p%C5%99%C3%ADkazovou-%C5%99%C3%A1dku)
    * [Kopírování z Mac OS na Raspberry Pi přes příkazovou řádku (v Mac OS)](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#kop%C3%ADrov%C3%A1n%C3%AD-z-mac-os-na-raspberry-pi-p%C5%99es-p%C5%99%C3%ADkazovou-%C5%99%C3%A1dku-v-mac-os)
    * [Kopírování z Rasberry Pi do Mac OS přes příkazovou řádku (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#kop%C3%ADrov%C3%A1n%C3%AD-z-rasberry-pi-do-mac-os-p%C5%99es-p%C5%99%C3%ADkazovou-%C5%99%C3%A1dku-v-mac-os)
    * [Nastavení pevné IP adresy na Raspberry Pi](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#nastaven%C3%AD-pevn%C3%A9-ip-adresy-na-raspberry-pi)
    * [Ovládání hlasitosti zvukového výstupu Raspberry Pi z příkazové řádky](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#hlasitost-raspberry-pi-z-p%C5%99%C3%ADkazov%C3%A9-%C5%99%C3%A1dky)
    * [Nastavení audio výstupu na jack](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#nastaven%C3%AD-audio-v%C3%BDstupu-na-jack)
    * [Uvolnění místa na SD kartě](https://github.com/tjbotcz/manuals/tree/master/cs/oziveni#uvoln%C4%9Bn%C3%AD-m%C3%ADsta-na-sd-kart%C4%9B)
    
    ## Faststart from ready-made image 

Clearly you are eager to have TJBot up and running. Therefore we have prepared a ready-made image, where we preconfigured Raspbian for TJBot CZ.

You will need:

*	internet connection to download the Raspbian OS and SW for installing image on the card
*	a computer with an SD/ microSD card’s slot or an SD/microSD reader
*	USB keyboard, USB mouse
*	LCD with HDMI port and HDMI cable.


Steps:
1. Download the ready-made [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) and unpack it.

2. Download and install SW for installing image of Raspbianu to the microSD card, e.g. Etcher: https://etcher.io/ . Use it to install downloaded image on microSD card (choose tjbotcz_lite.img file, select mounted microSD card , and…Flash!)

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
  TJBot je nakonfigurován, aby mluvil mužským hlasem a slyšel na jméno Michael (vyslovujte anglicky "Majkl"). To znamená, že bude rozpoznávat věty, které v sobě mají slovo Michael.
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---
