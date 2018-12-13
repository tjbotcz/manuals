# Oživljavanje TJBot-a (na Raspberry Pi-u) 
 
Izaberi svoj put… 
1. [Brzi start putem gotove slike](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image) 
2. [Započni od nule kao stručnjak](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro) 
3. Neki savjeti i trikovi koji bi ti mogli koristiti 
 
    * [Kako kopirati datoteke iz Windows OS-a na Raspberry Pi koristeći tekstualno sučelje](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line) 
    * [Kako kopirati datoteke iz Mac OS-a na Raspberry Pi koristeći tekstualno sučelje (u Mac OS-u)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os) 
    * [Kako kopirati datoteke iz Rasberry Pi-a na Mac OS koristeći tekstualno sučelje (u Mac OS-u)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-rasberry-pi-to-mac-os-using-command-line-v-mac-os) 
    * [Kako postaviti IP adresu Raspberry Pi-a](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address) 
    * [Kako podesiti glasnoću zvuka Raspberry Pi-a koristeći tekstualno sučelje](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line) 
    * [Postavljanje audio izlaza na jack](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack) 
    * [Stvaranje više prostora za pohranu na microSD kartici](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card) 
     
## Brzi start putem gotove slike 
 
Sigurno jedva čekaš imati svojeg TJBota, spremnog za korištenje. Stoga smo pripremili gotovu sliku sustava na kojoj je već konfiguriran Raspbian za TJBot CZ. 
 
Potrebni su ti: 
 
* internetska veza za spuštanje Raspbian OS-a i softvera za instalaciju slike na karticu
* računalo s utorom  za SD/ microSD karticu ili SD/microSD čitač
* USB tipkovnica, USB miš
* LCD s HDMI portom i HDMI kabel. 
 
 
Postupak: 
1. Spusti gotovu sliku [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) i raspakiraj je. 
 
2. Spusti i instaliraj softver potreban za instalaciju slike Raspbiana na microSD karticu (npr. Etcher: https://etcher.io/ . Prilikom instalacije prethodno spuštene slike na microSD karticu odaberi tjbotcz_lite.img datoteku, odaberi umetnutu microSD karticu i…Flash!) 
![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing") 
 
3. Umetni prethodno instaliranu microSD karticu u Raspberry-Pi, spoji uređaj s HDMI ekranom, tipkovnicom, mišem i s RJ-45 (eternet) internet kabelom. Druga opcija je spajanje putem WIFI veze  (ako koristiš WiFi morati ćeš konfigurirati vezu preko Raspbianovog grafičkog korisničkog sučelja, a postavke će biti pohranjene pri svakom slijedećem spajanju). Povezanost s internetom biti će ti potrebna i u slijedećem koraku. 
 
4. Na radnoj površini Raspbiana pripremljena je skripta "run-me-first.sh".  Pokreni je (dvostruki klik i naredba execute u tekstualnom sučelju). Skripta će spustiti najnoviju inačicu programa [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) sa interneta te instalirati potrebne dependencije. 
 
5. Kako bi chat s TJBotom bio moguć, na IBM Cloudu moraju biti  omogućene slijedeće usluge: 
 
* Watson pomoćnik (usluga za stvaranje dialoga/chatova) 
* govor u tekst (usluga transkribiranja glasovne datoteke u tekstualnu) 
* tekst u govor (usluga pretvaranja teksta u glas) 
* vidno prepoznavanje (usluga analize slika) 
 
Pokreni usluge prema uputstvima u ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md) mapi. 
 
6.Ako je za tebe prethodan korak već rješen, dobrodošao/la natrag u postupak i nastavimo dalje! 
Unesi korisničke podatke svake pojedine usluge u konfiguracijsku datoteku (credentials.js). Pošto korisnički podaci tvore dugačke linije, najbolji način za njihov unos je putem daljinskog povezivanja s  TJBotom s računala, na kojem su omogućene Watson usluge, a potom njihovo kopiranje i lijepljenje sa računala na TJBot. Ako si Mac korisnik, koristi program terminal, a ako koristiš Windows OS, koristi [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy je program daljinskog pristupa i potrebno ga je prethodno instalirati na računalo. Koristeći program terminal ili PuTTy spoji se s TJBotom (pritom je potrebno biti na istoj mreži/WiFiju kao i TJBot): 
 
  MacOS: 
  ``` 
  ssh pi@<ipadresa> 
  ``` 
  Windows (unesi IP adresu TJBot-a u označeno polje): 
 
  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png) 
 
  Pojaviti će se upit za lozinku. Generirana lozinka je: **_raspberry_**. 
 
7. U terminalu (ili cmd prozoru u Windowsu) slijedi put do mape s konfiguracisjkim datotekama: 
 
  ``` 
  cd Desktop/tjbotcz_lite/configuration 
  ``` 
8. Napravi kopiju credentials.default.js i config.default.js  datoteka i nazovi ih credentials.js i config.js. To možeš napraviti i putem daljinskog povezivanja u Terminalu ili u CMD prozoru: 
  ```   
  cp config.default.js config.js 
  cp credentials.default.js credentials.js 
  ``` 
9. U alat za obradu teksta zvan nano umetni potrebne pristupne podatke za odgovarajuće usluge. 
  ``` 
  nano credentials.js 
  ``` 
  Vidi sliku dolje na kojoj su označena sva mjesta koja se moraju ispuniti korisničkim podacima Watson usluga  (ne briši navodnike). 
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png) 
  Zatvaranje i spremanje datoteke CTRL+X, Y, Enter. 
   
10. A sada, oživi svogTJBota !!!  Vrati se do mape Desktop/tjbotcz_lite ... i krenimo. 
TJBot je namješten da govori muškim glasom i odgovara na ime Michael. To znači da će prepoznati samo one rečenice koja sadrže ime Michael. Više informacija o TJBotCZ lite programu i kako ga koristiti, naći ćeš na ovom mjestu [repository](https://github.com/tjbotcz/tjbotcz_lite). 
  ``` 
  cd .. 
  sudo node tjbotcz_lite.js 
  ``` 
   
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif) 
 
--- 
 
## Započni od nule kao stručnjak
 
Raspberry-Pi koristi Raspbian kao operativni sustav, koji je sagrađen na Debian Linuxu. 
Sav Raspbian je na microSD kartici. Stoga je nužno prvo instalirati operativni sustav Raspbian na microSD karticu.  
Potrebni su nam: 
 
*internetska veza za spuštanje Raspbian OS i softvera za instalaciju slike na karticu
*računalo s utorom za SD/ microSD karticu ili  SD/microSD čitač
*USB tipkovnica, USB miš 
*LCD s HDMI portom i HDMI kabelom. 
 
Upute: 
1. Spusti Raspbian OS https://www.raspberrypi.org/downloads/ . 
 
![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download") 
 
2. Spusti i instaliraj softver, kako bi instalacija slike Raspbian bila moguća, za npr. Etcher https://etcher.io/ , a nakon toga instaliraj Raspbian OS  na microSD karticu (klikni/odaberi downloaded .img file, potom već spojenu SD karticu, i…Flash!) 
 
![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing") 
 
3. Umetni prethodno instaliranu microSD karticu u Raspberry-Pi, spoji uređaj s HDMI ekranom, tipkovnicom, mišem i s RJ-45 (eternet) internet kabelom. Druga opcija je spajanje putem WIFI veze  (ako koristiš WiFi morati ćeš konfigurirati vezu preko Raspbianovog grafičkog korisničkog sučelja, a postavke će biti pohranjena pri slijedećem spajanju). Povezanost s internetom biti će ti potrebna u koraku broj 5.
  
4. Dozvoli spajanje Raspberry-Pi i SSH-a (Secure Shell mrežni protokol ), kako bi kasnije bilo moguće nastaviti s daljinskim povezivanjem Raspberry-Pi-a putem terminala ili PuTTYja (Windows). U terminal  napiši: 
``` 
sudo raspi-config 
``` 
Otvoriti će se izbornik. 
Izaberi “Interfacing Options” (razmjena opcija). 
Izaberi “SSH” i omogući ga. 
 
5. Open Terminal and run: 
``` 
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh - 
``` 
Ova naredba će spustiti skriptu sa servera koja će pokrenuti interaktivni vodič u prozoru terminala. Pomoću ovog vodiča konfigurirati ćeš Raspberry Pi za korištenje TJBota: 
 
* TJBot ime (ostavi raspberrypi)  - (Enter) 
* IPv6 (disable) - (Y) 
* Google DNS (enable) - (Y) 
* settings local (language) (Y) 
* update OS Raspbian(Y) 
* update to newer version of Node.js (N) 
* connecting camera (Y) 
* downloading original TJBot and test scenarios (Enter) 
* configuring audio output (leave port for jack-audio enabled) (N) 
* reboot (Y) 
 
6. Instaliraj node.js inačicu 9: 
``` 
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash - 
sudo apt-get install -y nodejs 
``` 
7. Otvori mapu Desktop u terminalu: 
``` 
cd Desktop 
``` 
8. Instaliraj jedan od TJBotCZ programa(tjbotcz_lite, tjbotcz, tjbotcz_iot): 
``` 
git clone https://github.com/tjbotcz/<name of tjbotcz program>.git 
``` 
9. U terminalu otvori nedavno kreiranu mapu “tjbotcz_lite”, "tjbotcz" ili tjbotcz_iot": 
``` 
cd <name of the folder> 
``` 
10. Spusti dependencije definirane u datoteci package.json u mapi s programom spuštenim u prethodnom koraku broj 8: 
``` 
npm install 
``` 
 
11. Kako bi chat s TJBotom bio moguć, na IBM Cloudu moraju biti  omogućene slijedeće usluge: 
 
* Watson pomoćnik (usluga za stvaranje dialoga/chatova) 
* govor u tekst (usluga transkribiranja glasovne datoteke u tekstualnu) 
* tekst u govor (usluga pretvaranja teksta u glas) 
* vidno prepoznavanje (usluga analize slika) 
 
Pokreni usluge prema uputstvima u ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md) mapi. 
 
12. Imaš li već omogućene usluge, dobrodošao/la natrag i nastavimo dalje! 
Unesi korisničke podatke svake pojedine usluge u konfiguracijsku datoteku (credentials.js). Pošto korisnički podaci čine dugačke linije, najbolji način za njihov unos je putem daljinskog povezivanja s  TJBotom sa računala s kojeg su omogućene Watson usluge, a potom njihovo kopiranje i lijepljenje sa računala na TJBot. Ako si Mac korisnik, koristi program terminal, a ako koristiš Windows OS, koristi [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy je program daljinskog pristupa i potrebno ga je prethodno instalirati na računalo. Korištenje programa terminala ili PuTTy spoji se s  TJBotom (potrebno je biti na istoj mreži/WiFiju kao i TJBot): 
 
 
MacOS: 
  ``` 
  ssh pi@<ipadresa> 
  ``` 
  Windows (unesi IP adresu TJBot-a u označeno polje): 
 
  ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png) 
 
  Pojaviti će se upit za lozinku. Generirana lozinka je: **_raspberry_**. 
 
13. U terminalu (ili cmd prozoru u Windowsu) slijedi put do mape s konfiguracisjkim datotekama: 
 
  ``` 
  cd Desktop/tjbotcz_lite/configuration 
 
  ``` 
14. Napravi kopiju credentials.default.js i config.default.js  datoteka i nazovi ih credentials.js i config.js. To možeš napraviti i putem daljinskog povezivanja u Terminalu ili u CMD prozoru: 
  ```   
  cp config.default.js config.js 
  cp credentials.default.js credentials.js 
  ``` 
 
15. U alat za obradu teksta zvan nano umetni potrebne pristupne podatke za odgovarajuće usluge. 
  ``` 
  nano credentials.js 
  ``` 
  Vidi sliku dolje na kojoj su označena sva mjesta koja se moraju ispuniti korisničkim podacima Watson usluga  (ne briši navodnike). 
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png) 
  Zatvaranje i spremanje datoteke CTRL+X, Y, Enter. 
   
16. A sada, oživi svogTJBota !!! Vrati se do mape Desktop/tjbotcz_lite ... i krenimo. 
  TJBot je namješten da govori muškim glasom i odgovara na ime Michael. To znači da će prepoznati samo one rečenice koja sadrže ime Michael. Više informacija o TJBotCZ lite programu i kako ga koristiti, naći ćeš na ovom mjestu [repository](https://github.com/tjbotcz/tjbotcz_lite). 
  ``` 
  cd .. 
  sudo node tjbotcz_lite.js 
  ``` 
   
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif) 
 
--- 
 
## Neki savjeti i trikovi koji bi ti mogli koristiti 
 
### Kako kopirati datoteke s Windowsa na Raspberry Pi koristeći tekstualno sučelje
Otvori naredbenu liniju i adresant. Kopiraj datoteku (cd = change directory).  Potom, koristeći slijedeću naredbenu liniju, gdje prije svega moraš utrditi da li je PuTTYveć instaliran i provjeri da li C:\Program Files\PuTTY\pscp.exe.  radi. Datoteka: “file.txt”je ime za kopiranje datoteka pa stoga promijeni “your_pi” u IP adresu svog Raspberry Pija (moraju biti u istoj mreži): 
 
``` 
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite 
``` 
 
 
### Kako kopirati datoteke s  Mac OS to Raspberry Pi koristeći tekstualno sučelje (u Mac OSu) 
Otvori naredbenu liniju i adresant.  Kopiraj datoteku (cd = change directory). Datoteka: “file.txt”je ime za kopiranje datoteka pa stoga promijeni “your_pi” u IP adresu svog Raspberry Pija (moraju biti u istoj mreži): 
 
``` 
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite 
``` 
 
 
### Kako kopirati datoteke s Rasberry Pija u Mac OS koristeći tekstualno sučelje(u Mac OS-u) 
Ako je TJBot spojen putem SSH, prvo se odjavi: 
 
``` 
logout 
``` 
 
U terminalu Mac OS-a upotrijebi naredbu za kopiranje datoteka: 
 
``` 
scp <ukorisničko ime na Raspberry Pi-u>@<ip adresa Raspberry Pija>:/<cijela adresa datoteke na Raspberry Pi-u> <cijela adresa do mjesta gdje su datoteke pohranjene na Mac OS> 
``` 
 
Primjer: 
 
``` 
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Ivan/Desktop 
``` 
 
Pojaviti će se zahtjev za unos lozinke u Raspberry Pi. 
 
 
### Kako namjestiti IP adresu  Raspberry Pi-a
Spoji se na Raspberry Pi putem SSH ili PuTTy-a. Potom unesi naredbu: 
 
``` 
sudo nano /etc/dhcpcd.conf 
``` 
 
U otvorenoj datoteci zamjeni postavke statične adrese i unesi ispravne podatke (IP adresa, IP adresa routera). 
 
 
 
### Kako promijeniti jačinu  zvuka na Raspberry Pi-u koristeći tekstualno sučelje 
Spoji se s  Raspberry Pi-em putem SSH ili PuTTY-a.  Slijedeća linija koda će promijeniti jačinu uređaja na 90%. Pošto bi se jačina trebala nelinearno mijenjati, razlika između 90 % i 95 % morala bi biti zamjetna. 
 
``` 
amixer  sset PCM,0 90% 
``` 
 
Slijedeća opcija je načiniti prečac za promjenu jačine zvuka. U nano alatu za uređivanje otvori datoteku .bashrc: 
 
``` 
nano ~/.bashrc 
``` 
 
i na kraju datoteke dodaj  
 
``` 
# povećanje jačine za 5% 
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%' 
# smanjenje jačine za 5% 
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%' 
``` 
Ponovo pokreni Raspberry-Pi. Zatim možeš samo napisati `volup`  ili  `voldown` u terminalu i jačina će se mijenjati gore/dolje za 5%. 
 
 
 
### Postavljanje audio izlaza na jack 
Ponekad ne možeš čuti TJBot dovoljno glasno, premda je jačina zvuka podešena na maksimum. Najvjerojatnije zvuk izlazi na HDMI, a ne na spojeni zvučnik (preko jacka). Za podešavanje izlaza na jack konektor koristi slijedeće: 
 
``` 
sudo amixer cset numid=3 1 
``` 
Zadnji broj određuje izlaz (0=auto, 1=jack, 2=HDMI) 
 
 
### Dobijanje više mjesta za pohranu na microSD  kartici
Ako imaš microSD karticu od 16GB, trebalo bi ti biti dosta prostora za pohranu. Međutim, ako imaš karticu od 8GB, nakon instalacije ostati će ti otprilike 2GB slobodnog prostora. Možeš deinstalirati Wolfram i LibreOffice da oslobodiš više prostora, pošto te programe nećeš trebati za rad s TJBotom. I time ćeš dobiti dodatnih 1GB slobodnog prostora. 
 
Za uklanjanje programa: 
 
``` 
sudo apt-get purge wolfram-engine 
sudo apt-get purge libreoffice* 
sudo apt-get autoremove 
``` 
 
--- 
 

