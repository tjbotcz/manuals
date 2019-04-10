# IBM Cloud: Watson Services

You will need Watson services available in IBM Cloud to bring TJBot to life - specifically you will give him power of:

* Listening -  Speech to Text service, converting voice files to text that can be processed further. 
* Talking - Text to Speech service, converting text to voice files used by TJBot to talk. 
* Seeing - Visual Recognition service analyzing pictures, so that TJBot can tell you what he sees.
* Chatting - Watson Assisstant service creating dialog logic, so that you can have a high quality chat with TJBot.

In order to setup these services you will need to have an account on IBM Cloud (the registration is free of charge). You can provision the services in lite version for free. Every service has its credentials that you will need to enter into the configuration file of TJBotCZ (credentials.js).

Let's create the services and note down the credential details.

## Registration to IBM Cloud

You can register to IBM Cloud at [cloud.ibm.com](https://cloud.ibm.com/login).

Registration is free (no credit card needed) and allows you to provision the necessary services in LITE version, that is sufficient for our needs. All the services are accessible via the tab "Catalog". 

Limitations for LITE services (subject to change according to IBM offering):
* Speech to Text: 100 minutes
* Text to Speech: 10.000 characters
* Watson Assistant: 10.000 messages, 5 skills (each 100 nodes)
* Visual Recognition: 1000 events, 2 custom models
* Translation: 1.000.000 characters
* Tone analyzer: 2500 API calls

## Speech to Text service

In "Catalog" search for _**Speech to Text**_ a click on "Create". New page with service configuration will open. Clicking the "Show" icon will unhide the credentials of the service (apikey and url). You will need to enter those in the TJBotCZ  configuration file (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Text to Speech service

In "Catalog" search for _**Text to Speech**_ a click on "Create". New page with service configuration will open. Clicking the "Show" icon will unhide the credentials of the service (apikey and url). You will need to enter those in the TJBotCZ  configuration file (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Služba Visual Recognition

In "Catalog" search for _**Visual Recognition**_ a click on "Create". New page with service configuration will open. Clicking the "Show" icon will unhide the credentials of the service. You will need to enter those in the TJBotCZ  configuration file (credentials.js). In case of this service it is just so called API KEY, that you will need. 

![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Watson Assisstant service

Watson Assisstant is tool for creating dialogs (chats). For fast start we have prepared a simple dialog which you can import to the service before you start creating your own chats. [Download the dialog here](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). In "Catalog" search for _**Watson Assisstant**_ a click on "Create". New page with service configuration will open. Note down the API KEY and URL.

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)

Clicking the "Launch" button gets you to the new window - the actual user interface for creating chats. Select "Skills" tab, then create skills by importing the downloaded dialog file. On the tile of the created skills, you can access the credentials for the chat (View credentials details). Here you will find the WORKSPACE ID.

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

In case of Watson Assisstant service we are using API V1, so there are 3 credentials you will need: WORKSPACE ID, APIKEY and URL.

---

