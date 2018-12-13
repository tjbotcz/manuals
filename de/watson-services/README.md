# IBM Cloud: Watson-Dienste
 
 
Um TJBot zum Leben zu erwecken, benötigst du die Watson-Dienste, die auf IBM Cloud verfügbar sind - insbesondere gibst du ihm die Funktion des:
 
* Hören - Sprache zum Text-Dienst, der Sprachdateien in Text konvertiert, die weiterverarbeitet werden können.
* Sprechen - Text zu Sprache-Dienst, der Text in Sprachdateien konvertiert, die von TJBot zum Sprechen verwendet werden.
* Sehen - Visuelle Wahrnehmung – Bilder werden analysiert, so dass TJBot dir sagen kann, was er sieht. 

* Chat - Watson Assistant Service erstellt Dialoglogik, so dass du einen qualitativ hochwertigen Chat mit TJBot haben kannst.
 
Um diese Dienste einzurichten, benötigst du ein IBM Cloud Konto (die Registrierung ist kostenlos). Du kannst die Dienste in Lite-Version kostenlos erhalten. Jeder Dienst hat seine Anmeldeinformationen, die du in die Konfigurationsdatei von TJBotCZ (credentials.js) eingeben musst.
 
Lass uns dann die Dienste erstellen und die Anmeldedaten notieren!
 
## Registrierung in IBM Cloud
 
Du kannst dich bei IBM Cloud unter www.bluemix.net registrieren.
 
Die Registrierung ist kostenlos (keine Kreditkarte erforderlich) und ermöglicht dir die Bereitstellung der notwendigen Dienste in LITE-Version, die für unsere Bedürfnisse ausreichend ist. Alle Dienste sind über den  "Katalog" Reiter erreichbar.
 
## Sprache zum Text-Dienst
 
Suche in "Catalog" nach _**Speech to Text**_ und klicke auf "Create". Neue Seite mit Service-Konfiguration wird geöffnet. Wenn du auf das Symbol “Show" klickst, blendest du die Anmeldeinformationen des Dienstes ein (Benutzername und Passwort). Du solltest diese in die TJBotCZ-Konfigurationsdatei (credentials.js) eingeben.
 
![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png) 
 
 
## Text zu Sprache-Dienst
 
Suche in "Catalog" nach _**Text to Speech**_ und klicke auf "Create". Neue Seite mit Service-Konfiguration wird geöffnet. Wenn du auf das Symbol “Show” klickst, blendest du die Anmeldeinformationen des Dienstes ein (Benutzername und Passwort). Du solltest diese in die TJBotCZ-Konfigurationsdatei (credentials.js) eingeben.
 
![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png) 
 
## Visueller Wahrnehmung-Dienst
 
Suche in "Catalog" nach _**Visual Recognition**_ und klicke auf "Create". Neue Seite mit Service-Konfiguration wird geöffnet. Wenn du auf das Symbol “Show” klickst, blendest du die Anmeldeinformationen des Dienstes ein. Du solltest diese in die TJBotCZ-Konfigurationsdatei (credentials.js) eingeben. Hierbei benötigt man nur das so genannte API KEY.
 
![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png) 
 
--- 
 
## Watson Assistent-Dienst
 
Watson Assistent ist ein Werkzeug zum Erstellen von Dialogen (Chats). Für den schnellen Start haben wir einen einfachen Dialog vorbereitet, den du in den Dienst importieren kannst, bevor du eigene Chats erstellst. [Lade den Dialog hier herunter](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). Suche in "Catalog" nach _**Watson Assistant**_ und klicke auf "Create". Neue Seite mit Service-Konfiguration wird geöffnet. Mit einem Klick auf den “Launch” -Taste öffnet sich  ein neues Fenster - und bietet das eigentliche Mittel zum Erstellen des Chats an. Wähle den "Arbeitsbereich" Reiter, in dem du das Symbol zum Importieren der heruntergeladenen Dialogdatei finden wirst (siehe Abbildung unten).
 
![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)
 
Nachdem das Dialogs Importiert ist, öffnet sich ein neu angelegter Arbeitsbereich. Ein Schnecken-ähnlicher Symbol bringt dich zu den Anmeldedaten, die du für die Konfigurationsdatei auf TJBot (credentials.js) benötigen wirst. Im Fall von Watson Assistant Service gibt es 3 Zugangsdaten: workspace id, Benutzername und Passwort.
 
![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png) 
