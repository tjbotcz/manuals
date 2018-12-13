# Handbuch zum Aufbau von TJBotCZ und zum Anschluss der Hardware
 
---
![exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _** HINWEIS VOR DEM START** _
 
_1. SEI AUFMERKSAM BEIM FALTEN DES KARTONS. SOLLTE ES FALSCH GEFALTET SEIN, WIRST DU NACHER KLEBSTOFF BENÖTIGEN, UM ES ZU REPARIEREN._
 
_2. SEI BEREIT, DEINE HÄNDE SCHMUTZIG ZU MACHEN. LASERCUT-PAPIER HINTERLÄSST SCHWARZE FARBE AUF DEN HÄNDEN.
 
(Wir empfehlen, jedes Teil vorher mit Papiertuch abzuwischen.)
 
---
 
### Video-Handbuch
Hier ist das originale Video-Handbuch um TJBot erstellen zu können. Du kannst es verfolgen. Der einzig große Unterschied ist der Anschluss der LED. TJBotCZ verwendet traditionelle RGB-LED, die auf einer Plattform unter dem oberen Teil (dem Kopf) gestellt ist - siehe die Fotos unten. Um die LED zu fixieren, empfehlen wir die Verwendung von Blue Tack oder einem ähnlichen, klebrigen Gummi.
 
**Achtung:**
* Falte den Karton richtig herum (an manchen Stellen gibt es die Anweisung "falte nach oben” oder "falte nach unten“  - sicher ist sicher :)
* Verfolge  den Ablauf im Videohandbuch, damit du es später nicht erneut zusammenbauen musst
* vor allem, beim Verbinden der Beine für Stabilität
* Einsetzen des Servos im entsprechenden Zeitpunkt
 
 
<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a> 
 
  
### Was ist also an TJBotCZ anders?
 
1. Teil, der den Lautsprecher hält.
2. RGB LED
 
Eine gute Anleitung zum Aufbau von TJBot gibt es auch hier:
 
https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/ 
 
Für längere Ausdauer, empfehlen wir einige Teile mit Klebepistole zu kleben. Besonders Beine und die Teile, die  den Raspberry Pi auf der Unterseite halten (Klappen, Flügel).
 
### Anschließen der Hardware
 
Das Bild unten zeigt alle Verbindungsteile, die man für TJBot benötigen könnte:
* Netzteil
* HDMI zum Anschließen des Monitors
* Kamera
* Jack Audio-Ausgang für Lautsprecher
* Ethernet Verbindung zum Internet (falls du kein WiFi benutzt)
* USB-Steckplätze für Mikrofon, Maus und Tastatur
* Pins auf Raspberry Pi zum Anschluss von RGB LED und Servo
 
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg) 
 
 
**GPIO-Stifte**
 
Peripheriegeräte zum Raspberry Pi sind über einzelne Stifte verbunden. Hier ist die Legende zu allen Stiften:
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png) 
 
 
**Servo an GPIO-Stifte anschließen**
 
Servo verwendet 3 Stifte:
* 5V power / + (physischer Stift 02)
* Masse / - (physischer Stift 14)
* GPIO 7 für Befehle (physischer Stift 26) - kann in der Konfigurationsdatei von TJbotCZ konfiguriert werden (config.js - siehe zum-Leben-erwecken/bring-to-life)
 
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg) 
 
**RGB-LED an GPIO-Stifte anschließen**
 
RGB LED verwendet 4 Stifte:
* Masse / - (physischer Stift 09)
* GPIO 17 / R (physischer Stift 11) - kann konfiguriert werden (config.js - siehe siehe zum-Leben-erwecken/bring-to-life)
* GPIO 27 / G (physischer Stift 13) - kann konfiguriert werden (config.js - siehe zum-Leben-erwecken/bring-to-life)
* GPIO 22 / B (physischer Stift 15) - kann konfiguriert werden (config.js - siehe zum-Leben-erwecken/bring-to-life)
 
![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg) 
