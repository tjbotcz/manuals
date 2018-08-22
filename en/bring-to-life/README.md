# Bringing TJBota to life (on Raspberry Pi)
Choose your path...
1. [Faststart from ready-made image](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2. [Start from scratch like a PRO](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3. Some how-to's that may come handy

    * [How to copy files from Windows to Raspberry Pi using a command line](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line)
    * [How to copy files from Mac OS to Raspberry Pi using a command line (in Mac OS)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os)
    * [How to copy files from Rasberry Pi to Mac OS using command line (v Mac Os)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-rasberry-pi-to-mac-os-using-command-line-v-mac-os)
    * [How to set up a Raspberry Pi’s IP address](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address)
    * [How to change Raspberry Pi’s volume using the command line](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line)
    * [Setting audio output to jack](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)
    * [Get more free space on microSD Card](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)
    
## Faststart from ready-made image 

Clearly you are eager to have TJBot up and running. Therefore we have prepared a ready-made image, where we preconfigured Raspbian for TJBot CZ.

You will need:

*	internet connection to download the Raspbian OS and SW for installing image on the card
*	a computer with an SD/ microSD card’s slot or an SD/microSD reader
*	USB keyboard, USB mouse
*	LCD with HDMI port and HDMI cable.


Steps:
1. Download the ready-made [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) and unpack it.

2. Download and install SW for installing image of Raspbianu to the microSD card, e.g. Etcher: https://etcher.io/ . Use it to install downloaded image on microSD card (choose tjbotcz_lite.img file, select mounted microSD card , and…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Insert preinstalled microSD card into Raspberry-Pi, connect it with a keyboard, a mouse or with RJ-45 (ethernet) internet cable. The second option is to connect it via  WiFi (if you use WiFi you need to configurate connection from the OS Raspbian GUI, Raspberry Pi will remember this setting fo rthe future). You will need the connectivity in step 4.

4. On Raspbian Desktop we prepared a script "run-me-first.sh".  Run it (double click and execute in terminal). Script will download the latest version of [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) from the internet and will install necessary dependencies.

5. In order to chat with TJBot we need to have the followinf services provisioned in the IBM Cloud:

* Watson Assistant (service for creating dialogs/chats)
* Speech to Text (service transcripting voice file to text file)
* Text to Speech (service synthetizing text to voice)
* Visual Recognition (service analyzing pictures)

  Provision the services according to the manual in the folder ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. If you have all the services provisioned then welcome back and let's continue. You need to enter the credentials of individual services into the configuration file (credentials.js). Since the credentials are quite long strings, the best way to enter them is to remotely connect to TJBot from the computer where you created the Watson services and copy-paste them. If you are a Mac user, you will use terminal, if you are running Windows, you will use [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy is a program fro remote access and you need to install it first. Using Terminal or in PuTTy connect to TJBot (you need to be on the same network/WiFi as TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (enter IP address of TJBota into highlighted field):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  You will be asked for a password. Default password is: **_raspberry_**.

7. In Terminal (or cmd window in Windows) navigate to folder with configuration files:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
8. Create a copy of credentials.default.js and config.default.js  files and name them credentials.js and config.js accordingly. You can do this also remotly via the Terminal/CMD window:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. In text editor called nano insert the necessary credentials to individual services.
  ```
  nano credentials.js
  ```
  See picture below for places that need to be filled with credential data from Watson services (do not delete the quotation marks).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Closing and saving the file: CTRL+X, Y, Enter.
  
10. And now, bring TJBot to life !!! back to folder Desktop/tjbotcz_lite ... and here we go.
  TJBot is configured to speak in male voice and is reacting on name Michael. This means that he will recognize only sentences that have name Michael in them. For more information about TJBotCZ lite program and what to do with it go to this [repository](https://github.com/tjbotcz/tjbotcz_lite).
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Start from scratch like a PRO

Raspberry-Pi uses Raspbian as an operation system, which is built at Debian Linux.
Then, the whole Raspbian is on a microSD card. Thus, we firstly need to install OS Raspbian on a microSD card. We will need:

*	internet connection to download the Raspbian OS and SW for installing image on the card
*	a computer with an SD/ microSD card’s slot or an SD/microSD reader
*	USB keyboard, USB mouse
*	LCD with HDMI port and HDMI cable.

Steps:
1. Download Raspbian OS https://www.raspberrypi.org/downloads/ .

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Download and install SW in order to install image Raspbian, for e.g. Etcher https://etcher.io/ and then install Raspbian OS on microSD card (click/select downloaded .img file, then already connected SD card, and…Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Insert preinstalled microSD card into Raspberry-Pi, connect it with a keyboard, a mouse or with RJ-45 (ethernet) internet cable. The second option is to connect it via  WiFi (if you use WiFi you need to configurate connection from the OS Raspbian GUI, Raspberry Pi will remember this setting fo rthe future). You will need the connectivity in step 5.

4. Permit the connection for the Raspberry-Pi SSH, in order to later continue with Raspberry-Pi distance connection via terminal or PuTTY (Windows). In Terminal write:
```
sudo raspi-config
```
A menu will open.
Choose “Interfacing Options”.
Choose “SSH” and enable it.
5. Open Terminal and run:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
This command will download a script from the server, which will run an interactive guide in Terminal window. With this guide you will configure Raspberry Pi for TJBot:

* TJBot name (leave raspberrypi)  - (Enter)
* IPv6 (disable) - (Y)
* Google DNS (enable) - (Y)
* settings local (language) (Y)
* update OS Raspbianu (Y)
* update to newer version of Node.js (N)
* connecting camera (Y)
* downloading original TJBot and test scenarios (Enter)
* configuring audio output (leave port for jack-audio enabled) (N)
* reboot (Y)

6. Install node.js version 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. In Terminal open folder Desktop:
```
cd Desktop
```
8. Install one of the TJBotCZ programs (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<name of tjbotcz program>.git
```
9. In Terminal open the newly created folder “tjbotcz_lite”, "tjbotcz" or tjbotcz_iot":
```
cd <name of the folder>
```
10. Download dependencies defined in file package.json in the folder with program downloaded in step 8:
```
npm install
```
11. In order to chat with TJBot we need to have the followinf services provisioned in the IBM Cloud:

* Watson Assistant (service for creating dialogs/chats)
* Speech to Text (service transcripting voice file to text file)
* Text to Speech (service synthetizing text to voice)
* Visual Recognition (service analyzing pictures)

  Provision the services according to the manual in the folder ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. If you have all the services provisioned then welcome back and let's continue. You need to enter the credentials of individual services into the configuration file (credentials.js). Since the credentials are quite long strings, the best way to enter them is to remotely connect to TJBot from the computer where you created the Watson services and copy-paste them. If you are a Mac user, you will use terminal, if you are running Windows, you will use [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy is a program fro remote access and you need to install it first. Using Terminal or in PuTTy connect to TJBot (you need to be on the same network/WiFi as TJBot):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (enter IP address of TJBota into highlighted field):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)


  You will be asked for a password. Default password is: **_raspberry_**.

13. In Terminal (or cmd window in Windows) navigate to folder with configuration files:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
14. Create a copy of credentials.default.js and config.default.js  files and name them credentials.js and config.js accordingly. You can do this also remotly via the Terminal/CMD window:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. In text editor called nano insert the necessary credentials to individual services.
  ```
  nano credentials.js
  ```
  See picture below for places that need to be filled with credential data from Watson services (do not delete the quotation marks).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Closing and saving the file: CTRL+X, Y, Enter.
  
16. And now, bring TJBot to life !!! back to folder Desktop/tjbotcz_lite ... and here we go.
  TJBot is configured to speak in male voice and is reacting on name Michael. This means that he will recognize only sentences that have name Michael in them. 
  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Some how-to's that may come handy

### How to copy files from Windows to Raspberry Pi using a command line 
Open CMD line and addresser. There is a file which you want to copy (cd = change directory).  Then use the next command line, where firstly you need to check whether PuTTY is already installed and check if C:\Program Files\PuTTY\pscp.exe.  is working. The following file: “file.txt” is a name for copying files thus change “your_pi” to IP address of your Raspberry Pi (it has to be at the same network):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### How to copy files from Mac OS to Raspberry Pi using a command line (in Mac OS)
Open CMD line and addresser. There is a file which you want to copy (cd = change directory). Then use the next command line where “file.txt” is name for copying files thus change “your_pi” to IP address of your Raspberry Pi (it has to be done in the same network):

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```


### How to copy files from Rasberry Pi to Mac OS using command line (v Mac Os)
If you are connected to TJBot over SSH, logout first:

```
logout
```

In Terminal in Mac OS use command to copy files:

```
scp <username na Raspberry Pi>@<ip adresa Raspberry Pi>:/<full path to file on Raspberry pi> <full path to where files is to be saved on Mac OS>
```

Example:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

You will be asked for password to Raspberry Pi.


### How to set up a Raspberry Pi’s IP address 
Connect to Raspberry Pi over SSH or PuTTy. Then use command:

```
sudo nano /etc/dhcpcd.conf
```

In the opened file un-comment the part with static address setting and enter correct values (IP address, router IP address).



### How to change Raspberry Pi’s volume using the command line 
Connect via SSH or  PuTTY at Raspberry Pi.  The next line of code will change its volume to 90%. The volume should change in a non-linear way so the difference between 90 % and 95 % is notable.

```
amixer  sset PCM,0 90%
```

The next option is to make a short-cut which can change the volume. In editor nano open .bashrc file:

```
nano ~/.bashrc
```

and at the end of the file add 

```
# Increase volume by 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Decrease volume by 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
Restart Raspberry-Pi. Then you can just write `volup`  or  `voldown`  in Terminal and the volume will change up/down by 5%.



### Setting audio output to jack
Sometimes you cannot hear TJBot eventhough the volume is set to max. Most probably the audio goes to HDMI and not to connected speaker (via jack). To set output to jack connector use the following:

```
sudo amixer cset numid=3 1
```
The last number specifies the output (0=auto, 1=jack, 2=HDMI)


### Get more free space on microSD Card
If you have 16GB microSD card, you should be fine. However, if you have 8GB card, then after installing you will have approximately 2GB left. You can uninstall Wolfram and LibreOffice to get more free space. As you will not need any of these programs for working with TJBot. You will get an extra 1GB free space.

To remove the programs:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

---

