# IBM Cloud: Watson Services

 Pour donner vie à TJBot vous allez avoir besoin de services Watson disponibles sur IBM Cloud  - plus précisément, vous allez lui donner le pouvoir de:

* Écouter - le service Speech to Text, convertissant les fichiers vocaux en texte pouvant être traité ultérieurement.
* Parler - le service Text to speech, conversion du texte en fichiers vocaux utilisés par TJBot pour parler.
* Voir - le service Visual recognition analysant les images, afin que TJBot puisse vous dire ce qu'il voit.
* Dialoguer - le service Watson Assistant crée une logique de dialogue pour que vous puissiez avoir une conversation intelligente avec TJBot.

Pour pouvoir utiliser ces services, vous devez disposer d'un compte sur IBM Cloud (l'enregistrement est gratuit). Vous pouvez obtenir gratuitement les services en version allégée. Chaque service possède ses identifiants que vous devrez entrer dans le fichier de configuration de TJBotCZ (credentials.js).

Créons à présent les services et notons les identifiants.


## S'enregistrer sur IBM Cloud 

Vous pouvez vous enregistrer sur IBM Cloud via www.bluemix.net.

L'enregistrement est gratuit (aucune carte de crédit est nécessaire) et vous permet d'obtenir les services nécessaires en version LITE, ce qui est suffisant pour vos besoins. Tous les services sont accessibles via l'onglet "Catalogue".

## Service Speech to Text

Dans "Catalogue", recherchez _**Speech to Text**_  et cliquez sur "Create". Une nouvelle page avec la configuration du service s'ouvrira. En cliquant sur l'icône "Show", vous afficherez les identifiants du service (nom d'utilisateur, mot de passe). Vous devrez les entrer dans le fichier de configuration du TJBotCZ (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Service Text to Speech

Dans "Catalogue", recherchez _**Text to Speech**_ et cliquez sur "Create". Une nouvelle page avec la configuration du service s'ouvrira. En cliquant sur l'icône "Show", vous afficherez les identifiants du service (nom d'utilisateur, mot de passe). Vous devrez les entrer dans le fichier de configuration du TJBotCZ (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Service Visual Recognition

Dans "Catalogue", recherchez _**Visual Recognition**_ et cliquez sur "Create". Une nouvelle page avec la configuration du service s'ouvrira. En cliquant sur l'icône "Show", vous afficherez les identifiants du service (nom d'utilisateur, mot de passe). Vous devrez les entrer dans le fichier de configuration du TJBotCZ (credentials.js). Dans le cas de ce service, il s’agit simplement de API KEY, dont vous aurez besoin.

![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Service Watson Assistant

Watson Assistant est un outil de création de boîtes de dialogue (chats). Pour un démarrage rapide, nous avons préparé une boîte de dialogue simple que vous pouvez importer dans le service avant de créer vos propres chats. [Télécharger le dialogue ici](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). Dans "Catalogue", recherchez _**Watson Assistant**_ et cliquez sur "Create". Une nouvelle page avec la configuration du service s'ouvrira. En cliquant sur le bouton "Launch", vous ouvrirez une nouvelle fenêtre - le vrai outil de création de chats. Sélectionnez l'onglet "Workspace" où vous trouverez l'icône permettant d'importer le fichier de dialogue téléchargé (voir l'image ci-dessous).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

Après l'importation de la boîte de dialogue, l'espace de travail nouvellement créé s'ouvrira. 
L'icône qui représente un escargot vous amènera vers les identifiants dont vous aurez besoin pour le fichier de configuration sur TJBot (credentials.js). En cas de service Watson Assistant, il existe 3 identifiants : l'identifiant d'espace de travail, le nom d'utilisateur et le mot de passe.

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)

---
