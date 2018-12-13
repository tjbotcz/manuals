# IBM Cloud: Watson Services (Watson usluge) 
 
Watson usluge koje su dostupne na  IBM Cloudu će ti trebati da oživiš svog TJBot-a - posebice ako mu želiš dati mogućnost: 
 
* Slušanja -  usluga govor u tekst, pretvaranje audio datoteka u tekst koji se može dalje obrađivati, 
* Govora - usluga tekst u govor, pretvaranje teksta u audio datoteke koje TJBot koristi za govor,
* Vida - usluga vidnog prepoznavanja analizirajući slike, tako da ti TJBot može opisati što vidi,
* Chatanja - usluga Watson asistenta stvara dijaloški slijed, koji ti omogućuje chat visoke kvalitete s TJBot-om.
 
Za pristup i postavljanje navedenih usluga, trebati će ti račun na IBM Cloud-u (registracija je besplatna). Usluge u lite inačici su besplatne. Svaka usluga zahtjeva pristupne podatke koje moraš unesti da pristupiš konfiguracijskoj datoteci TJBotCZ-a (credentials.js). 
 
Krenimo postaviti usluge i zapisati pristupne podatke! 
 
## Registracija na IBM Cloud 
 
Na IBM Cloud se možeš registrirati preko stranice www.bluemix.net. 
 
Registracija je besplatna (nisu potrebne kreditne kartice) i omogućuje ti korištenje potrebnih usluga u LITE inačici koje su dovoljne za tvoje potrebe. Sve su usluge dostupne putem "Catalog" kartice.  
 
## Usluga govor u tekst
 
Potraži u "Catalog" kartici _**Speech to Text**_ i klikni na "Create". Otvoriti će se nova stranica za konfiguraciju. Klikom na "Show" ikonu otkriti ćeš pristupne podatke usluge (korisničko ime i lozinka). Trebati ćeš ih unijeti u TJBotCZ  configuracijsku datoteku (credentials.js). 
 
![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png) 
 
## Usluga tekst u govor
 
Potraži u "Catalog" kartici _**Text to Speech**_ i klikni na "Create". Otvoriti će se nova stranica za konfiguraciju. Klikom na "Show" ikonu otkriti ćeš pristupne podatke usluge (korisničko ime i lozinka). Trebati ćeš ih unijeti u konfiguracijsku datoteku TJBotCZ-a (credentials.js). 
 
![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png) 
 
## Usluga vidno prepoznavanje
 
Potraži u "Catalog" kartici _**Visual Recognition**_ i klikni na "Create". Otvoriti će se nova stranica za konfiguraciju. Klikom na "Show" ikonu otkriti ćeš pristupne podatke usluge (korisničko ime i lozinka). Trebati ćeš ih unijeti u TJBotCZ  configuracijsku datoteku (credentials.js).  Prilikom korištenja ove usluge trebat će ti samo tzv. API KEY (API ključ).
 
![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png) 
 
## Usluga Watson asistent
 
Watson Assistant (Watson asistent) je alat za stvaranje dijaloga (chatova). Za brzi start pripremili smo jednostavan dijalog koji možeš učitati u uslugu prije nego kreneš stvarati svoje vlastite dijaloge.  
[Ovdje možeš spustiti dijaloge](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). 
Potraži u "Catalog" kartici  _**Watson Assistant **_ i klikni na "Create”. Otvoriti će se nova stranica za konfiguraciju. Klikom na "Launch" dugme otvoriti će se novi prozor - alat za stvaranje chatova. Odaberi "Workspace" karticu, gdje ćeš naći ikonu za učitavanje prethodno spuštene dijaloške datoteke (vidi sliku ispod). 
 
![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png) 
 
Nakon učitavanja dijaloga, pojaviti će se novonastali radni prostor. Ikona nalik na puža dovesti će te do unosa korisničkih podataka koje ćeš morati unijeti za pristup konfiguracijskoj datoteci za TJBot-a (credentials.js). Prilikom korištenja usluge Watson asistenta 3 su pristupna podatka:  identifikacijska oznaka radnog prostora, korisničko ime i lozinka. 
 
![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png) 

