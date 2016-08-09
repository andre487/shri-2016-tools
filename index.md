---

layout: default

---

# &nbsp;

<img src="pictures/hand.png" height="100%">

## **{{ site.presentation.title }}** {#cover}

<div class="info">
	<p class="author">{{ site.author.name }}</p>
</div>

## Инструменты

<center>
  <img src="pictures/workbench.jpg" height="450">
</center>

## Джентльменский набор

  * Удобный редактор или IDE, тысячи их
  * VCS: Git, Mercurial, <s>svn</s>
  * Терминал
  * Статический анализ:
    * JavaScript: ESLint, JSHint, JSCS
    * CSS: stylelint, CSSComb
  * Инструменты разработчика в браузерах
  * Инструменты для работы с графикой

## Мобильная специфика

Всё как 10 лет назад:

  * Плохие сети
  * Cлабое железо
  * Нет удобств для разработчика

## Повестка дня

  * Как разрабатывать без мобильного?
  * Как пробросить проект в устройство?
  * Как пробраться в мобильный браузер?
  * Что, если нужно устройство, но его не найти?

## &nbsp;
{:.section}

### Как разрабатывать без мобильного?

## Chromium
{:.screen-shot}

<center>
  <img src="pictures/chrome.png" height="530">
</center>

## Chromium
{:.screen-shot}

<center>
  <img src="pictures/chrome-emulation.png" height="530">
</center>

## MS Edge
{:.screen-shot}

<center>
  <img src="pictures/edge.png" height="500">
</center>

## Firefox
{:.screen-shot}

<center>
  <img src="pictures/firefox.png" height="570">
</center>

## &nbsp;
{:.section}

### Как пробросить проект в устройство?

## Варианты

  * Открыть напрямую: `http://192.168.1.100`
  * Туннелирование:
    * localtunnel
    * ngrok
    * SSH туннель

## Открыть напрямую

<img src="pictures/network-diagram.png">

## Туннелирование

<img src="pictures/tunnel-diagram.png">



## localtunnel

[github.com/localtunnel/localtunnel](https://github.com/localtunnel/localtunnel)

&nbsp;
&nbsp;

  * `npm install localtunnel`
  * `lt --port 8487`
  * Получаем URL в Интернете: `http://ipnhrxfvkt.localtunnel.me`


## ngrok

[ngrok.com](https://ngrok.com/)


&nbsp;
&nbsp;

  * Скачать, распаковать
  * `ngrok http 8487`
  * Получаем URL в Интернете:
    * `http://a3c04d5b.ngrok.io`
    * `https://a3c04d5b.ngrok.io`

## SSH туннель

На UNIX-like системах присутствует по умолчанию

  * `ssh -N -R 8487:localhost:8487 my-server.me`
  * Открываем `my-server.me:8487`

В Windows можно воспользоваться PuTTY

## &nbsp;
{:.section}

### Как пробраться в мобильный браузер?

## Как пробраться в мобильный браузер?
{:.section}

### Отладка по USB

## Отладка по USB

![](pictures/android-usb-connection.jpg){:.right-image}

  * Chromium
  * Safari
  * Firefox

## Chromium
{:.screen-shot}

<center>
  <img src="pictures/chromium-debug.png" height="570">
</center>

## Safari
{:.screen-shot}

<center>
  <img src="pictures/safari-debug.png" height="570">
</center>

## Минусы

Хорошо и везде работает отладка Android 4.4+ в Chromium

Хорошо на macOS работает отладка iOS 6+ в Safari

А другие сочетания?

...Неплохо работает отладка Firefox, но это нечасто нужно

## ios-webkit-debug-proxy

Позволяет отлаживать iOS в Chromium

&nbsp;
&nbsp;

Проект:

  * <span style="color: #666">MaxOS, Linux:</span> [ios-webkit-debug-proxy](https://github.com/google/ios-webkit-debug-proxy)
  * <span style="color: #666">Windows:</span> [ios-webkit-debug-proxy-win32](https://github.com/artygus/ios-webkit-debug-proxy-win32)

## Как пробраться в мобильный браузер?
{:.section}

### Встраиваемые отладчики

## Встраиваемые отладчики

  * Vorlon.JS
  * weinre
  * Firebug light

## Vorlon.JS

[github.com/MicrosoftDX/Vorlonjs](https://github.com/MicrosoftDX/Vorlonjs)

&nbsp;
&nbsp;

Установить, запустить:

~~~
$ npm install vorlon
$ vorlon
~~~

Подключить к странице:

~~~
<script src="http://localhost:1337/vorlon.js"></script>
~~~

## Vorlon.JS с туннелем

~~~
$ lt --port 1337
~~~

~~~
http://quahpivgsm.localtunnel.me/vorlon.js
~~~

## Vorlon.JS
{:.screen-shot}

<center>
  <img src="pictures/vorlon.png" height="570">
</center>

## Vorlon.JS

Интересные фичи:

  * DOM Explorer
  * Network Monitoring
  * Resource Explorer
  * My Device
  * Плагины

## Vorlon.JS
{:.screen-shot}

<center>
  <img src="pictures/vorlon-dom-explorer.png" height="520">
</center>

## Vorlon.JS
{:.screen-shot}

<center>
  <img src="pictures/vorlon-net.png" width="900">
</center>

## Vorlon.JS
{:.screen-shot}

<center>
  <img src="pictures/vorlon-resources.png" width="900">
</center>

## Vorlon.JS
{:.screen-shot}

<center>
  <img src="pictures/vorlon-device-info.png" width="900">
</center>

## Vorlon.JS

Расширяем: [www.vorlonjs.io/plugins](http://www.vorlonjs.io/plugins/)

## Vorlon.JS
{:.screen-shot}

<center>
  <img src="pictures/vorlon-plugins.png" width="900">
</center>

## weinre

[people.apache.org/~pmuellr/weinre](http://people.apache.org/~pmuellr/weinre)

&nbsp;
&nbsp;

~~~
$ npm install weinre
$ weinre
$ lt --port 8080
~~~

~~~
<script
src="http://lthost/target/target-script-min.js#anonymous">
</script>
~~~

## weinre
{:.screen-shot}

<center>
  <img src="pictures/weinre.png" height="570">
</center>

## Firebug light

[getfirebug.com/firebuglite](http://getfirebug.com/firebuglite)

&nbsp;
&nbsp;

~~~
<script
src="https://getfirebug.com/firebug-lite.js#startOpened">
</script>
~~~

## Firebug light
{:.screen-shot}

<center>
  <img src="pictures/firebug-light.png" height="510">
</center>

## &nbsp;
{:.section}

### Что, если нужно устройство, но его не найти?

## Эмуляторы

<table style="text-align: center">
  <tr style="padding: 10px !important">
    <td>Android</td>
    <td>iOS</td>
    <td>Windows Phone</td>
  </tr>
  <tr style="padding: 10px !important">
    <td style="vertical-align: middle"><img src="pictures/android-studio.png" width="190"></td>
    <td style="vertical-align: middle"><img src="pictures/xcode.jpg" width="120"></td>
    <td style="vertical-align: middle"><img src="pictures/windows-phone-logo.png" width="105"></td>
  </tr>
  <tr style="padding: 10px !important">
    <td>Android Studio</td>
    <td>XCode</td>
    <td>Windows Phone emulator</td>
  </tr>
</table>

## BrowserStack

[browserstack.com](https://www.browserstack.com)

&nbsp;
&nbsp;

Тестирование в реальных браузерах

&nbsp;
&nbsp;

<img src="pictures/browserstack-form.png" height="300">

## BrowserStack
{:.screen-shot}

<img src="pictures/browserstack.png" height="570">

## Smartphone Test Farm

[github.com/openstf/stf](https://github.com/openstf/stf)

&nbsp;
&nbsp;

Удалённое тестирование в устройствах

«Свой BrowserStack»

## Smartphone Test Farm
{:.screen-shot}

<center>
  <img src="pictures/stf.gif" height="530">
</center>

## &nbsp;
{:.section}

### Заключение

## Проблемы и решения

<table>
  <tr>
    <td>Как разрабатывать без мобильного?</td>
    <td>Инструменты браузеров</td>
  </tr>
  <tr>
    <td>Как пробросить проект в устройство?</td>
    <td>localtunnel, ngrok, SSH</td>
  </tr>
  <tr>
    <td>Как пробраться в мобильный браузер?</td>
    <td>USB-отладка, Vorlon.JS, Firebug light</td>
  </tr>
  <tr>
    <td>Что, если нужно устройство, но его не найти?</td>
    <td>Эмуляторы, BrowserStack</td>
  </tr>
</table>

## &nbsp;
{:.section}

### Спасибо за внимание!
