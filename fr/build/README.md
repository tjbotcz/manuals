# Manuel pour la construction de TJBotCZ et la connexion du matériel
---
![exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _**AVERTISSEMENT AVANT DE COMMENCER**_ 

 _1. FAITES ATTENTION LORSQUE VOUS PLIEZ LE CARTON. SI VOUS LE PLIEZ DE FAÇON ERRONÉE, VOUS AUREZ BESOIN DE COLLE POUR LE FAIRE TENIR._
 
 _2. VOUS ALLEZ VOUS SALIR. LE CARTON DÉCOUPÉ PAR LASER LAISSE DES TRACES NOIRES SUR VOS MAINS._

(Nous vous recommandons d'essuyer chaque partie avec un mouchoir en papier.)

---

### Les instructions vidéo
Voici les instructions vidéo originales pour construire un TJBot. Vous pouvez les suivre. La seule différence majeure réside dans la connexion de la LED. JBotCZ utilise une LED RVB traditionnelle qui est simplement posée sur une plate-forme située sous la partie supérieure (la tête) - voir les photos ci-dessous. Pour fixer la LED, nous vous recommandons d'utiliser de la patafix ou une gomme adhésive similaire.

**Faites attention:**
* plier le carton dans le bon sens (sur certaines parties, il y a des instructions "fold up" (ohni nahoru) or "fold down" (ohni dolů) - donc mieux vaut prévenir que guérir :)
* respectez l'ordre des instructions vidéo 
  * surtout lors du montage des jambes 
  * insérez le servo au bon moment 


<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a>

### Alors, en quoi le TJBotCZ est-il différent ?

1. Partie de maintien du haut-parleur.
2. RGB LED

Un bon manuel pour la construction TJBot est également disponible ici :

https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/

Pour une plus grande solidité, nous recommandons de coller certaines parties avec un pistolet à colle. Surtout les jambes et les ailes qui tiennent le Raspberry Pi.

### La connexion du matériel

L'image ci-dessous montre tous les périphériques dont vous aurez besoin pour TJBot :
* Adaptateur d'alimentation
* HDMI pour connecter un écran 
* camera
* sortie audio jack pour haut-parleur
* Ethernet pour la connexion à Internet (au cas où vous n'utilisez pas le WiFi)
* Slots USB pour microphone, souris et clavier
* broches sur Raspberry Pi pour connecter LED RGB et servo

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg)


**Broches GPIO**

Les périphériques Raspberry Pi sont connectés sur des broches individuelles. Voici la légende pour toutes les broches :
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png)


**Connexion du servo aux broches GPIO**

Servo utilise 3 broches:
* Puissance 5V / + (broche physique 02)
* terre / - (broche physique 14)
* GPIO 7 pour les commandes (broche physique 26) - peut être configuré (config.js - voir Donner vie)


![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg)


**Connexion de LED RVB aux broches GPIO**

LED RGB utilise 4 broches:
* terre / - (broche physique 09)
* GPIO 17 / R (broche physique 11) - peut être configuré (config.js - voir Donner vie)
* GPIO 27 / G (broche physique 13) - peut être configuré (config.js - voir Donner vie)
* GPIO 22 / B (broche physique 15) - peut être configuré (config.js - voir Donner vie)

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg)


