# IBM Cloud: Watson Services ( Servizi di Watson)

I servizi di Watson in IBM Cloud dovranno essere abilitati per permettere il funzionamento di TJBot - in particolare: 

* Ascoltare - servizio Speech to Text,  trascrizione di file audio in file di testo che possono essere ulteriormente elaborati.
* Parlare - servizio Text to Speech, conversione dei file di testo in file audio utilizzati da TJBot per comunicare.
* Vedere - servizio Visual Recognition che analizza le immagini, permettendo a TJBot di descrivere ciò che vede.
* Chattare – il servizio Watson Assistant permette a TJBot di dialogare in modo naturale con gli utenti.

Per configurare questi servizi è necessario disporre di un account su IBM Cloud (la registrazione è gratuita). È possibile usufruire gratuitamente la versione Lite dei servizi. Ogni servizio ha le sue credenziali che dovranno essere inserite nel file di configurazione di TJBotCZ (credentials.js).

Creiamo i servizi e annotiamo i dettagli delle credenziali.

## Registration to IBM Cloud

È possibile registrarsi a IBM Cloud tramite l'indirizzo www.bluemix.net.

La registrazione è gratuita (non è richiesta nessuna carta di credito) e permette di usufruire dei servizi necessari nella versione LITE, che è sufficiente per le nostre esigenze. Tutti i servizi sono accessibili tramite la scheda "Catalogo".

## Speech to Text service ( Servizio Speech to Text)

Cercare nel "Catalogo” il servizio _**Speech to Text**_ e premere sul tasto "Crea". Si aprirà una nuova pagina con la configurazione del servizio. Facendo clic sull'icona "Mostra" verranno visualizzate le credenziali del servizio (nome utente e password). Queste credenziali dovranno essere inserite nel file di configurazione TJBotCZ (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Text to Speech service  ( Servizio Text to Speech) 

Cercare nel "Catalogo" il servizio _**Text to Speech**_ e premere sul tasto "Crea". Si aprirà una nuova pagina con la configurazione del servizio. Facendo clic sull'icona "Mostra" verranno visualizzate le credenziali del servizio (nome utente una password). Queste credenziali dovranno essere inserite nel file di configurazione TJBotCZ (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Servizio Visual Recognition

Cercare nel "Catalogo" il servizio _**Visual Recognition**_  e premere sul tasto "Crea". Si aprirà una nuova pagina con la configurazione del servizio. Facendo clic sull'icona "Mostra" verranno visualizzate le credenziali del servizio. Queste credenziali dovranno essere inserite nel file di configurazione TJBotCZ (credentials.js). Nel caso specifico di questo servizio, il file viene chiamato semplicemente API KEY.

![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Watson Assistant service ( Servizio Watson Assistant)

Watson Assistant è lo strumento per comunicare via chat. Per un rapido test abbiamo preparato una semplice finestra di dialogo che puoi importare nel servizio prima di creare le singole chat. [Scarica la finestra di dialogo qui](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). Cercare nel "Catalogo" il servizio _**Watson Assisstant**_ e premere sul tasto "Crea". Si aprirà nuova pagina con la configurazione del servizio. Facendo clic sul tasto "Avvia" si aprirà la finestra di configurazione per creare le chat. Seleziona la scheda "Area di lavoro" in cui troverai l'icona per importare il file della finestra di dialogo scaricata precedentemente (vedi immagine sotto).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

Dopo aver importato la finestra di dialogo, si aprirà l’area di lavoro appena creata. L’icona a forma di lumaca permette di visualizzare i dettagli delle credenziali che serviranno per il file di configurazione di TJBot (credentials.js). Per il servizio Watson Assistant ci sono 3 credenziali di accesso: ID area di lavoro, nome utente e password.

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)

---

