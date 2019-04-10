# IBM Cloud: Watson Services

Služby Watson dostupné na IBM Cloudu využijete k tomu, abyste oživili TJBota - konkrétně mu tím dáte následující schopnosti:
* Poslouchat - služba Speech to Text, která převede hlas na text, se kterým může TJBot dále pracovat.
* Mluvit - služba Text to Speech, která převede textový výstup na hlas, kterým TJBot mluví.
* Vidět - služba Visual Recognition umožňuje analyzovat obrázky, které TJBot vyfotí.
* Konverzovat - služba Watson Assisstant vytváří logiku dialogu, který s vámi TJBot vede.

Abyste mohli tyto služby používat, je potřeba vytvořit si účet na IBM Cloudu (registrace je zdarma) a poté spustit výše uvdené služby (v LITE verzi zdarma). Každá služba má své přihlašovací údaje, které je potřeba zadat do souboru "credentials.js".

Pojďme tedy vytvořit služby a získat tak jejich přihlašovací údaje. 

## Registrace do IBM Cloudu

Registrovat se do IBM Cloudu můžete na adrese www.bluemix.net.

Registrace je zdarma a získáte tak přístup k službám potřebným pro TJBota. Tyto služby jsou v tzv. LITE verzi, která je dostačující. Veškeré služby naleznete v záložce "Catalog". 

## Služba Speech to Text

V záložce "Catalog" vyhledejte službu _**Speech to Text**_ a klikněte na tlačítko "Create". Spustí se vám stránka s parametry služby. Kliknutím na ikonu "Show" si zobrazíte přihlašovací údaje ke službě (API KEY a URL). Ty budete potřebovat vložit do konfiguračního souboru na TJBotovi (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)

## Služba Text to Speech

V záložce "Catalog" vyhledejte službu _**Text to Speech**_ a klikněte na tlačítko "Create". Spustí se vám stránka s parametry služby. Kliknutím na ikonu "Show" si zobrazíte přihlašovací údaje ke službě (API KEY a URL). Ty budete potřebovat vložit do konfiguračního souboru na TJBotovi (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)

## Služba Visual Recognition

V záložce "Catalog" vyhledejte službu _**Visual Recognition**_ a klikněte na tlačítko "Create". Spustí se vám stránka s parametry služby. Kliknutím na ikonu "Show" si zobrazíte přihlašovací údaje ke službě. Ty budete potřebovat vložit do konfiguračního souboru na TJBotovi (credentials.js). V případě této služby jde pouze o tzv. API KEY, který budete potřebovat.

![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Služba Watson Assisstant

Watson Assisstant je nástroj pro vytváření dialogů (chatu). Pro začátek jsme vám připravili jednoduchý dialog, který můžete do služby importovat, než začnete vytvářet vlastní TJBotí chat.  [Stáhněte si dialog zde](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). V záložce "Catalog" vyhledejte službu _**Watson Assisstant**_ a klikněte na tlačítko "Create". Spustí se vám stránka s parametry služby. Kliknutím na tlačítko "Launch" se vám otevře nové okno s nástrojem pro vytváření chatu. Přepněte na záložku "Skills", vytvořte nový Skill importováním stáhnutého souboru. Na dlaždici vytvořeného Skillu si můžete zobrazit potřebné přihlašovací údaje (View API details).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)

Pro přístup ke službě Watson Assistant používáme API V1 a potřebujeme celkem 3 údaje: WORKSPACE ID, API KEY a URL.

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)

---

