# IBM Cloud: Watson paslaugos

Jums reikės Watson paslaugų, kurias galima įsigyti IBM Cloud, kad TJBot prisikeltų gyvenimui - būtent jūs suteiksite jam galią:

* Klausymas - kalbos į tekstą paslauga, konvertuojanti balso failus į tekstą, kurį galima toliau apdoroti.
* Kalbėjimas - teksto į kalbą paslauga, konvertuojanti tekstą į balso failus, kuriuos TJBot naudoja kalbėjimuisi.
* Matymas - Vizualinio atpažinimo paslauga, analizuojanti nuotraukas, kad TJBot galėtų jums pasakyti, ką jis mato.
* Pokalbiai - Watson Asistento paslauga, sukurianti dialogo logiką, kad galėtumėte turėti aukšto lygio pokalbį su TJBot.

Norint įdiegti šias paslaugas, turite turėti sąskaitą IBM Cloud (registracija yra nemokama). Lite nemokamas paslaugas galite teikti nemokamai. Kiekviena paslauga turi savo įgaliojimus, kuriuos turėsite įvesti į TJBot (credentials.js) konfigūracijos rinkmeną.

Sukurkime paslaugas ir atsisiųskime pažymėjimus.

## Registracija į IBM Cloud

Galite užsiregistruoti IBM Cloud adresu www.bluemix.net.

Registracija yra nemokama (nereikia kredito kortelės) ir leidžia jums teikti reikiamas paslaugas LITE versijoje, to pakanka mūsų poreikiams. Visos paslaugos yra prieinamos per skirtuką Catalog.

## Kalbos į tekstą paslauga

Kataloge ieškokite _**Speech to Text**_ spustelėkite sukurti. Bus atidarytas naujas puslapis su paslaugos konfigūracija. Paspaudus piktogramą rodyti, bus rodomi paslaugos patvirtinimai (vartotojo vardas ir slaptažodis). Turėsite juos įvesti į TJBot konfigūracijos failą (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Teksto į kalbą paslauga

"Kataloge" ieškokite _**Text to Speech**_ spustelėkite sukurti. Bus atidarytas naujas puslapis su paslaugos konfigūracija. Paspaudus piktogramą rodyti, bus rodomi paslaugos patvirtinimai (vartotojo vardas ir slaptažodis). Turėsite įvesti juos į TJBot konfigūracijos failą (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Vizualinio atpažinimo paslauga

"Kataloge" ieškokite _**Visual Recognition**_ spustelėkite sukurti. Bus atidarytas naujas puslapis su paslaugos konfigūracija. Paspaudus piktogramą rodyti, bus rodomi paslaugos įgaliojimai. Turėsite įvesti juos į TJBot konfigūracijos failą (credentials.js). Šios paslaugos atveju tai vadinamasis API RAKTAS, kurio jums reikės.

![Vaizdo atpažinimo API RAKTAS](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Watson Asistento paslauga

Watson Asistentas yra dialogo (pokalbių) kūrimo įrankis. Greitai pradžiai, parengėme paprastą dialogą, kurį galite importuoti į paslaugą prieš pradėdami kurti savo pokalbius. [Atsisiųskite dialogą čia] (https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). Kataloge ieškokite _**Watson Asisstant**_ spustelėkite sukurti. Bus atidarytas naujas puslapis su paslaugos konfigūracija. Paspaudę mygtuką paleisti, jūs atidarysite naują langą - tai tikrasis pokalbių kūrimo įrankis. Pasirinkite Workspace skirtuką, kuriame rasite piktogramą atsisiųsto dialogo failo importavimui (žr. Paveikslėlį žemiau).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

Importavus dialogą, atsidarys naujai sukurta darbo vieta. Piktograma, imituojanti sraigę, pateiks jums reikalingus duomenis apie TJBot konfidencialumą (credentials.js). Watson Asistento paslaugos atveju, egzistuoja 3 įgaliojimai: darbo vietos id, vartotojo vardas ir slaptažodis.

![WA įgaliojimai](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)
