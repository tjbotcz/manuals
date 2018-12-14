# Portare TJBota in vita (su Raspberry Pi)

Scegli il tuo percorso ...
1. [Avvio rapido da ready-made image (dall'immagine già pronta)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2. [Inizia da zero come un PRO](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3. Alcuni consigli pratici

    * [Come copiare i file da Windows a Raspberry Pi utilizzando la riga di comando]()
    * [Come copiare i file da Mac OS a Raspberry Pi utilizzando la riga di comando (in Mac OS)]()
    * [Come copiare i file da Rasberry Pi a Mac OS utilizzando la riga di comando (v Mac OS)]()
    * [Come configurare l'indirizzo IP di Raspberry Pi]()
    * [Come modificare il volume di Raspberry Pi utilizzando la riga di comando]()
    * [Impostare l’audio sull’uscita jack]()
    * [Ottenere più spazio libero su microSD Card](https://github.com/tjbotcz/manuals/blob/master/it/bring-to-life/README.md#ottieni-pi%C3%B9-spazio-libero-sulla-scheda-microsd)
    
## Avvio rapido da ready-made image (dall'immagine già pronta) 

Certamente sei ansioso di avere TJBot attivo e funzionante. Pertanto abbiamo preparato un'immagine pronta, dove abbiamo preconfigurato Raspbian per TJBot CZ.

Servirà:

* connessione Internet per scaricare il sistema operativo Raspbian e il software per installare l'immagine sulla scheda
* computer con slot per scheda SD / microSD o lettore SD / microSD
* tastiera USB, mouse USB
* LCD con porta HDMI e cavo HDMI

Passi:
1. Scaricare ready-made image (l'immagine già pronta) [l’imagine di TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) e scomprimerla. 

2. Scaricare e installare il SW di installazione immagine Raspbian sulla scheda microSD, ad es. Etcher: https://etcher.io/. Da usare per installare l'immagine scaricata sulla scheda microSD (scegli il file tjbotcz_lite.img, seleziona la scheda microSD montata e ... Flash !)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher lampeggiante")

3. Inserire la scheda microSD preinstallata in Raspberry-Pi, collegarla con una tastiera, un mouse o con un cavo internet RJ-45 (ethernet). La seconda opzione è quella di collegarla via WiFi (se si utilizza WiFi è necessario configurare la connessione dalla GU Raspbian OS, Raspberry Pi ricorderà questa impostazione per il futuro). Avrai bisogno della connettività al punto 4.

4. Lancia lo script "run-me-first.sh" (doppio clic ed esegui nel terminale) che trovi su  Raspbian Desktop. Lo script scaricherà la versione più aggiornata di [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) da Internet e installerà tutte le dipendenze necessarie.

5. Per chattare con TJBot è necessario avere i seguenti servizi disponibili su IBM Cloud:

* Watson Assisstant (il servizio per creare i dialoghi / le chat)
* Speech to text (il servizio che trascrive il file vocale in un file di testo)
* Text to Speech (il servizio che sintetizza il testo alla voce)
* Visual Recognition (il servizio che analizza le immagini)

  Fornire i servizi in base al manuale nella cartella ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Se disponi di tutti i servizi forniti, allora bentornato e continuiamo. È necessario inserire le credenziali dei singoli servizi nel file di configurazione (credentials.js). Poiché le credenziali sono stringhe piuttosto lunghe, il modo migliore per inserirle è connettersi in remoto a TJBot dal computer in cui sono stati creati i servizi Watson, copiarli ed incollarli. Se sei un utente Mac, utilizzerai il terminale, se sei un utente Windows, utilizzerai [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy è un programma per l'accesso remoto ed è necessario installarlo prima. Usando Terminal o  PuTTy connettiti a TJBot (devi essere sulla stessa rete / WiFi di TJBot):

  Mac OS:
  ```
  ssh pi @ <ipadresa>
  ```

Windows (inserire l'indirizzo IP di TJBota nel campo evidenziato):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Verra’ richiesta una passowrd. La password predefinita è: **_raspberry_**.

7. In Terminale (o in una finestra di cmd in Windows) navigare alla cartella con i file di configurazione:

  ```
  cd Desktop / tjbotcz_lite / configuration
  ```
8. Creare una copia dei file credentials.default.js e config.default.js e denominarli di conseguenza in credentials.js e config.js. E’ possibile farlo anche da remoto tramite Terminale / CMD Window:

  ```
  cp config.default.js config.js
  cp credentials.default.js credentials.js

```
Vedere l'immagine sotto per i campi che devono essere compilati con i dati delle credenziali dai servizi di Watson (non eliminare le virgolette).
  ![credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Chiudere e salvare il file: CTRL + X, Y, Invio.
  
10. E adesso, porta TJBot in vita!!! Tornare alla cartella Desktop / tjbotcz_lite ... e siamo pronti.
  TJBot è configurato per parlare in voce maschile e reagisce al nome Michael. Ciò significa che riconoscerà solo le frasi che hanno il nome di Michael. Per ulteriori informazioni sul programma lite TJBotCZ e su cosa fare, vai a questo [repository](https://github.com/tjbotcz/tjbotcz_lite).
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![Tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Inizia da zero come un PRO

Raspberry-Pi usa Raspbian come un sistema operativo, che è costruito su Debian Linux.
Quindi, l'intero Raspbian si trova su una scheda microSD. Pertanto, dobbiamo prima installare OS Raspbian su una scheda microSD. 

Sarà necessario:

* connessione Internet per scaricare il sistema operativo e il software Raspbian per l'installazione dell'immagine sulla scheda
* un computer con slot per scheda SD / microSD o lettore SD / microSD
* Tastiera USB, mouse USB
* LCD con porta HDMI e cavo HDMI.

passi:
1. Scaricare il sistema operativo Raspbian https://www.raspberrypi.org/downloads/.

![Download di Raspbian](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Download di Raspbian")

2. Scaricare e installare SW per installare l'immagine Raspbian, ad es. Etcher https://etcher.io/ e quindi installa il sistema operativo Raspbian sulla scheda microSD (fai clic / seleziona il file .img scaricato, quindi la scheda SD già connessa e ... Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher lampeggiante")

3. Inserisci la scheda microSD preinstallata in Raspberry-Pi, collegala con una tastiera, un mouse o con il cavo internet RJ-45 (ethernet). La seconda opzione è quella di collegarlo via WiFi (se si utilizza WiFi è necessario configurare la connessione dalla GU Raspbian OS, Raspberry Pi ricorderà questa impostazione per il futuro). Avrai bisogno della connettività nel passaggio 5.

4. Consentire la connessione SSH per Raspberry-Pi, in modo da poter proseguire in seguito con la connessione remota Raspberry-Pi tramite terminale o PuTTY (Windows). Nel terminale scrivi:
```
sudo raspi-config
```
Si aprirà un menu.
Scegli "Opzioni di interfaccia".
Scegli "SSH" e abilitalo.
5. Apri il Terminale ed esegui:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
Questo comando scaricherà uno script dal server, che eseguirà una guida interattiva nella finestra del Terminale. Con questa guida configurerai Raspberry Pi per TJBot:

* Nome TJBot (lascia raspberrypi) - (Invio)
* IPv6 (disabilitato) - (Y)
* Google DNS (abilitazione) - (Y)
* impostazioni locali (lingua) (Y)
* aggiorna OS Raspbianu (Y)
* aggiornamento alla versione più recente di Node.js (N)
* collegamento della fotocamera (Y)
* download di TJBot originali e scenari di test (Invio)
* configurazione dell'uscita audio (lasciare la porta per jack audio abilitata) (N)
* riavvio (Y)

6. Installa node.js versione 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. In Terminal aprire la cartella Desktop:
```
cd Desktop
```
8. Installa uno dei programmi TJBotCZ (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<name del programma tjbotcz> .git
```
9. In Terminale apri la cartella appena creata "tjbotcz_lite", "tjbotcz" o tjbotcz_iot ":
```
cd <nome della cartella>
```
10. Scaricare le dipendenze definite nel file package.json nella cartella con il programma scaricato nel passaggio 8:
```
npm install
```
11. Per poter chattare con TJBot è necessario avere i seguenti servizi forniti in IBM Cloud:

* Assistente di Watson (servizio per la creazione di dialoghi / chat)
* Discorso al testo (servizio che trascrive il file vocale in un file di testo)
* Text to Speech (servizio che sintetizza il testo alla voce)
* Riconoscimento visivo (servizio che analizza le immagini)

  Fornire i servizi in base al manuale nella cartella ["watson-services"] (https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. Se possiedi tutti i servizi forniti, allora bentornati e continuiamo. È necessario inserire le credenziali dei singoli servizi nel file di configurazione (credentials.js). Poiché le credenziali sono stringhe piuttosto lunghe, il modo migliore per inserirle è connettersi in remoto a TJBot dal computer in cui sono stati creati i servizi Watson e copiarli e incollarli. Se sei un utente Mac, utilizzerai il terminale, se sei un utente Windows, utilizzerai [PuTTy] (https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy è un programma per l'accesso remoto ed è necessario installarlo prima. Usando Terminal o in PuTTy connettiti a TJBot (devi essere sulla stessa rete / WiFi di TJBot):

  Mac OS:
  ```
  ssh pi @ <ipadresa>
  ```
  Windows (inserisci l'indirizzo IP di TJBot nel campo evidenziato):

![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  Sarai pregato di inserire la password. La password predefinita è: ** _ raspberry _ **.

13. In Terminale (o in una finestra di cmd in Windows) accedere alla cartella con i file di configurazione:

  ```
  cd Desktop / tjbotcz_lite / configuration
  ```
14. Creare una copia dei file credentials.default.js e config.default.js e denominarli di conseguenza in credentials.js e config.js. Puoi farlo anche da remoto tramite la finestra Terminal / CMD:
  ```
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. Nell'editor di testo chiamato nano inserire le credenziali necessarie per i singoli servizi.
  ```
  nano credentials.js
  ```
  Vedi l'immagine sotto per i psoti che devono essere riempiti con i dati delle credenziali dai servizi di Watson (non eliminare le virgolette).
  ![credentials.js](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Chiusura e salvataggio del file: CTRL + X, Y, Invio.
  
16. E ora, porta TJBot in vita!!! torna alla cartella Desktop / tjbotcz_lite ... e qui andiamo.
  TJBot è configurato per parlare in voce maschile e sente al nome Michael. Ciò significa che riconoscerà solo le frasi che contengono il nome Michael.
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![Tjbot-agitando](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Alcuni suggerimenti che potrebbero tornare utili

### Come copiare file da Windows a Raspberry Pi usando la riga di comando
Apri la linea CMD e l'indirizzatore. Li si trova il file che vuoi copiare (cd = cambia directory). Quindi utilizza la riga di comando successiva, dove prima è necessario verificare se PuTTY è già installato e controllare se C: \ Programmi \ PuTTY \ pscp.exe. sta lavorando. Il seguente file: "file.txt" è il nome per copiare i file, quindi cambia "your_pi" in indirizzo IP del tuo Raspberry Pi (deve essere nella stessa rete):

```
"C: \ Programmi \ PuTTY \ pscp.exe" file.txt pi @ your_pi: Desktop / tjbotcz_lite
```


### Come copiare file da Mac OS a Raspberry Pi usando la riga di comando (in Mac OS)
Apri la linea CMD e l'indirizzatore. Li si trova il file che vuoi copiare (cd = cambia directory). Quindi usa la riga di comando successiva dove "file.txt" è il nome per copiare i file, quindi cambia "your_pi" in indirizzo IP del tuo Raspberry Pi (deve essere fatto nella stessa rete):

```
scp file.txt pi @ your_pi: ~ / Desktop / tjbotcz_lite
```


### Come copiare file da Rasberry Pi a Mac OS utilizzando la riga di comando (v Mac Os)
Se si è connessi a TJBot tramite SSH, effettuare prima il logout:

```
logout
```

In Terminale in Mac OS usa il comando per copiare i file:

```
scp <nome utente na Raspberry Pi> @ <ip Reed Pi adresa:> / <percorso completo al file su Raspberry pi> <percorso completo in cui i file devono essere salvati su Mac OS>
```

Esempio:

```
scp pi@192.168.1.10: /home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

E neccessario inserire la password per Raspberry Pi.


### Come impostare l'indirizzo IP di Raspberry Pi
Accedi a Raspberry Pi su SSH o PuTTy. Quindi usa il comando:

```
sudo nano /etc/dhcpcd.conf
```

Nel file aperto non commentare la parte con l'impostazione dell'indirizzo statico e immettere i valori corretti (indirizzo IP, indirizzo IP del router).



### Come cambiare il volume di Raspberry Pi usando la riga di comando
Accedi tramite SSH o PuTTY su Raspberry Pi. La prossima riga di codice cambierà il suo volume al 90%. Il volume dovrebbe cambiare in modo non lineare, quindi la differenza tra il 90% e il 95% è notevole.

```
amixer sset PCM, 0 90%
```

L'opzione successiva è quella di creare una scorciatoia che possa modificare il volume. Nell'editor nano apri il file .bashrc:

```
nano ~ / .bashrc
```

e alla fine del file aggiungere

```
# Aumenta il volume del 5%
alias volup = 'sudo amixer set PCM - $ [$ (amixer ottiene PCM | grep -o [0-9] *% | sed' s /% // ') + 5]%'
# Diminuisci il volume del 5%
alias voldown = 'sudo amixer set PCM - $ [$ (amixer get PCM | grep -o [0-9] *% | sed' s /% // ') - 5]%'
```
Riavvia Raspberry-Pi. Quindi puoi semplicemente scrivere `volup` o` voldown` in Terminal e il volume cambierà su / giù del 5%.



### Impostare l'uscita audio sul jack
A volte non riesci a sentire TJBot nonostante il volume sia impostato su max. Molto probabilmente l'audio passa a HDMI e non a diffusori collegati (via jack). Per impostare l'uscita sul connettore jack, utilizzare quanto segue:

```
sudo amixer cset numid = 3 1
```
L'ultimo numero specifica l'output (0 = auto, 1 = jack, 2 = HDMI)


### Ottieni più spazio libero sulla scheda microSD
Se hai una scheda microSD da 16 GB, dovrebbe essere sufficente. Tuttavia, se si dispone di una scheda da 8 GB, dopo l'installazione rimangono circa 2 GB. È possibile uninstallare Wolfram e LibreOffice per liberare dello spazio sul scheda microSD. Se questi programi non ti servono per lavorare con TJBot, ottieni di 1 GB dello spazio libero.

Per rimuovere i programmi:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice *
sudo apt-get autoremove
```

