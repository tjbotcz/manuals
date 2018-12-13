# Donner vie à TJBot (sur Raspberry Pi)

Choisissez votre façon de faire...
1. [Faststart à partir d'une image prête à l'emploi](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2. [Partir de zéro comme un PRO](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3. Quelques conseils pratiques qui peuvent être utiles

    * [Comment copier des fichiers de Windows vers Raspberry Pi en utilisant une ligne de commande](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line)
    * [Comment copier des fichiers de Mac OS vers Raspberry Pi en utilisant une ligne de commande (in Mac OS)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os)
    * [Comment copier des fichiers de Raspberry Pi vers Mac OS en utilisant la ligne de commande (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-rasberry-pi-to-mac-os-using-command-line-v-mac-os)
    * [Comment configurer l’adresse IP d’un Raspberry Pi](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address)
    * [Comment changer le volume du son du Raspberry Pi en utilisant la ligne de commande](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line)
    * [Réglage de la sortie audio sur jack](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)
    * [Obtenez plus d'espace libre sur la carte microSD](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)
    
## Faststart à partir d'une image prête à l'emploi 

Vous êtes surement impatient de voir votre TJBot fonctionner. Nous avons donc préparé une image prête à l'emploi, où nous avons préconfiguré Raspbian pour TJBot CZ.

Vous allez voir besoin de :

* connexion Internet pour télécharger le système d'exploitation et le logiciel Raspbian, ce qui permettra d'installer l'image sur la carte
* un ordinateur avec un slot pour carte SD et adaptateur vers microSD ou un lecteur des cartes SD / microSD
* Clavier USB, souris USB
* LCD avec port HDMI et câble HDMI.


Les étapes :
1. Téléchargez [l'image de TJBotCZ] prête à l'emploi(https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) et extrayez-la.

2. Téléchargez et installez le logiciel pour pouvoir installer l'image de Raspbian sur la carte microSD, par ex. Etcher: https://etcher.io/ . Utilisez-le pour installer l'image téléchargée sur la carte microSD(sélectionnez le fichier tjbotcz_lite.img, sélectionnez la carte microSD montée, et …flashez!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Insérez la carte microSD préinstallée dans le Raspberry-Pi, connectez-la avec un écran HDMI, un clavier, une souris ou un câble Internet RJ-45 (Ethernet). La deuxième option consiste à se connecter via WiFi (si vous utilisez le WiFi, vous devez configurer la connexion à partir de l'interface graphique du système d'exploitation de Raspbian, Raspberry Pi se souviendra de ce paramètre pour le futur). Vous aurez besoin de la connectivité à l'étape 4.

4. Sur Raspbian Desktop, nous avons préparé un script "run-me-first.sh". Exécutez-le (double-cliquez et exécutez dans le terminal). Script va télécharger la dernière version de [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) de l'internet et va installer les dépendances nécessaires.

5. Pour dialoguer avec TJBot, vous devez vous procurer les services suivants dans IBM Cloud :

* Watson Assistant (service de création de dialogues / chats)
* Speech to Text (service de transcription de fichier vocal en fichier texte)
* Text to Speech (service de synthèse de texte à la voix)
* Visual Recognition (service d'analyse d'images)

  Procurez-vous ces services conformément au manuel dans le dossier ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Si vous vous êtes procuré tous les services, nous pouvons continuer. Vous devez entrer les identifiants des différents services dans le fichier de configuration(credentials.js). Les identifiants étant des chaînes assez longues, la meilleure façon de les saisir est de se connecter à distance à TJBot à partir de l'ordinateur où vous avez créé les services Watson et de les copier-coller. Si vous êtes un utilisateur Mac, vous utiliserez un terminal, si vous êtes un utilisateur Windows, vous utiliserez [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy est un programme pour l'accès à distance et vous devez d'abord l'installer. En utilisant Terminal ou PuTTy, connectez-vous à TJBot (vous devez être sur le même réseau / WiFi que TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (entrez l'adresse IP de TJBot dans le champ surligné):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Il vous sera demandé un mot de passe. Le mot de passe par défaut est: **_raspberry_**.

7. Dans un terminal (ou une fenêtre cmd sous Windows), accédez au dossier contenant les fichiers de configuration:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
8. Créez une copie des fichiers credentials.default.js et config.default.js et nommez-les credentials.js et config.js respectivement. Vous pouvez le faire aussi à distance via la fenêtre Terminal / CMD:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. Dans l'éditeur de texte appelé nano, entrez les identifiants nécessaires de différents services.
  ```
  nano credentials.js
  ```
  Voir l'image ci-dessous montrant les endroits qui doivent être remplis avec les données d'identification des services Watson (ne supprimez pas les guillemets).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Enregistrer et fermer le fichier: CTRL+X, Y, Enter.
  
10. Et maintenant, donnez vie à TJBot !!! Retour au dossier Desktop/tjbotcz_lite ... et c'est parti ! 
  TJBot est configuré pour parler en voix masculine et réagit au nom de Michael.(prononciation anglaise). Cela signifie qu'il ne reconnaîtra que les phrases qui contiennent le nom de Michael.Pour plus d'informations sur le programme TJBotCZ lite et ce qu'il faut en faire, rendez-vous sur [repository](https://github.com/tjbotcz/tjbotcz_lite).
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Partir de zéro comme un PRO

Raspberry-Pi utilise Raspbian comme système d’exploitation, construit sous Debian Linux.
Ensuite, tout le Raspbian est sur une carte microSD. Ainsi, nous devons d’abord installer OS Raspbian sur une carte microSD. Nous aurons besoin de:

* connexion Internet pour télécharger le système d'exploitation et le logiciel Raspbian, ce qui permettra d'installer l'image sur la carte
* un ordinateur avec un slot pour carte SD / microSD ou un lecteur SD / microSD
* Clavier USB, souris USB
* LCD avec port HDMI et câble HDMI.

Etapes:
1. Téléchargez Raspbian OS https://www.raspberrypi.org/downloads/ .

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Téléchargez et installez le logiciel pour pouvoir installer l'image de Raspbian, par ex. Etcher: https://etcher.io/ et ensuite installez le système d’exploitation Raspian sur la carte microSD (cliquez sur/sélectionnez le fichier téléchargé .img, ensuite la carte SD déjà connectée, et …flashez!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Insérez la carte microSD préinstallée dans le Raspberry-Pi, connectez-la avec un clavier, une souris ou un câble Internet RJ-45 (Ethernet). La deuxième option est de le connecter via WiFi (si vous utilisez le WiFi, vous devez configurer la connexion à partir de l'interface graphique du système d'exploitation Raspbian, Raspberry Pi se souviendra de ce paramètre pour le futur). Vous aurez besoin de la connectivité à l'étape 5.

4. Autorisez la connexion pour le SSH Raspberry-Pi, afin de pouvoir se connecter à distance sur le Raspberry-Pi via un terminal ou PuTTY (Windows). Dans un terminal écrivez : 
```
sudo raspi-config
```
Un menu s'ouvrira.
Sélectionnez “Interfacing Options”.
Sélectionnez “SSH” et autorisez-le.
5. Ouvrez le terminal et lancez :
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```

Cette commande téléchargera un script du serveur, qui exécutera un guide interactif dans la fenêtre du terminal. Avec ce guide, vous allez configurer Raspberry Pi pour TJBot:

* TJBot name (laissez raspberrypi)  - (Enter)
* IPv6 (désactivez) - (Y)
* Google DNS (activez) - (Y)
* paramètres locaux (langue) (Y)
* mettre à jour le système d'exploitation Raspbian (Y)
* mise à jour vers une version plus récente de Node.js (N)
* connexion d’une camera (Y)
* télécharger le TJBot original et les scénarios de test (Enter)
* configuration de la sortie audio (laissez le port pour jack-audio activé) (N)
* redémarrer (Y)

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
9. Dans Terminal ouvrez le dossier nouvellement créé “tjbotcz_lite”, "tjbotcz" ou tjbotcz_iot":
```
cd <name of the folder>
```
10. Télécharger les dépendances définies dans le fichier package.json dans le dossier avec le programme téléchargé à l'étape 8:
```
npm install
```
11. Pour dialoguer avec TJBot, vous devez vous procurer les services suivants dans IBM Cloud :

* Watson Assistant (service de création de dialogues / chats)
* Speech to Text (service de transcription de fichier vocal en fichier texte)
* Text to Speech (service de synthèse de texte à la voix)
* Visual Recognition (service d'analyse d'images)

  Procurez-vous ces services conformément au manuel dans le dossier["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. Si vous vous êtes procuré tous les services, nous pouvons continuer. Vous devez entrer les identifiants des différents services dans le fichier de configuration(credentials.js). Les identifiants étant des chaînes assez longues, la meilleure façon de les saisir est de se connecter à distance à TJBot à partir de l'ordinateur où vous avez créé les services Watson et de les copier-coller. Si vous êtes un utilisateur Mac, vous utiliserez un terminal, si vous êtes un utilisateur Windows, vous utiliserez [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy est un programme pour l'accès à distance et vous devez d'abord l'installer. En utilisant Terminal ou PuTTy, connectez vous à TJBot (vous devez être sur le même réseau / WiFi que TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (entrez l'adresse IP de TJBot dans le champs surligné):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Il vous sera demandé un mot de passe. Le mot de passe par défaut est: **_raspberry_**.

13. Dans un Terminal(ou dans une fenêtre cmd sous Windows) accédez au dossier contenant les fichiers de configuration:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
14. Créer une copie des fichiers credentials.default.js et config.default.js et nommez-les credentials.js et config.js respectivement. Vous pouvez le faire aussi à distance via un terminal / une fenêtre CMD:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. Dans l'éditeur de texte appelé nano, entrez les identifiants nécessaires des différents services.
  ```
  nano credentials.js
  ```
  Voir l'image ci-dessous montrant les endroits qui doivent être remplis avec les identifiants des services Watson (ne supprimez pas les guillemets).
  ![credentials.js](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Enregistrez et fermez le fichier : CTRL+X, Y, Enter.
  
16. Et maintenant, donnez vie à TJBot !!! Retour au dossier Desktop/tjbotcz_lite ... et c'est parti ! 
  TJBot est configuré pour parler en voix masculine et réagit au nom de Michael.(prononciation anglaise). Cela signifie qu'il ne reconnaîtra que les phrases qui contiennent le nom de Michael.
 
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Quelques conseils pratiques qui peuvent être utiles

### Comment copier des fichiers de Windows vers Raspberry Pi en utilisant une ligne de commande
Ouvrez la ligne CMD et le répertoire. Vous y trouverez le fichier que vous voulez copier(cd = change directory).  Ensuite, utilisez la ligne de commande suivante, où vous devez d'abord vérifier si PuTTY est déjà installé et si C:\Program Files\PuTTY\pscp.exe fonctionne. Le “file.txt” est un nom du fichier à copier, remplacez “your_pi”  par l'adresse IP de votre Raspberry Pi (il doit être sur le même réseau):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### Comment copier des fichiers de Mac OS vers Raspberry Pi en utilisant une ligne de commande (sous Mac OS)
Ouvrez la ligne CMD et le répertoire. Vous y trouverez le fichier que vous voulez copier(cd = change directory). Ensuite, utilisez la ligne de commande suivante où “file.txt” est un nom du fichier à copier, remplacez “your_pi”  par l'adresse IP de votre Raspberry Pi (il doit être sur le même réseau):

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```


### Comment copier des fichiers de Raspberry Pi vers Mac OS à l'aide de la ligne de commande (sous Mac Os)
Si vous êtes connecté à TJBot via SSH, déconnectez-vous d'abord: 

```
logout
```

Dans Terminal sous Mac OS, utilisez la commande pour copier des fichiers:

```
scp <username sur Raspberry Pi>@< adresse ip de Raspberry Pi>:/<chemin complet vers le fichier sur Raspberry pi> <chemin complet vers vers l’endroit où le fichier doit être enregistré sur Mac OS> 
```

Example:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

On vous demandera le mot de passe du Raspberry Pi.


### Comment configurer l’adresse IP d’un Raspberry Pi
Connectez-vous à Raspberry Pi via SSH ou PuTTy. Ensuite, utilisez la commande :

```
sudo nano /etc/dhcpcd.conf
```

Dans le fichier ouvert, désélectionnez la partie avec le paramètre d'adresse statique et entrez les valeurs correctes (adresse IP, adresse IP du routeur).



### Comment changer le volume du Raspberry Pi en utilisant la ligne de commande
Connectez-vous via SSH ou PuTTY au Raspberry Pi. La ligne de code suivante changera le volume pour 90%. Il semblerait que le volume change de manière non linéaire, de sorte que la différence entre 90% et 95% est notable.

```
amixer  sset PCM,0 90%
```

L'option suivante consiste à faire un raccourci afin de changer le volume. Dans l'éditeur nano ouvrez .bashrc file :

```
nano ~/.bashrc
```

et à la fin du fichier ajoutez
```
# Augmenter le volume de 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Diminuer le volume de 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
Redémarrez Raspberry-Pi. Ensuite, vous pouvez simplement écrire `volup`  ou `voldown`  dans Terminal et le volume augmentera ou baissera de 5%.



### Réglage de la sortie audio vers le jack

Parfois, vous ne pouvez pas entendre TJBot même si le volume est défini sur max. Très probablement, le son va vers HDMI et non vers le haut-parleur connecté (via jack). Pour régler la sortie vers le connecteur jack, procédez comme suit:

```
sudo amixer cset numid=3 1
```
Le dernier chiffre spécifie la sortie (0=auto, 1=jack, 2=HDMI)


### Obtenez plus d'espace libre sur la carte microSD

Si vous avez une carte microSD de 16 Go, ça devrait aller. Cependant, si vous avez une carte de 8 Go, il vous restera environ 2 Go après l’installation. Vous pouvez désinstaller Wolfram et LibreOffice pour obtenir plus d'espace libre, car vous n'avez besoin d'aucun de ces programmes pour travailler avec TJBot. Vous gagnerez 1 Go d'espace supplémentaire.

Pour supprimer les programmes :

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

---
