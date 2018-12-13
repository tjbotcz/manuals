# Оживление TJBot (с помощью Raspberry Pi)

 
Выберите ваш способ... 
1. [Быстрый старт с подготовленного изображения](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#faststart-from-ready-made-image)
2. [Начать с нуля как профессионал](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#start-from-scratch-like-a-pro)
3. Некоторые практические советы

	* [Как скопировать файлы с Windows на Raspberry Pi используя командную строку](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-windows-to-raspberry-pi-using-a-command-line)
	* [Как скопировать файлы с Mac OS на Raspberry Pi используя командную строку](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-mac-os-to-raspberry-pi-using-a-command-line-in-mac-os)
	* [Как скопировать файлы с Rasberry Pi на Mac OS используя командную строку (в Mac Os)](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-copy-files-from-rasberry-pi-to-mac-os-using-command-line-v-mac-os)
	* [Как настроить IP адрес для Raspberry Pi](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-set-up-a-raspberry-pis-ip-address)
	* [Как менять громкость на Raspberry Pi используя командную строку](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#how-to-change-raspberry-pis-volume-using-the-command-line)
	* [Настройка аудиовыхода на джек](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#setting-audio-output-to-jack)
	* [Как освободить больше места на microSD карте](https://github.com/tjbotcz/manuals/tree/master/en/bring-to-life#get-more-free-space-on-microsd-card)

## Быстрый старт с подготовленного изображения

Вы, конечно, уже не можете ждать и хотите скорее оживить TJBot. Поэтому мы подготовили готовое изображение, где мы предварительно настроили Raspbian для запуска TJBotCZ.

Вам необходимо:

* интернет соединение, чтобы скачать Raspbian ОС и ОП для установки изображения на карту
* компьютер со слотом для SD/microSD карт или со считывателем SD/microSD карт 
* USB  клавиатура, USB мышь
* ЖК-дисплей с HDMI портом или HDMI кабелем.

Шаги:
1. Скачать подготовленное изображение [image of TJBotCZ](https://drive.google.com/open?id=1d_CRvtKdND36NPi7GKzZatBY5vo-nD4V) и распаковать его.

2. Скачать и установить ПО для установки образа Raspbianu на microSD карту, например, Etcher: https://etcher.io/. Используйте его, чтобы установить скаченный образ на microSD карту (выберете tjbotcz_lite.img файл, выберете вставленную карту, и ... готово!)

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Вставьте предустановленную microSD карту в Raspberry-Pi, соедините его с HDMI монитором, клавиатурой, мышью или с RJ-45 (ethernet) кабелем. Второй вариант - подключить его через WiFi (если вы используете WiFi, вам необходимо настроить соединение при помощи ГИП ОС Raspberry Pi, Raspberry Pi запомнит настройки и будет использовать их в дальнейшем). Вам понадобится интернет соединение на шаге 4.

4. На рабочем столе Raspbian  мы подготовили скрипт "run-me-first.sh". Запустите его (двойное нажатие и он запустится в терминале). Скрипт скачает из интернета последнюю версию программы [TJBotCZ_lite program](https://github.com/tjbotcz/tjbotcz_lite) и установит необходимые зависимые элементы.

5. Для того, чтобы общаться с TJBot необходимо подключить следующие службы на IBM Cloud:

* Watson Assistant (служба для создания диалогов/чатов)
* Speech to Text (служба для перевода голосовых файлов в текстовые)
* Text to Speech (служба для синтезирование текста в голос)
* Visual Recognition (служба для анализа изображений)

 Инструкции по подключению сервисов можно найти в руководстве пользователя ["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

6. Если вы подключили все необходимые службы, добро пожаловать обратно и давайте продолжим. Вам необходимо ввести учетные данные отдельных служб в файл конфигурации (credentials.js). Поскольку учетные данные довольно длинные, лучший способ ввести их - это удаленно подключиться к TJBot с компьютера, на котором были созданы службы Watson, и скопировать-вставить их. Если вы пользователь Mac, воспользуйтесь Терминалом, в случае Windows, используйте [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy -программа для удаленного доступа, вам необходимо установить её в первую очередь. Используйте Терминал или PuTTy, чтобы подсоединиться к TJBot (вам необходимо находится в той же сети, что и TJBot ):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (введите IP адрес TJBot в выделенное поле):

 ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)

  Вас попросят ввести пароль. Пароль по умолчанию: **_raspberry_**.
 
7. В Терминале (или в командной строке в Windows) перейдите в папку с файлом конфигурации TJBot:

  ```
  cd Desktop/tjbotcz_lite/configuration
  
  ```
8. Создайте копии credentials.default.js и config.default.js файлов и назовите их credentials.js и config.js соответственно. Вы можете сделать это также удаленно через Терминал/CMD окно:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
9. Вставьте учетные данные отдельных служб в текстовый редактор "nano". 
  ```
  nano credentials.js
  
  ```
 На изображении ниже обозначены места, которые необходимо заполнить учетными данными служб Watson (не удаляйте кавычки).

  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
 Сохраните и закройте файл:  CTRL+X, Y, Enter.

10. А теперь давайте оживим TJBot !!! вернемся к папке Desktop/tjbotcz_lite ... и мы там, где надо.
 TJBot сконфигурирован говорить мужским голосом и реагирует на имя Михаэль. Это означает, что он будет распознавать предложения, которые содержат имя Михаэль. Для получения дополнительной информации о программе TJBotCZ lite и о том, что с ней делать, перейдите в [repository] (https://github.com/tjbotcz/tjbotcz_lite).

  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```

![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)
 
---

## Начните с нуля, как профессионал

Raspberry-Pi использует Raspbian как операционную систему, которая построена на Debian Linux.
Вся Raspbian находится на карте microSD. Таким образом, сначала необходимо установить OС Raspbian на карту microSD. 
Нам понадобится:

* интернет соединение, чтобы скачать Raspbian ОС и ОП для установки образа на карту
* компьютер со слотом для SD/microSD карт или со считывателем SD/microSD карт 
* USB клавиатура, USB мышь
* ЖК-дисплей с HDMI портом или HDMI кабелем.

Шаги:
1. Скачать Raspbian ОС (https://www.raspberrypi.org/downloads/).

![Raspbian download](https://github.com/tjbotcz/manuals/blob/master/images/raspbian-download.png "Raspbian download")

2. Скачать и установить ПО для установки образ Raspbian, например, Etcher https://etcher.io/, затем установите ОС  Raspbian  на microSD карту (нажмите/выберете скаченный .img файл, а затем уже подсоединенную SD карту, и ...готово! )

![Etcher](https://github.com/tjbotcz/manuals/blob/master/images/etcher-flashing.png "Etcher flashing")

3. Вставьте предустановленную microSD карту в Raspberry-Pi, соедините его с HDMI монитором, клавиатурой, мышью или с RJ-45 (ethernet) кабелем. Второй вариант - подключить его через WiFi (если вы используете WiFi, вам необходимо настроить соединение при помощи ГИП ОС Raspberry Pi, Raspberry Pi запомнит настройки и будет использовать их в дальнейшем). Вам понадобится интернет соединение на шаге 5.
 
4. Установите подключение Raspberry-Pi SSH, это позволит работать с  Raspberry-Pi удаленно через терминал или PuTTY (Windows). В Терминал введите:

```
sudo raspi-config
```
Откроется меню.
Выберете “Interfacing Options”.
Выберете “SSH” и включите его.
5. Откройте Терминал и запустите:
```
curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh -
```
Эта команда скачает скрипт с сервера, который запустит
интерактивное руководство в окне терминала. С помощью этого руководства вы сможете сконфигурировать Raspberry Pi для TJBot:

* не меняйте имя TJBot  (оставьте raspberrypi)  - (Enter)
* IPv6 (выключить) - (Y)
* Google DNS (включить) - (Y)
* локальные настройки (язык) (Y)
* обновить ОС Raspbianu (Y)
* обновить до более новой версии Node.js (N)
* подключение камеры (Y)
* скачать оригинальную программу TJBot и тестовые сценарии (Enter)
* настроить аудио выход (оставьте порт для джек-аудио включенным) (N)
* перезагрузить (Y)

6. Установите node.js версии 9:
```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```
7. В Терминале откройте папку Desktop:
```
cd Desktop
```
8. Установите одну из TJBotCZ программ (tjbotcz_lite, tjbotcz, tjbotcz_iot):
```
git clone https://github.com/tjbotcz/<name of tjbotcz program>.git
```
9. Откройте в Терминале только что созданную папку “tjbotcz_lite”, "tjbotcz" or tjbotcz_iot":
```
cd <имя папки>
```
10. Скачайте зависимые программы, определенные в файле package.json, который находится в папке с программами, скаченными на шаге 8:
```
npm install
```
11. Чтобы иметь возможность разговаривать с TJBot, вам понадобятся следующие службы подготовленные на IBM Cloud:

* Watson Assistant (служба для создания диалогов/чатов)
* Speech to Text (служба для перевода голосовых файлов в текстовые)
* Text to Speech (служба для синтезирование текста в голос)
* Visual Recognition (служба для анализа изображений)

  Активировать службы можно при помощи руководства в папке["watson-services"](https://github.com/tjbotcz/manuals/blob/master/en/watson-services/README.md).

12. Если вы подключили все необходимые службы, добро пожаловать обратно и давайте продолжим. Вам необходимо ввести учетные данные отдельных служб в файл конфигурации (credentials.js). Поскольку учетные данные довольно длинные, лучший способ ввести их - это удаленно подключиться к TJBot с компьютера, на котором были созданы службы Watson, и скопировать-вставить их. Если вы пользователь Mac, воспользуйтесь Терминалом, в случае Windows, используйте [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). PuTTy -программа для удаленного доступа, вам необходимо установить её в первую очередь. Используйте Терминал или PuTTy, чтобы подсоединится к TJBot (вам необходимо находится в той же сети, что и TJBot ):

  MacOS:
  ```
  ssh pi@<ipadresa>
  ```
  Windows (введите IP адрес TJBot в выделенное поле):

 ![PuTTy](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/putty.png)

   Вас попросят ввести пароль. Пароль по умолчанию: **_raspberry_**.

13. В Терминале (или в командной стрике в Windows) перейдите в папку с файлами конфигурационнии:

  ```
  cd Desktop/tjbotcz_lite/configuration
  ```
14.  Создайте копии credentials.default.js и config.default.js файлов и назовите их credentials.js и config.js соответственно. Вы можете сделать это также удаленно через Терминал/CMD окно:
  ```  
  cp config.default.js config.js
  cp credentials.default.js credentials.js
  ```
15. Вставьте учетные данные отдельных служб в текстовый редактор "nano". 
  ```
  nano credentials.js
  ```
 На изображении ниже обозначены места, которые необходимо заполнить учетными данными служб Watson (не удаляйте кавычки).
  ![credentials.js soubor](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/credentials.png)
  Сохраните и закройте файл:  CTRL+X, Y, Enter.
  
16.  А теперь давайте оживим TJBot !!! вернемся к папке Desktop/tjbotcz_lite ... и мы там, где надо.
 TJBot сконфигурирован говорить мужским голосом и реагирует на имя Михаэль. Это означает, что он будет распознавать предложения, которые содержат имя Михаэль. 

  ```
  cd ..
  sudo node tjbotcz_lite.js
  ```
  
![tjbot-waving](https://raw.githubusercontent.com/tjbotcz/manuals/master/images/tjbot_wave.gif)

---

## Некоторые практические советы, которые могут пригодиться

### Как копировать файлы с Windows на Raspberry Pi при помощи командной строки

Откройте командную строку и адрес, где находится файл, который вы хотите скопировать (cd = change directory). Затем используйте следующую командную строку, но прежде выясните, если PuTTY уже установлен и проверьте, если C:\Program Files\PuTTY\pscp.exe. работает. Файл «file.txt» - имя для копируемых файлов, таким образом измените «your_pi» на IP-адрес вашего Raspberry Pi (это должно быть сделано в той же сети):


```
"C:\Program Files\PuTTY\pscp.exe" file.txt pi@your_pi:Desktop/tjbotcz_lite
```


### Как скопировать файлы с Mac ОС на Raspberry Pi используя командную строку (на Mac ОС)

Откройте командную строку и адрес, где находится файл, которий вы хотите скопировать  (cd = change directory). Затем используйте  следующую  командную строку, где «file.txt» - имя для копируемых файлов, таким образом измените «your_pi» на IP-адрес вашего Raspberry Pi (это должно быть сделано в той же сети):

```
scp file.txt pi@your_pi:~/Desktop/tjbotcz_lite
```

### Как скопировать файлы с Rasberry Pi на Mac OS используя командную строку (на Mac ОС)

Если вы подключены к TJBot через SSH, сначала выполните выход:

```
logout
```

В Терминале Mac ОС используйте команду для копирования файлов:

```
scp <имя пользователя Raspberry Pi>@<ip адрес Raspberry Pi>:/<целый путь к файлу на Raspberry pi> <целый путь к директории, где файлы будут храниться на Mac OS>
```

Пример:

```
scp pi@192.168.1.10:/home/pi/Desktop/tjbotcz_lite/config.js Users/Honza/Desktop
```

Вас попросят ввести пароль от Raspberry Pi.


### Как настроить IP адрес Raspberry Pi

Подключите Raspberry Pi через SSH или PuTTy. Затем используйте команду:

```
sudo nano /etc/dhcpcd.conf
```

В открывшемся файле раскомментируйте часть с настройками статического адреса и введите верные значения (IP-адрес, IP-адрес маршрутизатора).


### Как изменить громкость Raspberry Pi с помощью командной строки

Подключитесь через SSH или PuTTY к Raspberry Pi. Следующая строка кода изменит громкость на 90%. Громкость должна изменяться нелинейным образом, поэтому разница между 90% и 95% примечательна.

```
amixer  sset PCM,0 90%
```

Еще один способ - создать сокращение, с помощью которого можно менять громкость. В редакторе "nano" откройте .bashrc файл:

```
nano ~/.bashrc
```

и в конце файла добавьте 

```
# Увеличить громкость на 5%
alias volup='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')+5]%'
# Уменьшить громкость на 5%
alias voldown='sudo amixer set PCM -- $[$(amixer get PCM|grep -o [0-9]*%|sed 's/%//')-5]%'
```
Перезагрузите Raspberry-Pi. После этого вы просто можете написать `volup`  или  `voldown` в Терминале, и громкость изменится на 5%.


### Настройка аудио выхода на джек

Иногда вы не можете услышать TJBot, даже если уровень громкости установлен на максимум. Скорее всего, звук идет на HDMI, а не на подключенный динамик (через джек). Для установки выхода на разъем джек сделайте следующее:

```
sudo amixer cset numid=3 1
```

Последнее число определяет выход (0=auto, 1=jack, 2=HDMI)


### Освободить больше места на microSD карте

Если у вас есть 16 ГБ microSD карта, все в порядке. Однако, если карта на 8 ГБ, то после установки у вас останется около 2 ГБ. Вы можете удалить Wolfram и LibreOffice, чтобы освободить место. Так как ни одна из этих программ не пригодится вам для работы с TJBot, более того вы освободите 1GB памяти дополнительно.
Чтобы удалить программы:

```
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get autoremove
```

---
