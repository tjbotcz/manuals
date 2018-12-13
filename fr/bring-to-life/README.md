# Donner vie Ã  TJBot (sur Raspberry Pi)

Choisissez votre faÃ§on de faire...
1. [Faststart Ã  partir d'une image prÃªte Ã  l'emploi](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2. [Partir de zÃ©ro comme un PRO](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3. Quelques conseils pratiques qui peuvent Ãªtre utiles

    * [Comment copier des fichiers de Windows vers Raspberry Pi en utilisant une ligne de commande](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line)
    * [Comment copier des fichiers de Mac OS vers Raspberry Pi en utilisant une ligne de commande (in Mac OS)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os)
    * [Comment copier des fichiers de Raspberry Pi vers Mac OS en utilisant la ligne de commande (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-rasberry-pi-to-mac-os-using-command-line-v-mac-os)
    * [Comment configurer lâadresse IP dâun Raspberry Pi](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address)
    * [Comment changer le volume du son du Raspberry Pi en utilisant la ligne de commande](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line)
    * [RÃ©glage de la sortie audio sur jack](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)
    * [Obtenez plus d'espace libre sur la carte microSD](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)
    
## Faststart Ã  partir d'une image prÃªte Ã  l'emploi 

Vous Ãªtes surement impatient de voir votre TJBot fonctionner. Nous avons donc prÃ©parÃ© une image prÃªte Ã  l'emploi, oÃ¹ nous avons prÃ©configurÃ© Raspbian pour TJBot CZ.

Vous allez voir besoin de :

* connexion Internet pour tÃ©lÃ©charger le systÃ¨me d'exploitation et le logiciel Raspbian, ce qui permettra d'installer l'image sur la carte
* un ordinateur avec un slot pour carte SD et adaptateur vers microSD ou un lecteur des cartes SD / microSD
* Clavier USB, souris USB
* LCD avec port HDMI et cÃ¢ble HDMI.


Les Ã©tapes :
1. TÃ©lÃ©chargez [l'image de TJBotCZ] prÃªte Ã  l'emploi(https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) et extrayez-la.

2. TÃ©lÃ©chargez et installez le logiciel pour pouvoir installer l'image de Raspbian sur la carte microSD, par ex. Etcher: https://etcher.io/ . Utilisez-le pour installer l'image tÃ©lÃ©chargÃ©e sur la carte microSD(sÃ©lectionnez le fichier tjbotcz_lite.img, sÃ©lectionnez la carte microSD montÃ©e, et â¦flashez!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. InsÃ©rez la carte microSD prÃ©installÃ©e dans le Raspberry-Pi, connectez-la avec un Ã©cran HDMI, un clavier, une souris ou un cÃ¢ble Internet RJ-45 (Ethernet). La deuxiÃ¨me option consiste Ã  se connecter via WiFi (si vous utilisez le WiFi, vous devez configurer la connexion Ã  partir de l'interface graphique du systÃ¨me d'exploitation de Raspbian, Raspberry Pi se souviendra de ce paramÃ¨tre pour le futur). Vous aurez besoin de la connectivitÃ© Ã  l'Ã©tape 4.

4. Sur Raspbian Desktop, nous avons prÃ©parÃ© un script "run-me-first.sh". ExÃ©cutez-le (double-cliquez et exÃ©cutez dans le terminal). Script va tÃ©lÃ©charger la derniÃ¨re version de [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) de l'internet et va installer les dÃ©pendances nÃ©cessaires.

5. Pour dialoguer avec TJBot, vous devez vous procurer les services suivants dans IBM Cloud :

* Watson Assistant (service de crÃ©ation de dialogues / chats)
* Speech to Text (service de transcription de fichier vocal en fichier texte)
* Text to Speech (service de synthÃ¨se de texte Ã  la voix)
* Visual Recognition (service d'analyse d'images)

  Procurez-vous ces services conformÃ©ment au manuel dans le dossier ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Si vous vous Ãªtes procurÃ© tous les services, nous pouvons continuer. Vous devez entrer les identifiants des diffÃ©rents services dans le fichier de configuration(credentials.js). Les identifiants Ã©tant des chaÃ®nes assez longues, la meilleure faÃ§on de les saisir est de se connecter Ã  distance Ã  TJBot Ã  partir de l'ordinateur oÃ¹ vous avez crÃ©Ã© les services Watson et de les copier-coller. Si vous Ãªtes un utilisateur Mac, vous utiliserez un terminal, si vous Ãªtes un utilisateur Windows, vous utiliserez [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy est un programme pour l'accÃ¨s Ã  distance et vous devez d'abord l'installer. En utilisant Terminal ou PuTTy, connectez-vous Ã  TJBot (vous devez Ãªtre sur le mÃªme rÃ©seau / WiFi que TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (entrez l'adresse IP de TJBot dans le champ surlignÃ©):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Il vous sera demandÃ© un mot de passe. Le mot de passe par dÃ©faut est: **_raspberry_**.

7. Dans un terminal (ou une fenÃªtre cmd sous Windows), accÃ©dez au dossier contenant les fichiers de configuration:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
8. CrÃ©ez une copie des fichiers credentials.default.js et config.default.js et nommez-les credentials.js et config.js respectivement. Vous pouvez le faire aussi Ã  distance via la fenÃªtre Terminal / CMD:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. Dans l'Ã©diteur de texte appelÃ© nano, entrez les identifiants nÃ©cessaires de diffÃ©rents services.
  ```
  nano credentials.js
  ```
  Voir l'image ci-dessous montrant les endroits qui doivent Ãªtre remplis avec les donnÃ©es d'identification des services Watson (ne supprimez pas les guillemets).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Enregistrer et fermer le fichier: CTRL+X, Y, Enter.
  
10. Et maintenant, donnez vie Ã  TJBot !!! Retour au dossier Desktop/tjbotcz_lite ... et c'est parti ! 
  TJBot est configurÃ© pour parler en voix masculine et rÃ©agit au nom de Michael.(prononciation anglaise). Cela signifie qu'il ne reconnaÃ®tra que les phrases qui contiennent le nom de Michael.Pour plus d'informations sur le programme TJBotCZ lite et ce qu'il faut en faire, rendez-vous sur [repository](https://github.com/tjbotcz/tjbotcz_lite).
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Partir de zÃ©ro comme un PRO

Raspberry-Pi utilise Raspbian comme systÃ¨me dâexploitation, construit sous Debian Linux.
Ensuite, tout le Raspbian est sur une carte microSD. Ainsi, nous devons dâabord installer OS Raspbian sur une carte microSD. Nous aurons besoin de:

* connexion Internet pour tÃ©lÃ©charger le systÃ¨me d'exploitation et le logiciel Raspbian, ce qui permettra d'installer l'image sur la carte
* un ordinateur avec un slot pour carte SD / microSD ou un lecteur SD / microSD
* Clavier USB, souris USB
* LCD avec port HDMI et cÃ¢ble HDMI.

Etapes:
1. TÃ©lÃ©chargez Raspbian OS https://www.raspberrypi.org/downloads/ .

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. TÃ©lÃ©chargez et installez le logiciel pour pouvoir installer l'image de Raspbian, par ex. Etcher: https://etcher.io/ et ensuite installez le systÃ¨me dâexploitation Raspian sur la carte microSD (cliquez sur/sÃ©lectionnez le fichier tÃ©lÃ©chargÃ© .img, ensuite la carte SD dÃ©jÃ  connectÃ©e, et â¦flashez!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. InsÃ©rez la carte microSD prÃ©installÃ©e dans le Raspberry-Pi, connectez-la avec un clavier, une souris ou un cÃ¢ble Internet RJ-45 (Ethernet). La deuxiÃ¨me option est de le connecter via WiFi (si vous utilisez le WiFi, vous devez configurer la connexion Ã  partir de l'interface graphique du systÃ¨me d'exploitation Raspbian, Raspberry Pi se souviendra de ce paramÃ¨tre pour le futur). Vous aurez besoin de la connectivitÃ© Ã  l'Ã©tape 5.

4. Autorisez la connexion pour le SSH Raspberry-Pi, afin de pouvoir se connecter Ã  distance sur le Raspberry-Pi via un terminal ou PuTTY (Windows). Dans un terminal Ã©crivez : 
```
sudo raspi-config
```
Un menu s'ouvrira.
SÃ©lectionnez âInterfacing Optionsâ.
SÃ©lectionnez âSSHâ et autorisez-le.
5. Ouvrez le terminal et lancez :
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```

Cette commande tÃ©lÃ©chargera un script du serveur, qui exÃ©cutera un guide interactif dans la fenÃªtre du terminal. Avec ce guide, vous allez configurer Raspberry Pi pour TJBot:

* TJBot name (laissez raspberrypi)  - (Enter)
* IPv6 (dÃ©sactivez) - (Y)
* Google DNS (activez) - (Y)
* paramÃ¨tres locaux (langue) (Y)
* mettre Ã  jour le systÃ¨me d'exploitation Raspbian (Y)
* mise Ã  jour vers une version plus rÃ©cente de Node.js (N)
* connexion dâune camera (Y)
* tÃ©lÃ©charger le TJBot original et les scÃ©narios de test (Enter)
* configuration de la sortie audio (laissez le port pour jack-audio activÃ©) (N)
* redÃ©marrer (Y)

6. Installez node.js version 9 :
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. Dans Terminal ouvrez le dossier Desktop :
```
cd Desktop
```
8. Installez un des programmes TJBotCZ (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<nom du programme tjbotcz>.git
```
9. Dans Terminal ouvrez le dossier nouvellement crÃ©Ã© âtjbotcz_liteâ, "tjbotcz" ou tjbotcz_iot":
```
cd <name of the folder>
```
10. TÃ©lÃ©charger les dÃ©pendances dÃ©finies dans le fichier package.json dans le dossier avec le programme tÃ©lÃ©chargÃ© Ã  l'Ã©tape 8:
```
npm install
```
11. Pour dialoguer avec TJBot, vous devez vous procurer les services suivants dans IBM Cloud :

* Watson Assistant (service de crÃ©ation de dialogues / chats)
* Speech to Text (service de transcription de fichier vocal en fichier texte)
* Text to Speech (service de synthÃ¨se de texte Ã  la voix)
* Visual Recognition (service d'analyse d'images)

  Procurez-vous ces services conformÃ©ment au manuel dans le dossier["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. Si vous vous Ãªtes procurÃ© tous les services, nous pouvons continuer. Vous devez entrer les identifiants des diffÃ©rents services dans le fichier de configuration(credentials.js). Les identifiants Ã©tant des chaÃ®nes assez longues, la meilleure faÃ§on de les saisir est de se connecter Ã  distance Ã  TJBot Ã  partir de l'ordinateur oÃ¹ vous avez crÃ©Ã© les services Watson et de les copier-coller. Si vous Ãªtes un utilisateur Mac, vous utiliserez un terminal, si vous Ãªtes un utilisateur Windows, vous utiliserez [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy est un programme pour l'accÃ¨s Ã  distance et vous devez d'abord l'installer. En utilisant Terminal ou PuTTy, connectez vous Ã  TJBot (vous devez Ãªtre sur le mÃªme rÃ©seau / WiFi que TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (entrez l'adresse IP de TJBot dans le champs surlignÃ©):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Il vous sera demandÃ© un mot de passe. Le mot de passe par dÃ©faut est: **_raspberry_**.

13. Dans un Terminal(ou dans une fenÃªtre cmd sous Windows) accÃ©dez au dossier contenant les fichiers de configuration:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
14. CrÃ©er une copie des fichiers credentials.default.js et config.default.js et nommez-les credentials.js et config.js respectivement. Vous pouvez le faire aussi Ã  distance via un terminal / une fenÃªtre CMD:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. Dans l'Ã©diteur de texte appelÃ© nano, entrez les identifiants nÃ©cessaires des diffÃ©rents services.
  ```
  nano credentials.js
  ```
  Voir l'image ci-dessous montrant les endroits qui doivent Ãªtre remplis avec les identifiants des services Watson (ne supprimez pas les guillemets).
  ![credentials.js](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Enregistrez et fermez le fichier : CTRL+X, Y, Enter.
  
16. Et maintenant, donnez vie Ã  TJBot !!! Retour au dossier Desktop/tjbotcz_lite ... et c'est parti ! 
  TJBot est configurÃ© pour parler en voix masculine et rÃ©agit au nom de Michael.(prononciation anglaise). Cela signifie qu'il ne reconnaÃ®tra que les phrases qui contiennent le nom de Michael.
 
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Quelques conseils pratiques qui peuvent Ãªtre utiles

### Comment copier des fichiers de Windows vers Raspberry Pi en utilisant une ligne de commande
Ouvrez la ligne CMD et le rÃ©pertoire. Vous y trouverez le fichier que vous voulez copier(cd = change directory).  Ensuite, utilisez la ligne de commande suivante, oÃ¹ vous devez d'abord vÃ©rifier si PuTTY est dÃ©jÃ  installÃ© et si C:\Program Files\PuTTY\pscp.exe fonctionne. Le âfile.txtâ est un nom du fichier Ã  copier, remplacez âyour_piâ  par l'adresse IP de votre Raspberry Pi (il doit Ãªtre sur le mÃªme rÃ©seau):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### Comment copier des fichiers de Mac OS vers Raspberry Pi en utilisant une ligne de commande (sous Mac OS)
Ouvrez la ligne CMD et le rÃ©pertoire. Vous y trouverez le fichier que vous voulez copier(cd = change directory). Ensuite, utilisez la ligne de commande suivante oÃ¹ âfile.txtâ est un nom du fichier Ã  copier, remplacez âyour_piâ  par l'adresse IP de votre Raspberry Pi (il doit Ãªtre sur le mÃªme rÃ©seau):

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```


### Comment copier des fichiers de Raspberry Pi vers Mac OS Ã  l'aide de la ligne de commande (sous Mac Os)
Si vous Ãªtes connectÃ© Ã  TJBot via SSH, dÃ©connectez-vous d'abord: 

```
logout
```

Dans Terminal sous Mac OS, utilisez la commande pour copier des fichiers:

```
scp <username sur Raspberry Pi>@< adresse ip de Raspberry Pi>:/<chemin complet vers le fichier sur Raspberry pi> <chemin complet vers vers lâendroit oÃ¹ le fichier doit Ãªtre enregistrÃ© sur Mac OS> 
```

Example:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

On vous demandera le mot de passe du Raspberry Pi.


### Comment configurer lâadresse IP dâun Raspberry Pi
Connectez-vous Ã  Raspberry Pi via SSH ou PuTTy. Ensuite, utilisez la commande :

```
sudo nano /etc/dhcpcd.conf
```

Dans le fichier ouvert, dÃ©sÃ©lectionnez la partie avec le paramÃ¨tre d'adresse statique et entrez les valeurs correctes (adresse IP, adresse IP du routeur).



### Comment changer le volume du Raspberry Pi en utilisant la ligne de commande
Connectez-vous via SSH ou PuTTY au Raspberry Pi. La ligne de code suivante changera le volume pour 90%. Il semblerait que le volume change de maniÃ¨re non linÃ©aire, de sorte que la diffÃ©rence entre 90% et 95% est notable.

```
amixer  sset PCM,0 90%
```

L'option suivante consiste Ã  faire un raccourci afin de changer le volume. Dans l'Ã©diteur nano ouvrez .bashrc file :

```
nano ~/.bashrc
```

et Ã  la fin du fichier ajoutez
```
# Augmenter le volume de 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Diminuer le volume de 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
RedÃ©marrez Raspberry-Pi. Ensuite, vous pouvez simplement Ã©crire `volup`  ou `voldown`  dans Terminal et le volume augmentera ou baissera de 5%.



### RÃ©glage de la sortie audio vers le jack

Parfois, vous ne pouvez pas entendre TJBot mÃªme si le volume est dÃ©fini sur max. TrÃ¨s probablement, le son va vers HDMI et non vers le haut-parleur connectÃ© (via jack). Pour rÃ©gler la sortie vers le connecteur jack, procÃ©dez comme suit:

```
sudo amixer cset numid=3 1
```
Le dernier chiffre spÃ©cifie la sortie (0=auto, 1=jack, 2=HDMI)


### Obtenez plus d'espace libre sur la carte microSD

Si vous avez une carte microSD de 16 Go, Ã§a devrait aller. Cependant, si vous avez une carte de 8 Go, il vous restera environ 2 Go aprÃ¨s lâinstallation. Vous pouvez dÃ©sinstaller Wolfram et LibreOffice pour obtenir plus d'espace libre, car vous n'avez besoin d'aucun de ces programmes pour travailler avec TJBot. Vous gagnerez 1 Go d'espace supplÃ©mentaire.

Pour supprimer les programmes :

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

---
