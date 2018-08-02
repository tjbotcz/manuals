# Oživujeme TJBota na Raspberry-Pi

Raspberry-Pi využívá jako operační systém Raspbian, který je postaven na Debian Linuxu.
Celý Raspbian je pak na microSD kartě. Napřed tedy musíme na microSD kartu nahrát OS Raspbian. Budete k tomu potřebovat:

* připojení k internetu, aby sis mohl stáhnout Raspbian OS
* počítač se slotem na SD kartu a adaptér na microSD karty nebo čtečku SD/microSD karet
* USB klávesnici, USB myš
* LCD s HDMI vstupem a HDMI kabel

Postup:
1. Stáhněte si Raspbian OS z https://www.raspberrypi.org/downloads/

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Stáhni si a nainstaluj SW na instalaci image Raspbianu, např. Etcher: https://etcher.io/ a nainstaluj Raspbian OS na microSD kartu (vyber stáhnutý .img soubor, vyber připojenou SD kartu , a…Flash!)

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
11.
