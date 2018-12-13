# IBM Cloud: Watson Services

Na to, aby ste oživili TJBota, budete potrebovať služby Watson services dostupné v IBM Cloud - konkrétne mu dodáte tieto schopnosti:

* Počúvanie -  služba Speech to Text: konverzia hlasových súborov na text, s ktorým môže TJBot ďalej pracovať. 
* Rozprávanie - služba Text to Speech: konverzia textu na hlasové súbory, ktoré TJBot používa pri rozprávaní.
* Videnie - služba Visual Recognition: analýza obrázkov, ktoré TJBot vyfotí.
* Konverzácia - služba Watson Assistant: vytváranie dialógovej logiky, ktorá vám umožní vysoko kvalitný rozhovor s TJBotom.

Ak chcete tieto služby používať, potrebujete účet na IBM Cloud (registrácia je bezplatná). Následne môžete spustiť vyššie uvedené služby (v lite verzii zdarma). Každá služba má svoje prihlasovacie údaje, ktoré budete musieť zadať do konfiguračného súboru na TJBotCZ (credentials.js).

Poďme si teraz vytvoriť služby a získať tak ich prihlasovacie údaje.

## Registrácia na IBM Cloud

Na IBM Cloud sa môžete sa zaregistrovať na stránke www.bluemix.net.

Registrácia je zdarma (nebudete potrebovať žiadnu kreditnú kartu) a umožňuje obstarať si služby potrebné pre TJBota v LITE verzii, ktorá je pre vaše potreby dostatočná. Všetky služby sú dostupné cez záložku "Catalog". 

## Služba Speech to Text

V záložke "Catalog" vyhľadajte službu _**Speech to Text**_ a kliknite na tlačidlo "Create". Otvorí sa nová stránka s parametrami služby. Kliknutím na ikonku "Show" zobrazíte prihlasovacie údaje k službe (používateľské meno a heslo). Tie budete musieť zadať do konfiguračného súboru na TJBotCZ  (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Služba Text to Speech

V záložke "Catalog" vyhľadajte službu  _**Text to Speech**_ a kliknite na tlačidlo "Create". Otvorí sa nová stránka s parametrami služby. Kliknutím na ikonku "Show" zobrazíte prihlasovacie údaje k službe (používateľské meno a heslo). Tie budete musieť zadať do konfiguračného súboru na TJBotCZ (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Služba Visual Recognition

V záložke "Catalog" vyhľadajte službu _**Visual Recognition**_ a kliknite na "Create". Otvorí sa nová stránka s parametrami služby. Kliknutím na ikonku "Show" zobrazíte prihlasovacie údaje k službe. Tie budete musieť zadať do konfiguračného súboru na TJBotCZ (credentials.js). V prípade tejto služby budete potrebovať jedine takzvaný API KEY. 

![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Služba Watson Assistant

Watson Assisstant je nástroj na vytváranie dialógov (chatov). Aby ste mohli rýchlo začať, pripravili sme jednoduché dialógové okno, ktoré môžete importovať do služby skôr, ako začnete vytvárať svoje vlastné rozhovory (chaty). [Dialóg si stiahnte tu](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). V záložke "Catalog" vyhľadajte _**Watson Assistant**_ a kliknite na "Create". Otvorí sa nová stránka s parametrami služby. Kliknutím na tlačidlo "Launch" získate nové okienko - skutočný nástroj na vytváranie chatov. V záložke "Workspace" nájdete ikonku na importovanie stiahnutého súboru s dialógom (pozri obrázok nižšie).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

Po tom, ako importujete dialóg, sa otvorí novovytvorený pracovný priestor. Prostredníctvom ikonky s podobou slimáka sa dostanete k potrebným prihlasovacím údajom, ktoré potrebujete pre konfiguračný súbor na TJBotovi (credentials.js). Pre službu Watson Assistant exitujú 3 prihlasovacie údaje: workspace id (prístup do pracovného priestoru), username (používateľské meno) a password (heslo).

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)

---
