# IBM Cloud: Watson Services

You will need Watson services available in IBM Cloud to bring TJBot to life - specifically you will give him power of:

* Listening -  Speech to Text service, converting voice files to text that can be processed further. 
* Talking - Text to Speech service, converting text to voice files used by TJBot to talk. 
* Seeing - Visual Recognition service analyzing pictures, so that TJBot can tell you what he sees.
* Chatting - Watson Assisstant service creating dialog logic, so that you can have a high quality chat with TJBot.

In order to setup these services you will need to have an account on IBM Cloud (the registration is free of charge). You can provision the services in lite version for free. Every service has its credentials that you will need to enter into the configuration file of TJBotCZ (credentials.js).

Let's create the services and note down the credential details.

## Registration to IBM Cloudu

You can register to IBM Cloud at www.bluemix.net.

Registration is free (no credit card needed) and allows you to provision the necessary services in LITE version, that is sufficient for our needs. All the services are accessible via the tab "Catalog". 

## Speech to Text service

In "Catalog" search for _**Speech to Text**_ a click on "Create". New page with service configuration will open. Clicking the "Show" icon will unhide the credentials of the service (username a password). You will need to enter those in the TJBotCZ  configuration file (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Text to Speech service

In "Catalog" search for _**Text to Speech**_ a click on "Create". New page with service configuration will open. Clicking the "Show" icon will unhide the credentials of the service (username a password). You will need to enter those in the TJBotCZ  configuration file (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Služba Visual Recognition

In "Catalog" search for _**Visual Recognition**_ a click on "Create". New page with service configuration will open. Clicking the "Show" icon will unhide the credentials of the service. You will need to enter those in the TJBotCZ  configuration file (credentials.js). In case of this service it is just so called API KEY, that you will need. 

![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Watson Assisstant service

Watson Assisstant is tool for creating dialogs (chats). For fast start we have prepared a simple dialog which you can import to the service before you start creating your own chats. [Download the dialog here](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). In "Catalog" search for _**Watson Assisstant**_ a click on "Create". New page with service configuration will open. Clicking the "Launch" button you get a new window - the actual tool for creating chats. Select "Workspace" tab where you will find icon for importing the downloaded dialog file (see picture below).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

After importing the dialog, the newly created workspace will open. Icon imitating snail will bring you to the credential details you need for configuration file on TJBot (credentials.js). In case of Watson Assisstant service there are 3 credentials: workspace id, username a password.

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)

---

