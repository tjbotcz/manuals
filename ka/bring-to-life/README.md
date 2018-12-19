# TJBot-ს გაცოცხლება(on Raspberry Pi)

გააკეთეთ თქვენთვის სასურველი არჩევანი: 

1.	[სწრაფი დაწყება
არსებულ გამოსახულიგან](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2.	[თავიდან დაწყება, როგორც  PRO](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3.	რამოდენიმე პრაქტიკული რჩევა, რომელიც  შეიძლება დაგჭირდეთ.

	* [როგორ დააკოპიროთ ფაილები Windows-დან Raspberry Pi-ში command line-ის გამოყენებით](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line)

	* [როგორ დააკოპიროთ ფაილები Mac OS-დან Raspberry Pi-ში command line-ის გამოყენებით (in Mac OS)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os)

	* [როგორ ავაწყოთ Raspberry Pi-ის IP მისამართი](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address)

	* [როგორ შეცვალოთ Raspberry Pi- ს მოცულობა command line-ის გამოყენებით](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line)

	* [აუდიოს დაყენება jack-ზე ](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)

	* [მიიღეთ თავისუფალი ადგილი მიკრო SD ბარათზე](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)

## სწრაფი დაწყება არსებულ გამოსახულიდან. 
ცხადია, თქვენ სურვილი გაქვთ TJBot- ის ჩართვა. აქედან გამომდინარე,მოვამზადეთ გამოსახულება, სადაც აწყობილია Raspbian TJBot-ი CZ- სთვის(კერძოდ ჩეხეთისთვის).

თქვენ დაგჭირდებათ:

•	ინტერნეტ კავშირი Raspbian OS- ს და SW-ი გადმოწერა ბარათზე ინსტალაციისთვის.

•	კომპიუტერი SD/ microSD card’s slot-ით or an SD/microSD reader-ით. 

•	USB კლავიატურა, USB მაუსი

•	LCD ერთად HDMI პორტი და HDMI კაბელი.

ნაბიჯები: 

1.	გადმოტვირთეთ ready-made [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) და ამოაარქივეთ.
2.	გადმოტვირთეთ და  დააინსტალირეთ SW-ი Raspbianu- ის გამოსახულების ინსტალაციისთვის micro SD ბარათზე, e.g. Etcher: https://etcher.io/ . გამოიყენეთ გადმოტვირთული სურათი ინსტალაციისთვის micro SD ბარათზე, აირჩიეთ tjbotcz_lite.img file, აირჩიეთ microSD card-ი , და …Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3.	ჩასვით წინასწარ ინსტალირებული micro SD ბარათი Raspberry-Pi-ში, შეუერთეთ კლავიატურას mouse-ს ან RJ-45-ს (ethernet) შინაგან კაბელით. მეორე გამოსავალია WiFi- თან დაკავშირება (თუ იყენებთ WiFi- ს, თქვენ უნდა დააკონფიგურიროთ კავშირი OS Raspbian GUI- დან, Raspberry Pi-დაიმახსოვროთ პარამეტრები მომავალში).Raspbian Desktop- ზე ჩვენ მოვამზადეთ სკრიპტი "Run-me-first.sh". ამოშარეთ (ორმაგი დაწკაპუნებით და ტერმინალის ამოქმედებით). სკრიპტი ჩამოტვირთავს უახლეს ვერსიას [TJBotCZ_lite პროგრამის] (https://github.com/tjbotcz/tjbotcz_lite) ინტერნეტიდან და დაამონტაჟებს საჭირო ურთიერთდამოკიდებულებას. 

TJBot-თან კომინიკაციისათვის დაგვჭირდება შემდეგი სერვისები IBM Cloud-ზე: 

* Watson Assistant (სერვისი დიალოგების/ჩატის შექმნისათვის)
* Speech to Text (სერვიცი, რომელიც გადადის ხმოვანი ფაილიდან ტექსტის ფაილში)
* Text to Speech (სინტეზირების სერვისი ტექსტი ხმაში) 
* Visual Recognition (ვიზუალიზირება, როდესაც აანალიზებს რასაც ხედავს)

სერვისის მომსახურება ["Watson- მომსახურება"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md)ფოლდერის მიხედვით. 
იმ შემთხვევაში თუ გაქვთ ყველა სერვისის მომსახურება მაშინ გავაგძელოთ. თქვენ დაგჭირდებათ ინდივიდუალური სერვისის მონაცემების ჩაწერა ფაილში (credentials.js). იმის გათვალისწინებით, რომ მონაცემები საკმაოდ ბევრია, საუკეთესო გამოსავალია TJBot- ის შეერთება კომპიუტერთან, სადაც შეგიძლიათ შექმნათ Watson სერვისი და შემდგომ გადმოაკოპიროთ მონაცემები.იმ შემთხვევაში თუ ხართ Mac-ის მომხმარებელი, მაშინ ტერმინალის გამოყენება დაგჭირდებათ, თუ Windows- სის მომხმარებელი ბრძანდებით გამოიყენეთ : [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy არის პროგრამა დისტანციური წვდომისთვის და საჭიროებს ინსტალაციას.  ტერმინალის ან PuTTy-ის გამოყენებისთვის TJBot -ი უნდა შეართოდ. ( გამოიყენეთ იგივე network/WiFi-ი, რაზეც TJBot-ია შეერთებული). 

MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (შეიყვანეთ IP address of TJBota ხაზგასმულ სფეროში):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)

თქვენ დაგჭირდებათ პაროლი. პაროლი არის : **_raspberry_**.

7. ტერმინალში (or cmd window in Windows) გადაიყვანეთ folder-ში  კონფიგურაციის ფაილთნ ერთად:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```

8. შექმენით credentials.default.js და config.default.js ფაილების ასლი და დაასახელეთ credentials.js და config.js accordingly -ი.ამის განხორციელება შეგიძლიათ ასევე Terminal / CMD-ის ფანჯრის საშუალებით:
  ```
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
ტექსტურ რედაქტორში სახელად nano ჩაწერეთ საჭირო მონაცემები, ინდივიდუალური სერვისისთვის. 

  ```
  nano credentials.js
  ```

იხილეთ ქვემოთ, განყოფილებები სადაც საჭიროა მონაცემების ჩაწერა Watson სერვისისთვის ( არ წაშალოთ ჩანართების ნიშნები) 

![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  ფაილის დახურვა და შენახვა: CTRL+X, Y, Enter.

ახლა კი, გააცოცხლეთ TJBot-ი !!! დაბრუნდით Desktop/tjbotcz_lite - ში ... და მზად არის. TJBot-ი ისაუბრებს მამაკცის ხმით და რეაგირებს სახელზე მიშელი (Michael). ეს იმას ნიშნავს, რომ TJBot-ი რეაგირებს მხოლოდ წინადადებებზე სადაც სახელი მიშელია ნახსენები. დამატებითი ინფორმაციისთვის TJBotCZ-ის პროგრამაზე და თუ როგორ უნდა ისარგებლოთ რობოტით, გადადით მოცემულ ლინკზე: (https://github.com/tjbotcz/tjbotcz_lite).

```
cd ..
sudo node tjbotcz_lite.js
```

![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## თავიდან დაწყება როგორც PRO: 

Raspberry-Pi-ი სარგებლობს Raspbian-ის საოპერაციო სისტემით, რომელიც აგებულია Debian Linux- ზე. შემდეგ მთლიანი Raspbian-ი microSD card-ზეა. ამრიგად,ჩვენ პირველ რიგში უნდა გვქონდეს OS Raspbian microSD-ი ბარათზე. ჩვენ გვჭირდება:
•	ინტერნეტ კავშირი Raspbian OS- ს და SW- ს გადმოსაწერად ბარათზე ინსტალაციისთვის.
•	კომპიუტერი SD / microSD ბარათის სლოტთათ ან SD / microSD მკითხველით.
•	USB კლავიატურა, USB მაუსი
•	LCD HDMI პორტთან ერთად და HDMI კაბელით.
	

ნაბიჯები:
1. Download Raspbian OS https://www.raspberrypi.org/downloads/ .

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. ჩამოტვირთეთ და დააინსტალირეთ SW იმისათვის, რომ დააინსტალიროთ image Raspbian, მაგ. Etcher https://etcher.io/ და შემდეგ დააყენეთ Raspbian OS microSD ბარათზე (დააწკაპუნეთ / აირჩიეთ downloaded .img ფაილი, შემდეგ დააკავშირებული SD ბარათი და ... Flash!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. ჩასვით Raspberry-Pi-ში წინასწარ დაყენებული microSD ბარათი. დააკავშირეთ იგი კლავიატურა, მაუსი ან RJ-45 (ეტერნეტი) ინტერნეტ კაბელი. მეორე გამოსავლია WiFi- თან დაკავშირება (თუ იყენებთ WiFi- ს, თქვენ უნდა დააკონფიგურიროთ კავშირი OS Raspbian GUI- დან, Raspberry Pi დაიმახსოვრეთ პარამეტრები მომავალში). თქვენ დაგჭირდებათ კავშირი მე-5 საფეხურზე.

4. ნებადართეთ Raspberry-Pi SSH დაკავშირება, რათა შემდგომ შესძლოთ დაუკავშირდეთ Raspberry-Pi distance ტერმინალით ან PuTTY (Windows)-ით. ტერმინალი წერს: 
```
sudo raspi-config	
```
გაიხსნება menu 
აირჩიეთ : “Interfacing Options”.
აირჩიეთ: “SSH” and enable it.


5. გახსენით ტერმინალი და დაიწყეთ (run):

```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```

ეს ბრძანება(command)სერვერიდან გადმოწერს სკრიპტს,რომელიც აწარმოებს ინტერაქტიულ ინსტრუქციას Terminal window-ში. აღნიშნულ ისტრიქციით დააკონფიგურეთ Raspberry Pi-ი TJBot-თვის:

•	TJBot- ის სახელი (ჩაწერეთ raspberrypi) - (შეიყვანეთ)
•	IPv6 (გამორთვა) - (Y)
•	Google DNS (ჩართვა) - (Y)
•	პარამეტრები “local” (ენა) 
•	გაანახლე OS Raspbianu (Y)
•	გაანახლეთ ახალი ვერსია Node.js (N)
•	დააკვაშირეთ კამერა 
•	გადმოტვირთეთ TJBot-ის ორიგინალი და დატესტეთ (Enter)
•	აუდიოს კონფიგურაცია (leave port for jack-audio enabled) (N)
•	გადატვირთეთ (Y)

6. დააინსტალირეთ node.js version 9:

```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. Terminal-ში გახსენით  ფოლდერი „Desktop“:

```
cd Desktop
```

8. დააინსტალირეთ ერთ-ერთი TJBotCZ პროგრამა (tjbotcz_lite, tjbotcz, tjbotcz_iot):

```
git clone https://github.com/tjbotcz/<name of tjbotcz program>.git
```

9. Terminal-ში გახსენით ახალ შექმნილი ფოლდერი “tjbotcz_lite”, "tjbotcz" or tjbotcz_iot":

```
cd <name of the folder>
```


10. გადმოტვირთეთ ფაილი package.json ფოლდერში ,იგივე პროგრამით, რომელიც იყო გადმოტვირთული მე-8 საფეხურზე:

```
npm install
```

11. TJBot-თან საუბრისთვის, ჩვენ გვესაჭიროება შემდეგი სერვისები, რომელიც მოცემულია IBM Cloud-ში:

Watson Assistant (სერვისი დიალოგის შექმნისთვის)
Speech to Text (ხმოვანი სერვისი ტექსტის ფაილში)
Text to Speech (ტექსტური სერვისის სინქრონიზირება ხმოვანში)
Visual Recognition (სურათის ანალიზირების სერვისი)

მომსახურების გაწევა ინსტრუქციის მიხედვით : ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

თუ თქვენ გაქვს ყველა სერვისი, მაშინ გავაგრძელოთ. შეიყვანეთ მონაცემები კონკრეტული სერვისისთვის კონფიგურაციის ფაილში (credentials.js). რადგან მონაცემები საკმაოდ გრძელია , საუკეტესო გამოსავალია TJBot -ის დისტანციურად დაკავშრება კომპიუტერთან, სადაც შექმნით Watson services და გადმოაკოპირებთ.თუ Mac-ს მომხმარებელი ბრძანდებით, გამოიყენებთ terminal, თუ Windows-ით სარგებლობთ, გამოიყენებთ [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy არის პროგრამის დისტანციური წვდომა და თქვენ უნდა დააინსტალიროთ იგი. როდესაც იყენებთ Terminal-ს ან PuTTy-ს  გამოიყენეთ TJBot ( თქვენ დაგჭირდებათ იგივე network/WiFi როზეც  TJBot-ია შეერთებული)

MacOS:
```
ssh pi@<ipadresa>
```
  Windows (enter IP address of TJBota into highlighted field):

  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)

პაროლი დაგჭირდებათ, რომელიც არის : **_raspberry_**.

13.  Terminal-ში (or cmd window in Windows) გადადით folder-ში
 
კონფიგურაციის ფაილით:

```
cd Desktop/tjbotcz_lite/configuration
```

14. შექმენით ფაილების ასლი credentials.default.js და config.default.js, შემდეგნ დაასახელეთ credentials.js and config.js შესაბამისად.თქვენ ასევე შეგიძლიათ  განახორციელოთ ეს დისტანციურად Terminal/CMD window -ით: 

```
cp config.default.js config.js
cp credentials.default.js credentials.js
```

15. ტექსტურ რედაქტორში სახელად ‘nano’ ჩაწეერეთ საჭირო მონაცემები ინდივიდუალურ სერვისისთვის.

nano credentials.js

იხილეთ სურათზე ქვემოთ მდებარე ადგილები, რომლებიც უნდა შეივსოს Watson- ის მონაცემებით (არ წაშალოთ ნიშნები).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  ფაილის დახურვა და შენახვა: CTRL+X, Y, Enter.

ეხლა კი გააცოცხლეთ TJBot!!! დაბრუნდით Desktop/tjbotcz_lite ... და მზად არის!
TJBot- შექმნილია ისე რომ ის საუბრობს მამაკაცის ხმით და რეაგირებს Michael-ის (მიშელი) სახელზე. ეს იმას ნიშნავს, რომ ის რეაგირებს წინადადებებზე სადაც მისი სახელია ნახსენები.

```
cd ..
sudo node tjbotcz_lite.js
```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

## სასარგებლო რჩევები: 
### როგორ დავაკოპიროთ ფაილები Windows-დან Raspberry Pi-ში, როდესაც ვიყენებთ command line 

Open CMD line და მიმღებს(addresser). თუ ფაილის გადმოკოპირება გსურთ (cd = change directory). შემდგომ გამოიყენეთ command line, სადაც პირველრიგში უნდა შეამოწმოთ თუ PuTTY უკვე დაყენებულია და ასევე შეამოწმოთ  თუ C:\Program Files\PuTTY\pscp.exe. მუშაობს. ფაილი : “file.txt”  არის ფაილების კოპირების სახელი, რითაც იცვლება "your_pi" - ი IP მისამართში თქვენი Raspberry Pi-სი (უნდა იყოს იგივე ქსელში):

```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```

### როგორ გადმოვაკოპოროთ ფაილები Mac OS-დან Raspberry Pi-ში command line-ის გამოყენებით (Mac OS-ში). 

გახსენით „CMD line“ და „addresser“. მანდ მდებარეობს ფაილი, რომელიც უნა გადმოაკოპიროთ(cd = change directory). შემდეგ გამოიყენეთ command line, სადაც “file.txt” არის ფაილის კოპირებისთვის სახელი და შეცვლეთ “your_pi” IP მისამართი თქვენ Raspberry Pi ( ეს უნდა განახორციელოთ ერთ ინტერნეტ ქსელზე). 

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```

### როგორ გადმოვაკოპიროთ ფაილები Rasberry Pi-დან Mac OS-ში, როდესაც ვიყენებთ command line (v Mac Os)

```
logout
```

Terminal-ლი in Mac OS იყენებს command(ბრძანებას)ფაილების გადმოსაკოპირებლად:

```
scp <username na Raspberry Pi>@<ip adresa Raspberry Pi>:/<full path to file on Raspberry pi> <full path to where files is to be saved on Mac OS>
```

Example:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

### პაროლი დაგჭირდებათ Raspberry Pi-ში.

როგორ შევქმნათ Raspberry Pi-ის  IP address (IP მისამართი): დაუკავშრდით Raspberry Pi-ის SSH ან PuTTy გამოყენებით.შემდეგ გამოიყენეთ „command“ :

```
sudo nano /etc/dhcpcd.conf
```

გახსნილ ფაილში, un-comment ნაწილი სტატიკურ მისამართის პარამეტრებით და ჩაწერეთ სწორი მისამართი (IP address, როუტერის IP address)

### როგორ შევცვალოთ Raspberry Pi-ის მოცულობა, როდელაც ვიყენებთ command line-ს. 

შეუერთეთ Raspberry Pi-ი SSH ან  PuTTY-ის გამოყენებით. შემდეგი  კოდის ხაზი შეიცვლება 90%-ით. მოცულობა უნდა შეიცვალოს არაწრფივი გზით, ასე რომ განსხვავება 90% -დან 95% -მდეა.

```
amixer  sset PCM,0 90%
```

ან თქცენ ასევე სეგიძლიათ განახორციელოთ short-cut(შემცირება),რომელიც მოცულობას შეცვლის. ედიტორში nano გაიხსნება .bashrc file:

```
nano ~/.bashrc
```

ასევე ფაილის ბოლოში დაამატეთ 

```
# Increase volume by 5% 
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Decrease volume by 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```

გადატვირთეთ Raspberry-Pi-ი, ჩაწერეთ `volup`  ან  `voldown`  Terminal-ში და მოცულობა შეიცვლება up/down by 5%.( 5%-ით).

### აუდიოს აწყობის პროცესი jack-ზე (ბუდეში).

 იმ შემთძვევაშიც კი თუ ხმა აწეულია მაქსიმუმზე, ზოგჯერ შეუძლებელია TJBot -ის გაგონება. სავარაუდოდ, აუდიო მიდის HDMI- ზე და არ არის დაკავშირებული სპიკერიზე.ჯეკ კონექტორის დასაყენებლად, გამოიყენეთ შემდეგი: 

```
sudo amixer cset numid=3 1
```
ბოლო ნომერი გიჩვენებთ შედეგს (0=auto, 1=jack, 2=HDMI)

### მეტი ადგილი დაუტოვეთ microSD Card-ს
თუ თქვენ გაქვს 16GB microSD card-ი, პრობლება არ შეგექმნებათ. იმ შემთხვევაში თუ თქვენ  8GB card გაქვს,ინსტალაციის შემდგომ დაგრჩებათ მხოლოდ 2GB. თქვენ შეგიძლიათ წაშალოთ Wolfram და LibreOffice უფრო მეტი სივრცის მისაღებად, ვინაიდან აღარ დაგჭირდებათ ზემო აღნიშნული პროგრამები TJBot-თან მუშაობისთვის. დამატებით 1GB თავისუფალი ადგილი გამოგიჩნდებათ.

წასაშლელი პროგრამები:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

 
