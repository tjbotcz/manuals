# TJBot zum Leben erwecken (auf Raspberry Pi)
 
Wähle deinen Weg aus…
1. [Schnellstart mit vorbereitetem Bild](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#schnellstart-mit-vorbereitetem-bild)
2. [Fang von vorne, wie ein Fachmann an](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#fang-von-vorne-wie-ein-fachmann-an)
3. Einige Anleitungstipps, die dir nützlich sein könnten
 
   * [Wie kopiert man die Dateien von Windows aufs Raspberry Pi mit der Befehlszeile](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#so-kopierst-du-die-dateien-von-windows-auf-raspberry-pi-mit-der-befehlszeile) 
   * [Anleitung zum Kopieren von Dateien von Mac Betriebsystem aufs Raspberry Pi mit der Befehlszeile (in Mac OS)](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#so-kopierst-du-die-dateien-von-mac-bs-auf-raspberry-pi--mit-der-befehlszeile-in-mac-bs)
   * [Kopieren von Dateien von Rasberry Pi ins Mac Betriebsystem mit der Befehlszeile (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#so-kopierst-du-dateien-von-rasberry-pi-ins-mac-bs-mit-der-befehlszeile-in-mac-bs)
   * [Wie kann man die IP-Adresse des Raspberry Pis einstellen](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#so-richtest-du-die-ip-adresse-eines-raspberry-pi-ein)
   * [Wie ändert man die Lautstärke von Raspberry Pi mit der Befehlszeile](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#wie-%C3%A4ndert-man-das-volume-von-raspberry-pi-%C3%BCber-die-befehlszeile) 
    * [Audio-Ausgang auf die Buchse setzen](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#einstellung-der-audioausgabe-f%C3%BCr-die-buchse)
    * [Mehr freien Speicherplatz auf der microSD-Karte erstellen](https://github.com/tjbotcz/manuals/tree/master/de/bring-to-life#mehr-freien-speicherplatz-auf-der-microsd-karte-erhalten)
 
## Schnellstart mit vorbereitetem Bild
 
Klar bist du eifrig den TJBot in Betrieb zu haben. Daher haben wir ein Bild vorbereitet, auf welchem Raspbian für TJBot CZ vorkonfiguriert wurde.
 
Du benötigst:
 
* Internetverbindung zum Herunterladen des Raspbian Betriebsystem und das Software um das Bild auf die Karte installieren zu können
* ein Computer mit einem SD / microSD-Kartensteckplatz oder einem SD / microSD-Leser
* USB-Tastatur, USB-Maus
* LCD mit HDMI-Anschluss und HDMI-Kabel.
 
Schritte:
1. Lade das Bild [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) herunter und entpacke es.
 
2. Lade die Software herunter und installiere es, um ein Image von Raspbian auf die microSD-Karte installieren zu können, z. B. Etcher: https://etcher.io/. Verwende es, um das heruntergeladene Bild auf die microSD-Karte zu installieren (suche die Datei tjbotcz_lite.img aus, wähle die geladene microSD-Karte und... Flash!)
 
![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing") 
 
3. Setz die vorinstallierte microSD-Karte in den Raspberry-Pi ein, verbinde es mit einem HDMI-Bildschirm, einer Tastatur, einer Maus oder mit einem RJ-45 (Ethernet) Internetkabel. Die zweite Möglichkeit ist es über WiFi zu verbinden (solltest du WiFi benutzen, musst du erstmal die Verbindung vom Betriebssystem Raspbian GUI konfigurieren, Raspberry Pi wird diese Einstellung für das nächste Mal merken). Die Verbindung wird für den Schritt 4 benötigt.
 
4. Auf Raspbian Desktop haben wir eine Skript "run-me-first.sh" vorbereitet. Fuhr es aus (Doppelklick und Ausführen im Terminal). Die Skript lädt die neueste Version des [TJBotCZ_lite-Programms](https://github.com/tjbotcz/tjbotcz_lite) aus dem Internet herunter und installiert notwendige Abhängigkeiten.
 
5. Um mit TJBot chatten zu können, müssen die folgenden Dienste in der IBM Cloud bereitgestellt werden:
 
* Watson Assistent (Dienst zum Erstellen von Dialogen / Chats)
* Sprache zum Text (Dienst, der die Sprachdatei in die Textdatei transkribiert)
* Text zu Sprache (Dienst, der Text in die Stimme synthetisiert)
* visuelle Wahrnehmung (die Analyse von Bildern)
 
 Aktiviere die Dienste gemäß dem Handbuch im Ordner ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).
 
6. Wenn du alle Dienste eingerichtet hast, dann willkommen zurück und lass uns fortfahren. Gebe die Anmeldeinformationen einzelner Dienste in die Konfigurationsdatei (credentials.js) ein. Da es sich bei den Anmeldeinformationen um recht lange Zeichenfolgen handelt, besteht die beste Eingabemöglichkeit wäre, eine Fernverbindung mit TJBot von dem Computer herzustellen, auf dem du die Watson-Dienste erstellt und diese kopiert und eingefügt hast. Wenn du ein Mac-Benutzer bist, verwende das Terminal. Wenn du Windows verwendest, benutze [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy ist ein Fernverbindungprogramm , das zuerst installiert werden soll. Verwende das Terminal oder in PuTTy (connect to TJBot) verbinden mit TJBot (du sollst auf dem gleichen Netzwerk / WiFi wie TJBot sein):
 
 
Mac OS:
  ```
  ssh pi @ <ipadresse>
  ```
Windows (gib die IP-Adresse von TJBot in das markierte Feld ein):
 
![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)
 
 
Du wirst nach einem Passwort gefragt. Das Standard-Passwort ist:  **_raspberry_**.
 
7. Navigiere im Terminal (oder cmd-Fenster in Windows) zu einem Ordner mit Konfigurationsdateien:
 
  ``` 
  cd Desktop/tjbotcz_lite/configuration 
  ``` 
 
8. Erstelle eine Kopie der Dateien "credentials.default.js" und "config.default.js", und benenne sie entsprechend mit "credentials.js" und "config.js".  Dies kannst du auch entfernt über das Terminal / CMD-Fenster tun:
 
 
  ```   
  cp config.default.js config.js 
  cp credentials.default.js credentials.js 
 
  ```  
 
9. Im Texteditor namens nano füge die notwendigen Zugangsdaten zu den einzelnen Diensten ein.
  ``` 
  nano credentials.js 
  ``` 
Siehe Bild unten für jeweilige Stellen, wo die Anmeldeinformationen aus Watson-Services eingetragen werden müssen (die Anführungszeichen nicht löschen).
![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
Schließen und Speichern der Datei: Speichern und Schließen von STRG + X, Y, Enter.
 
10. Und jetzt, erwecke deinenTJBot zum Leben !!! zurück zum Ordner Desktop / tjbotcz_lite ... und los geht's.
TJBot ist konfiguriert mit männlicher Stimme zu sprechen und auf den Namen Michael zu reagieren. Das bedeutet, er wird nur die Sätze erkennen, die den Namen Michael enthalten. Weitere Informationen über das TJBotCZ lite-Programm und was damit zu tun ist, findest du in [Repository](https://github.com/tjbotcz/tjbotcz_lite).
 ```
  cd ..
  sudo node tjbotcz_lite.js 
 ```
 
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)
 
 
 
## Fang von vorne, wie ein Fachmann an
 
Raspberry-Pi verwendet Raspbian als Betriebssystem, das bei Debian Linux gebaut wurde.
Dennoch ist der ganze Raspbian auf einer microSD-Karte gespeichert. Also müssen wir zuerst  Raspbian BS auf eine microSD-Karte installieren.  Wir benötigen:
 
* Internetverbindung zum Herunterladen des Raspbian BS und die Software zum Installieren des Bildes auf die Karte
* ein Computer mit einem SD / microSD-Kartensteckplatz oder einem SD / microSD-Leser
* USB-Tastatur, USB-Maus
* LCD mit HDMI-Anschluss und HDMI-Kabel.
 
Schritte:
1. Lade Raspbian OS https://www.raspberrypi.org/downloads/ herunter.
 
![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")
 
2. Lade die Software herunter und installiere es, um ein Image von Raspbian auf die microSD-Karte installieren zu können, z. B. Etcher: https://etcher.io/. Verwende es, um das heruntergeladene Bild auf die microSD-Karte zu installieren (suche die Datei tjbotcz_lite.img aus, wähle die geladene microSD-Karte und... Flash!)
 
![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing") 
 
3. Setz die vorinstallierte microSD-Karte in den Raspberry-Pi ein, verbinde es mit einem HDMI-Bildschirm, einer Tastatur, einer Maus oder mit einem RJ-45 (Ethernet) Internetkabel. Die zweite Möglichkeit ist es über WiFi zu verbinden (solltest du WiFi benutzen, musst du erstmal die Verbindung vom Betriebssystem Raspbian GUI konfigurieren, Raspberry Pi wird diese Einstellung für das nächste Mal merken). Die Verbindung wird für den Schritt 4 benötigt.
 
 
4. Erlaube die Verbindung für den Raspberry-Pi SSH, um später mit Raspberry-Pi Fernverbindung über das Terminal oder PuTTY (Windows) fortzusetzen.  Gib im Terminal ein:
```
sudo raspi-config
```
Ein Menü wird geöffnet.
Gib “interfacing Options” (Schnittstellenoptionen) ein.
Gib "SSH" und aktiviere es.
 
5. Öffne das Terminal und führe folgendes aus:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
Dieser Befehl lädt eine Skript vom Server herunter, auf der ein interaktiver Leitfaden im Terminal-Fenster ausgeführt wird. Mit dieser Anleitung konfigurierst du Raspberry Pi für TJBot:
 
* TJBot Name (Lass raspberrypi)  - (Enter) 
* IPv6 (disable) - (Y)
* Google DNS (enable) - (Y)
* local settings (language) (Y)
* Update OS Raspbian (Y)
* update to newer version of Node.js (N) 
* connecting camera (Y) 
* downloading original TJBot and test scenarios (Enter) 
* configuring audio output (leave port for jack-audio enabled) (N) 
* reboot (Y) 
 
 
6. Installiere node.js Version 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y Nodejs
```
7. Öffne den Ordner Desktop im Terminal, :
```
cd Desktop
```
8. Installiere ein der TJBotCZ-Programme (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/ <Name des tjbotcz-Programms> .git
```
9. Öffne im Terminal den neu erstellten Ordner "tjbotcz_lite", "tjbotcz" oder "tjbotcz_iot":
```
cd <Name des Ordners>
```
10. Lade die Abhängigkeiten herunter, die in der Datei package.json im Ordner mit dem in Schritt 8 heruntergeladenen Programm definiert sind:
```
npm installieren
```
11. Um mit TJBot chatten zu können, müssen die folgenden Dienste in der IBM Cloud bereitgestellt werden:
 
* Watson Assistent (Dienst zum Erstellen von Dialogen / Chats)
* Sprache zum Text (Dienst, der die Sprachdatei in die Textdatei transkribiert)
* Text zu Sprache (Dienst, der Text in die Stimme synthetisiert)
* visuelle Wahrnehmung (die Analyse von Bildern)

Aktiviere die Dienste gemäß dem Handbuch im Ordner  ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md). 
 
 
12. Wenn du alle Dienste eingerichtet hast, dann willkommen zurück und lass uns fortfahren. Gib die Anmeldeinformationen einzelner Dienste in die Konfigurationsdatei (credentials.js) ein. Da es sich bei den Anmeldeinformationen um recht lange Zeichenfolgen handelt, besteht die beste Eingabemöglichkeit wäre, eine Fernverbindung mit TJBot von dem Computer herzustellen, auf dem du die Watson-Dienste erstellt und diese kopiert und eingefügt hast. Wenn du ein Mac-Benutzer bist, verwende das Terminal. Wenn du Windows verwendest, benutze [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy ist ein Fernverbindungprogramm , das zuerst installiert werden soll. Verwende das Terminal oder in PuTTy (connect to TJBot) verbinden mit TJBot (du sollst auf dem gleichen Netzwerk / WiFi wie TJBot sein):
 
Mac OS:
```
ssh pi @ <ipadresse>
```
Windows (gib die IP-Adresse von TJBot in das markierte Feld ein):
 
![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)
 
 
Du wirst nach einem Passwort gefragt. Standard-Passwort ist:  **_raspberry_**.
 
13. Navigiere im Terminal (oder cmd-Fenster in Windows) zu einem Ordner mit Konfigurationsdateien:
 
  ``` 
  cd Desktop/tjbotcz_lite/configuration
  ```
 
14. Erstelle eine Kopie der Dateien "credentials.default.js" und "config.default.js", und benenne sie entsprechend mit "credentials.js" und "config.js".  Dies kannst du auch entfernt über das Terminal / CMD-Fenster tun:
 
 
  ```   
  cp config.default.js config.js 
  cp credentials.default.js credentials.js 
  ```  
15.  Im Texteditor namens nano füge die notwendigen Zugangsdaten zu den einzelnen Diensten ein.
  ``` 
  nano credentials.js 
  ``` 
Siehe Bild unten für jeweilige Stellen, wo die Anmeldeinformationen aus Watson-Services eingetragen werden müssen (die Anführungszeichen nicht löschen).
![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
Schließen und Speichern der Datei: IN CZ VERSION: Speichern und Schließen von STRG + X, Y, Enter.
 
16. Und jetzt, erwecke deinen TJBot zum Leben !!! zurück zum Ordner Desktop / tjbotcz_lite ... und los geht's.
TJBot ist konfiguriert mit männlicher Stimme zu sprechen und auf den Namen Michael zu reagieren. Das bedeutet, er wird nur die Sätze erkennen, die den Namen Michael enthalten. Weitere Informationen über das TJBotCZ lite-Programm und was damit zu tun ist, findest du in [Repository](https://github.com/tjbotcz/tjbotcz_lite).
```
cd ..
sudo node tjbotcz_lite.js 
```
 
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)
 
 
---
 
## Einige Anleitungstipps, die dir nützlich sein könnten
 
### So kopierst du die Dateien von Windows auf Raspberry Pi mit der Befehlszeile
Öffne die CMD-Zeile und den Absender. Es gibt eine Datei, die du kopieren sollst (cd = change directory / Verzeichnis ändern). Verwende dann die nächste Befehlszeile, wo du zunächst beachten müsst, ob PuTTY bereits vorhanden und installiert ist, und ob C: \ Program Files \ PuTTY \ pscp.exe funktioniert. Die folgende Datei: "file.txt" ist ein Name zum Kopieren von Dateien, dementsprechend ändere  "your_pi" in die IP-Adresse deines Raspberry Pi (es muss sich im selben Netzwerk befinden):
 
```
"C: \ Programme \ PuTTY \ pscp.exe" file.txt pi @ your_pi: Desktop / tjbotcz_lite
```
 
 
 
### So kopierst du die Dateien von Mac BS auf Raspberry Pi  mit der Befehlszeile (in Mac BS)
Öffne die CMD-Zeile und den Absender CZ VERSION: Terminal und Addresser. Es gibt eine Datei, die du kopieren sollst (cd = change directory / Verzeichnis ändern). Dann benutze die nächste Befehlszeile, wo "file.txt" der Name für das Kopieren von Dateien ist, also ändere "your_pi" in die IP-Adresse deines Raspberry Pi (es muss im selben Netzwerk gemacht werden):
 
```
scp file.txt pi @ ihr_pi: ~ / Desktop / tjbotcz_lite
```
 
 
### So kopierst du Dateien von Rasberry Pi ins Mac BS mit der Befehlszeile (in Mac BS)
Wenn du mit TJBot über SSH verbunden bist, melde dich zuerst ab:
 
``` 
logout 
``` 
 
 
Im Mac BS verwende  im Terminal den Befehl zum Kopieren von Dateien:
 
``` 
scp <username na Raspberry Pi>@<ip adresa Raspberry Pi>:/<full path to file on Raspberry pi> <full path to where files is to be saved on Mac OS> 
``` 
 
Beispiel:
 
``` 
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop 
``` 
Du wirst nach einem Passwort für Raspberry Pi gefragt.
 
 
In the opened file un-comment the part with static address setting and enter correct values (IP address, router IP address). 
 
 
 
 
 
### So richtest du die IP-Adresse eines Raspberry Pi ein
 
Verbinde dich mit Raspberry Pi über SSH oder PuTTy. Dann benutze den Befehl:
 
```
sudo nano /etc/dhcpcd.conf
```
 
Korrigiere den Teil  in der geöffneten Datei, der die  statischen Adresseinstellung enthält und gib die korrekten Werte ein (IP-Adresse, Router-IP-Adresse).
 
 
 
### Wie ändert man das Volume von Raspberry Pi über die Befehlszeile?
Verbinde dich über SSH oder PuTTY am Raspberry Pi. Die nächste Codezeile ändert ihre Lautstärke auf 90%. Das Volumen sollte sich nicht linear ändern, daher sollte der Unterschied zwischen 90% und 95% bemerkenswert sein.
 
```
amixer sset PCM, 0 90%
```
 
Die nächste Option ist eine Abkürzung, die die Lautstärke ändern kann. Im Editor nano  .bashrc Datei öffnen:
 
``` 
nano ~/.bashrc 
``` 
 
und am Ende der Datei hinzufügen
 
``` 
# Increase volume by 5% 
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%' 
# Decrease volume by 5% 
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%' 

```
Starten Sie Raspberry-Pi neu. Dann kannst du einfach "volup" oder "voldown" in Terminal schreiben und die Lautstärke wird um 5% erhöht / verringert.
 
 
 
### Einstellung der Audioausgabe für die Buchse
Manchmal kann man TJBot nicht hören, obwohl die Lautstärke auf max eingestellt ist. Höchstwahrscheinlich geht der Ton an HDMI und nicht an den angeschlossenen Lautsprecher (über die Buchse). Gehe folgendermaßen vor, um den Ausgang für den Buchsenanschluss festzulegen:
 
```
sudo amixer cset numid = 3 1
```
Die letzte Nummer gibt den Ausgang an (0 = auto, 1 = Buchse, 2 = HDMI)
 
 
### Mehr freien Speicherplatz auf der microSD-Karte erhalten
Wenn du 16 GB microSD-Karte hast, solltest du in Ordnung sein. Wenn du jedoch eine 8-GB-Karte hast, bleibt dir nach der Installation noch ca. 2 GB übrig. Du kannst Wolfram und LibreOffice deinstallieren, um mehr freien Speicherplatz zu erhalten, da du keines dieser Programme für die Arbeit mit TJBot benötigst. Du erhälst  einen zusätzlichen freien Speicherplatz von 1 GB.
 
So entfernst du die Programme:
 
``` 
sudo apt-get purge wolfram-engine 
sudo apt-get purge libreoffice* 
sudo apt-get autoremove 
``` 
 
--- 
