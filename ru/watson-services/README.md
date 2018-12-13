# IBM Cloud: Watson Services
 
Чтобы оживить TJBot, необходимо, чтобы службы Watson services были доступны на IBM Cloud, а именно вы позволите TJBot следующие опции:

* Слушать - служба Speech to Text: переводит голосовые файлы в текст, который может быть обработан в дальнейшем.
* Разговаривать - служба Text to Speech: переводит текст в голосовые файлы, которые TJBot использует, чтобы говорить.
* Видеть - служба Visual Recognition: анализирует изображения, которые TJBot сфотографирует.
* Беседовать - служба Watson Assistant: создает диалоговую логику, которая позволяет достичь высокого качества диалога с TJBot.

Чтобы настроить эти службы, вам необходимо зарегистрироваться на IBM Cloud (регистрация бесплатная). Вы можете пользоваться выше приведенными службами в lite версии бесплатно. Каждая служба имеет свои учетные данные, которые необходимо ввести в TJBotCZ файл конфигурации (credentials.js).

Давайте создадим службы и запишем учетные данные.

## Регистрация на IBM Cloud

Вы можете зарегистрироваться на IBM Cloud по ссылке www.bluemix.net.

Регистрация бесплатная (без кредитной карты) и позволяет пользоваться необходимыми службами в LITE версии, этого достаточно для наших целей. Все услуги доступны через вкладку "Catalog".

## Служба Speech to Text

В "Catalog" найдите _**Speech to Text**_ и нажмите "Create". Откроется новая страница с параметрами службы. После нажатия на кнопку "Show" появятся учетные данные службы (имя пользователя и пароль). Вам необходимо ввести их в TJBotCZ файл конфигурации (credentials.js).

![S2T Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/s2t-credentials.png)
 
## Служба Text to Speech

В "Catalog" найдите _**Text to Speech**_ и нажмите "Create". Откроется новая страница с параметрами службы. После нажатия на кнопку "Show" появятся учетные данные службы (имя пользователя и пароль).
Вам необходимо ввести их в TJBotCZ файл конфигурации (credentials.js).

![T2S Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/t2s-credentials.png)
 
## Служба Visual Recognition

В "Catalog" найдите _**Visual Recognition**_ и нажмите "Create". Откроется новая страница с параметрами службы. После нажатия на кнопку "Show" появятся учетные данные службы. Вам необходимо ввести их в TJBotCZ файл конфигурации (credentials.js). В случае данного сервиса учетные данные представлены как API KEY.

![Visual Recognition API KEY](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/visual-recognition-credentials.png)

## Служба Watson Assistant

Watson Assistant - это инструмент для создания диалогов (чатов). Для быстрого старта мы подготовили для вас простой диалог, который вы можете импортировать в сервис, прежде чем вы начнете создавать свои собственные чаты. [Скачать диалог здесь](https://drive.google.com/open?id=1-H3Tm_Le7OZP0Uzuw1moKFghC54GRycN). В "Catalog" найдите _**Watson Assistantт**_ и нажмите "Create". Откроется новая страница с параметрами службы. При нажатии на кнопку "Launch" появится новое окно - инструмент для создания чатов. Выберите вкладку "Workspace", там вы найдете иконку для импорта скаченного ранее файла с диалогом (см. Рисунок ниже).

![WA Workspace](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-workspace.png)
 
После импорта диалога, откроется недавно созданное рабочее пространство. Иконка, похожая на улитку, укажет на учетные данные, необходимые для TJBot файла конфигурации (credentials.js). Учетные данные Watson Assistant представлены в виде id рабочего пространства, имени пользователя и пароля.

![WA Credentials](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/wa-credentials.png)


---




