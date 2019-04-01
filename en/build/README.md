# Manual for building TJBotCZ and connecting the hardware

---
![exclamation](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/exclamation.png) _**NOTICE BEFORE YOU START**_ 

 _1. PAY ATTENTION WHEN FOLDING THE CARDBOARD. IF FOLDED WRONG WAY, YOU WILL NEED GLUE TO FIX IT._
 
 _2. GET READY TO GET DIRTY. LASERCUT CARDBOARD LEAVES BLACK SMUDGES ON YOUR HANDS._

(We recommend wipe every part with paper tissue.)

---

### Video-manual
Here is the original video-manual to build TJBot. You can follow it. The only major difference is in connecting the LED. TJBotCZ uses traditional RGB LED which is just resting on a platform below the top part (the head) - see the photos below. To fix the LED we rocommend using Blue Tack or similar sticky gum.

**Be careful:**
* fold cardboard the right way (on some parts there is instruction "fold up" or "fold down" (ohni dolů) - so better safe than sorry :)
* stick to the flow in the video manual so that ou do not have to re-assemble it later
  * especially when connecting the legs for stability
  * inserting the servo


<a href="http://www.youtube.com/watch?feature=player_embedded&v=bLt3Cf2Ui3o" target="_blank"><img src="http://img.youtube.com/vi/bLt3Cf2Ui3o/0.jpg" alt="IMAGE ALT TEXT HERE" width="480" border="10" /></a>

### So what is different about TJBotCZ?

1. Part holding the speaker.
2. RGB LED

Good walkthrough of building TJBot is available also here:

https://www.instructables.com/id/Build-TJ-Bot-Out-of-Cardboard/

For longer endurance we recommend stick some parts with glue-gun. Especially legs and parts holding the Raspberry Pi on the bottom.

### Connecting the hardware

Picture below shows all the connectivity you might need for TJBot:
* power adapter
* HDMI for connecting monitor
* camera
* jack audio output for speaker
* ethernet connecting to internet (in case you do not use WiFi)
* USB slots for microfone, mouse and keyboard
* pins on Raspberry Pi for connecting RGB LED and servo

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi-connect.jpg)


**GPIO pins**

Peropherals to Raspberry Pi are connected over individual pins. Here is the legend to all the pins:
![gpio pins](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/rpi_pins.png)


**Connecting servo to GPIO pins**

Servo uses 3 pins:
* 5V power / + (physical pin 02)
* ground / - (physical pin 14)
* GPIO 7 for commands (physical pin 26) - can be configured (config.js - see bring-to-life)


![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-servo.jpg)


**Connecting RGB LED to GPIO pins**

RGB LED uses 4 pins:
* ground / - (physical pin 09)
* GPIO 17 / R (physical pin 11) - can be configured (config.js - see bring-to-life)
* GPIO 27 / G (physical pin 13) - can be configured (config.js - see bring-to-life)
* GPIO 22 / B (physical pin 15) - can be configured (config.js - see bring-to-life)

![servo](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw-rgbled.jpg)

**Connecting IP Button (OPTIONAL)**

IP button is a regular button which you can connect to Raspberry Pi pins. This button runs _ipButton.js_ program telling you the IP address of the connected TJBotCZ. 

![ipbutton](https://github.com/tjbotcz/manuals/raw/master/images/hw_ipbutton.jpg)

**Connecting I2C LCD (16x2) (OPTIONAL)**

Complementing the IP Button, TJBotCZ can print its IP Address also on the connected LCD display. We use 16x2 LCD with I2C.
The LCD display is also used in some of the programs (e.g. tjbotcz_rps).

![lcd](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/hw_lcd.jpg)



