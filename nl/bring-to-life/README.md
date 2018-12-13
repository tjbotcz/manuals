# Brengt TJBota tot leven (op Raspberry Pi)

Kies je pad...


1. [Faststart van kant-en-klare afbeelding](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)

2. [Start vanaf nul als een PRO](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)

3. Enkele how-to's die van pas kunnen komen

 
      * [Hoe bestanden kopiëren van Windows naar Raspberry Pi via een opdrachtregel](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from -Windows-to-framboos-pi-behulp-a-command-line)
      * [Hoe bestanden kopiëren van Mac OS naar Raspberry Pi via een opdrachtregel (in Mac OS)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to -Kopie-files-from-mac-os-to-framboos-pi-behulp-a-command-line-in-mac-os)
      * [Hoe bestanden kopiëren van Rasberry Pi naar Mac OS met behulp van de opdrachtregel (v Mac OS)] (https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to- -copy-files-from-rasberry-pi-to-mac-os met behulp van command-line-v-mac-os)
      * [Hoe een IP-adres van een Raspberry Pi in te stellen](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis -IP adres)
      * [Hoe het volume van de Raspberry Pi te veranderen via de opdrachtregel](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume- met behulp van de command-line)
      * [Audio-uitgang instellen op jack](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)
      * [Krijg meer vrije ruimte op microSD-kaart](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)
    


## Faststart van kant-en-klare afbeelding



Het is duidelijk dat je enthousiast bent om TJBot operationeel te hebben. Daarom hebben we een kant-en-klaar beeld voorbereid, waarin we Raspbian voor TJBot CZ hebben voorgeconfigureerd.


Je hebt nodig:


* internetverbinding om het Raspbian OS en SW te downloaden voor het installeren van afbeeldingen op de kaart

* een computer met een sleuf voor een SD / microSD-kaart of een SD / microSD-lezer

* USB-toetsenbord, USB-muis

* LCD met HDMI-poort en HDMI-kabel.



Stappen:


1. Download het kant-en-klare [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) en pak het uit.

2. Download en installeer SW voor het installeren van de afbeelding van Raspbianu op de microSD-kaart, b.v. Etcher: https://etcher.io/. Gebruik het om gedownloade afbeelding op een microSD-kaart te installeren (kies het bestand tjbotcz_lite.img, selecteer de gematigde microSD-kaart en ... Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher knippert")

3. Plaats de vooraf geïnstalleerde microSD-kaart in Raspberry-Pi, sluit deze aan met een toetsenbord, een muis of met een RJ-45 (ethernet) internetkabel. De tweede optie is om het via WiFi te verbinden (als je WiFi gebruikt, moet je de verbinding configureren vanuit de OS Raspbian GUI, Raspberry Pi zal deze instelling onthouden voor de toekomst). U hebt de connectiviteit nodig in stap 4.

4. Op Raspbian Desktop hebben we een script "run-me-first.sh" voorbereid. Voer het uit (dubbelklik en voer de terminal uit). Script downloadt de laatste versie van [TJBotCZ_lite-programma](https://github.com/tjbotcz/tjbotcz_lite) van internet en installeert de benodigde afhankelijkheden.

5. Om te kunnen chatten met TJBot moeten de volginf-services worden ingericht in de IBM Cloud:

* Watson-assistent (service voor het maken van dialogen / chats)
* Speech to Text (spraakbestand voor service-transcriberen naar tekstbestand)
* Tekst naar spraak (service synthetiseert tekst naar stem)
* Visuele herkenning (service analyse van afbeeldingen)

  Bepaal de services volgens de handleiding in de map ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Als u alle services hebt geleverd, dan verwelkomt u terug en gaan we verder. U moet de inloggegevens van afzonderlijke services invoeren in het configuratiebestand (credentials.js). Aangezien de inloggegevens vrij lange reeksen zijn, is de beste manier om ze in te voeren om op afstand verbinding te maken met TJBot vanaf de computer waarop u de Watson-services hebt gemaakt en deze te kopiëren en plakken. Als u een Mac-gebruiker bent, gebruikt u terminal. Als u Windows gebruikt, gebruikt u [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy is een programma voor externe toegang en u moet het eerst installeren. Gebruik Terminal of in PuTTy maak verbinding met TJBot (u moet op hetzelfde netwerk / WiFi staan ??als TJBot):

  

MacOS:
  
```
  
ssh pi @ <ipadresa>
  
```

Windows (voer het IP-adres van TJBota in het gemarkeerde veld in):

  ![PuTTY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)

  U wordt om een ??wachtwoord gevraagd. Standaardwachtwoord is: **_raspberry_**.


7. Navigeer in Terminal (of het cmd-venster in Windows) naar de map met configuratiebestanden:

  ```
  
cd Desktop / tjbotcz_lite / configuratie
  ```

 8. Maak een kopie van de bestanden credentials.default.js en config.default.js en noem ze in overeenstemming hiermee referentiesjs en config.js. U kunt dit ook via het Terminal / CMD-venster op afstand doen:

  ```
  cp config.default.js config.js

  cp credentials.default.js referentials.js
  ```

9. Voeg in de teksteditor genaamd nano de benodigde inloggegevens toe aan afzonderlijke services.

  ```
nano credentials.js
  ```
    
Zie onderstaande afbeelding voor plaatsen die moeten worden gevuld met inloggegevens van Watson-services (verwijder de aanhalingstekens niet).


![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
Het bestand sluiten en opslaan: CTRL + X, Y, Enter.


10. En nu, breng TJBot tot leven !!! terug naar map Desktop / tjbotcz_lite ... en daar gaan we.
  
TJBot is geconfigureerd om met mannelijke stem te spreken en reageert op de naam Michael. Dit betekent dat hij alleen zinnen zal herkennen die Michael in zich hebben. Ga naar [repository](https://github.com/tjbotcz/tjbotcz_lite) voor meer informatie over het TJBotCZ lite-programma en wat ermee te doen.


  
cd ..
  sudo node tjbotcz_lite.js

  `` `
  
! [Tjbot-zwaaien] (https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

  ---

## Begin vanaf nul als een PRO


Raspberry-Pi gebruikt Raspbian als een besturingssysteem, dat is gebouwd op Debian Linux.

Vervolgens staat de hele Raspbian op een microSD-kaart. We moeten dus in de eerste plaats OS Raspbian op een microSD-kaart installeren. Wij hebben nodig:



* internetverbinding om het Raspbian OS en SW te downloaden voor het installeren van afbeeldingen op de kaart

* een computer met een sleuf voor een SD / microSD-kaart of een SD / microSD-lezer
* USB-toetsenbord, USB-muis

* LCD met HDMI-poort en HDMI-kabel.
Steps:


1. Download Raspbian OS https://www.raspberrypi.org/downloads/.



! [Raspbian download] (https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")



2. Download en installeer SW om image Raspbian te installeren, bijvoorbeeld voor Etcher https://etcher.io/ en installeer vervolgens Raspbian OS op microSD-kaart (klik / selecteer gedownload .img-bestand, dan al verbonden SD-kaart, en ... Flash!)



! [Etcher] (https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher knippert")

3. Plaats de vooraf geïnstalleerde microSD-kaart in Raspberry-Pi, sluit deze aan met een toetsenbord, een muis of met een RJ-45 (ethernet) internetkabel. De tweede optie is om het via WiFi te verbinden (als je WiFi gebruikt, moet je de verbinding configureren vanuit de OS Raspbian GUI, Raspberry Pi zal deze instelling onthouden voor de toekomst). U hebt de connectiviteit nodig in stap 5.



4. Vergun de verbinding voor de Raspberry-Pi SSH, om later door te gaan met Raspberry-Pi-afstandsverbinding via terminal of PuTTY (Windows). Schrijf in Terminal:


`` `

sudo raspi-config


`` `

Een menu zal openen.

Kies "Interfacing Options".

Kies "SSH" en schakel het in.

5. Open Terminal en voer uit:

`` `


curl -sl http://ibm.biz/tjbot-bootstrap | sudo sh -


`` `


Met deze opdracht wordt een script gedownload van de server, waarop een interactieve handleiding in het Terminal-venster wordt uitgevoerd. Met deze gids configureert u Raspberry Pi voor TJBot:



* TJBot naam (laat raspberrypi) - (Enter)

* IPv6 (uitschakelen) - (Y)

* Google DNS (inschakelen) - (Y)

* instellingen lokaal (taal) (Y)

* update OS Raspbianu (Y)

* update naar nieuwere versie van Node.js (N)

* camera aansluiten (Y)

* originele TJBot downloaden en testscenario's (Enter)

* configureren van audio-uitvoer (laat poort voor jack-audio ingeschakeld) (N)

* reboot (Y)



6. Installeer node.js versie 9:


`` `

Curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get installeer -y nodejs


```

7. In Terminal open folder Desktop:


```

cd Desktop


```


8. Installeer een van de TJBotCZ-programma's (tjbotcz_lite, tjbotcz, tjbotcz_iot):

`` `
git clone https://github.com/tjbotcz/<name van tjbotcz programma> .git

`` `
9. Open in Terminal de nieuw aangemaakte map "tjbotcz_lite", "tjbotcz" of tjbotcz_iot ":

`` `
cd <naam van de map>

` `
10. Download de afhankelijkheden gedefinieerd in bestand package.json in de map met het programma gedownload in stap 8:

`` `
npm installeren

`` `
11. Om met TJBot te kunnen chatten, moeten de volginfodiensten worden geleverd in de IBM Cloud:

* Watson-assistent (service voor het maken van dialogen / chats)

* Speech to Text (spraakbestand voor service-transcriberen naar tekstbestand)

* Tekst naar spraak (service synthetiseert tekst naar stem)

* Visuele herkenning (service analyse van afbeeldingen)

  
Bepaal de services volgens de handleiding in de map ["watson-services"] (https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).


12. Als u alle services hebt ingesteld, dan verwelkomt u terug en gaan we verder. U moet de inloggegevens van afzonderlijke services invoeren in het configuratiebestand (credentials.js). Aangezien de inloggegevens vrij lange reeksen zijn, is de beste manier om ze in te voeren om op afstand verbinding te maken met TJBot vanaf de computer waarop u de Watson-services hebt gemaakt en deze te kopiëren en plakken. Als u een Mac-gebruiker bent, gebruikt u terminal. Als u Windows gebruikt, gebruikt u [PuTTy] (https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy is een programma voor externe toegang en u moet het eerst installeren. Gebruik Terminal of in PuTTy maak verbinding met TJBot (u moet op hetzelfde netwerk / WiFi staan ??als TJBot):


  MacOS:

` `

ssh pi @ <ipadresa>
 
`` `
Windows (voer het IP-adres van TJBota in het gemarkeerde veld in):

  ! [PuTTY] (https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)

  U wordt om een ??wachtwoord gevraagd. Standaardwachtwoord is: ** _ raspberry _ **.


13. Navigeer in Terminal (of het cmd-venster in Windows) naar de map met configuratiebestanden:

`` `

  cd Desktop / tjbotcz_lite / configuratie

`` `
14. Maak een kopie van de bestanden credentials.default.js en config.default.js en noem ze in overeenstemming hiermee referentiesjs en config.js. U kunt dit ook via het Terminal / CMD-venster op afstand doen:

  `` `
 
cp config.default.js config.js
  
cp credentials.default.js referentials.js
  
`` `
15. Voer in de teksteditor genaamd nano de benodigde inloggegevens in voor afzonderlijke services.

  `` `
 
nano credentials.js
 
`` `
  Zie onderstaande afbeelding voor plaatsen die moeten worden gevuld met inloggegevens van Watson-services (verwijder de aanhalingstekens niet).

! [credentials.js soubor] (https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  
Het bestand sluiten en opslaan: CTRL + X, Y, Enter.
  

16. En nu, breng TJBot tot leven !!! terug naar map Desktop / tjbotcz_lite ... en daar gaan we.
  
TJBot is geconfigureerd om met mannelijke stem te spreken en reageert op de naam Michael. Dit betekent dat hij alleen zinnen zal herkennen die Michael in zich hebben.

`` `
cd ..
  sudo node tjbotcz_lite.js
  
`` `
 
! [Tjbot-zwaaien] (https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---


## Enkele how-to's die van pas kunnen komen

### Bestanden kopiëren van Windows naar Raspberry Pi met behulp van een opdrachtregel

Open de CMD-lijn en adresseerinrichting. Er is een bestand dat je wilt kopiëren (cd = map wijzigen). Gebruik vervolgens de volgende opdrachtregel, waarbij u eerst moet controleren of PuTTY al is geïnstalleerd en controleer of C: \ Program Files \ PuTTY \ pscp.exe. werkt. Het volgende bestand: "file.txt" is een naam voor het kopiëren van bestanden, verander dus "your_pi" naar IP-adres van uw Raspberry Pi (het moet op hetzelfde netwerk zijn):

`` `

"C: \ Program Files \ PuTTY \ pscp.exe" file.txt pi @ your_pi: Desktop / tjbotcz_lite


`` `



### Hoe bestanden kopiëren van Mac OS naar Raspberry Pi met behulp van een opdrachtregel (in Mac OS)


Open de CMD-lijn en adresseerinrichting. Er is een bestand dat je wilt kopiëren (cd = map wijzigen). Gebruik vervolgens de volgende opdrachtregel waar "file.txt" de naam is voor het kopiëren van bestanden, verander dus "your_pi" naar IP-adres van uw Raspberry Pi (het moet in hetzelfde netwerk gedaan worden):



`` `


scp file.txt pi @ your_pi: ~ / Desktop / tjbotcz_lite


`` `



### Bestanden kopiëren van Rasberry Pi naar Mac OS met behulp van de opdrachtregel (v Mac Os)

Als u via SSH bent verbonden met TJBot, logt u eerst uit:

`` `
uitloggen

`` `
n Terminal in Mac OS-opdracht gebruiken om bestanden te kopiëren:

`` `
scp <gebruikersnaam na Raspberry Pi> @ <ip adres Raspberry Pi>: / <volledig pad naar bestand op Raspberry pi> <volledig pad naar waar bestanden moeten worden opgeslagen op Mac OS>

`` `

Voorbeeld:

`` `

scp pi@192.168.1.10: /home/pi/Desktop/tjbotcz_lite/config.js Gebruikers / Honza / Desktop

`` `
U wordt gevraagd om een ??wachtwoord voor Raspberry Pi.

### Hoe een IP-adres van een Raspberry Pi in te stellen

Maak verbinding met Raspberry Pi via SSH of PuTTy. Gebruik vervolgens het commando:

`` `
sudo nano /etc/dhcpcd.conf

`` `

Voeg in het geopende bestand het gedeelte met een statische adresinstelling toe als commentaar en voer de juiste waarden in (IP-adres, router-IP-adres).


### Het volume van de Raspberry Pi wijzigen met behulp van de opdrachtregel
 
Maak verbinding via SSH of PuTTY op Raspberry Pi. De volgende regel code wijzigt het volume naar 90%. Het volume moet op een niet-lineaire manier veranderen, dus het verschil tussen 90% en 95% is opmerkelijk.

`` `

amixer sset PCM, 0 90%

`` `

De volgende optie is om een ??snelkoppeling te maken die het volume kan veranderen. In editor nano open .bashrc bestand:

`` `

nano ~ / .bashrc
`` `
en voeg aan het einde van het bestand toe

`` `

# Verhoog volume met 5%

alias volup = 'sudo amixer set PCM - $ [$ (amixer krijgt PCM | grep -o [0-9] *% | sed' s /% // ') + 5]%'

# Verlaag het volume met 5%

alias voldown = 'sudo amixer set PCM - $ [$ (amixer krijgt PCM | grep -o [0-9] *% | sed' s /% // ') - 5]%'

`` `
Start Raspberry-Pi opnieuw. Dan kun je gewoon `volup` of` voldown` in Terminal schrijven en het volume zal met 5% omhoog / omlaag gaan.


### De audio-uitgang instellen op jack

Soms hoor je TJBot niet, ook al staat het volume op max. Hoogstwaarschijnlijk gaat het geluid naar HDMI en niet naar aangesloten luidsprekers (via jack). Om de output naar jack-connector in te stellen, gebruikt u het volgende:

`` `
sudo amixer cset numid = 3 1


`` `
Het laatste nummer geeft de uitvoer aan (0 = automatisch, 1 = jack, 2 = HDMI)


### Krijg meer vrije ruimte op microSD-kaart


Als je een microSD-kaart van 16 GB hebt, zou het goed moeten komen. Als u echter een 8 GB-kaart hebt, hebt u na installatie nog ongeveer 2 GB over. U kunt Wolfram en LibreOffice verwijderen om meer vrije ruimte te krijgen. Omdat u geen van deze programma's nodig hebt om met TJBot te werken. U krijgt een extra vrije ruimte van 1 GB.

Om de programma's te verwijderen:

`` `

sudo apt-get purge wolfram-motor

sudo apt-get purge libreoffice *

sudo apt-get autoremove
`` `

---


`` `
