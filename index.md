# simple-discord-bot
Простой Discord бот для вашего сервера 

[![Discord](https://discordapp.com/api/guilds/662635194884292611/widget.png)](https://discord.gg/GG9Dkhg)

# Библиотеки
Библиотека для взаимодействия с Discord API - [`discore.js`](https://github.com/zargovv/discore.js) (Based on [DiscordJS](https://github.com/discordjs/discord.js) **v12**)
Библиотека для взаимодействия с MongoDB - [`mongoose`](https://npmjs.com/package/mongoose)

# Как запустить бота? 
Для начала, установите все необходимые библиотеки: ``npm install`` <br>
Затем укажите токены, ссылку для взаимодействия с БД, и ваш ID в файле ``.env`` (пример в [``example.env``](./example.env)) <br>


# Запуск бота
### Примечание.
Для корректной работы бота необходимо включить [**Privileged Gateway Intents**](https://support.discord.com/hc/en-us/articles/360040720412-Bot-Verification-and-Data-Whitelisting#privileged-intent-whitelisting)(кликабельно)
Их необходимо активировать на странице бота, иначе команды будут функционировать неправильно.
![](https://imgs.mrlivixx.me/372250211201543.gif)
## Запуск на VDS/VPS сервере.
* Для запуска бота используйте ``npm start``

* Для запуска через **pm2**:

+ Добавление и запуск: ``pm2 start bot.js --name simple-bot``
+ Просто запуск: ``pm2 start simple-bot``
+ Перезагрузка: ``pm2 restart/reload simple-bot``
+ Остановка работы: ``pm2 stop simple-bot``
+ Удаление бота (из pm2): ``pm2 delete simple-bot``
+ Автозапуск при старте системы: ``pm2 save && pm2 startup``

P.S. Если вы запускаете команду автозапуска не из root-пользователя, убедитесь что у вас есть права на sudo
<br>Либо обратитесь к администратору системы для прописания команды, которую вам даст pm2

## Запуск бота на [heroku](https://heroku.com)

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/sqdsh/simple-discord-bot/tree/master)

**Вы прекрасны!**

# Как сменить стандартный префикс? Для этого вам нужно нажать [сюда](https://github.com/sqdshcom/simple-discord-bot/blob/ece80bbff12119c911a5f07a32e8a11ad0b3b3f8/src/bot.js#L31) и заменить его на свой :3


# Прочее
Темпвойсы были взяты [отсюда](https://github.com/bemovpro/Create-temporary-voice-channel)<br>
Бот имеет недоработки и баги, если Вы нашли один, то открывайте [Issues](https://github.com/sqdshcom/simple-discord-bot/issues)<br>
Если знаете, как пофиксить, то Вам прямиком в [Pull Requests](https://github.com/sqdshcom/simple-discord-bot/pulls)<br>
Будем рады любой помощи! <br>

<br> 
<br>
# Создание кластера для базы данных

Для начала заходим на сайт https://mongodb.com и [Регистрируемся](https://account.mongodb.com/account/register) или [Входим](https://account.mongodb.com/account/login) в аккаунт.

После регистрации, вас перекинет на другую страничку. Вам необходимо нажать на зеленую кнопку, после в открывщимся окне написать название вашего проекта. Нажимаем на зеленую кнопку. 

![](https://imgs.mrlivixx.me/opera_cuCMXaULuj.png)

Затем нам нужно создать кластер, для этого жмём на кнопку **Build a Cluster** и затем **Create cluster** Если хотите вы можете изменить название кластера. И ждём 1-5 минут.

Теперь нам нужно открыть раздел **Database Access**
![](https://imgs.mrlivixx.me/opera_VFvHs0sXGW.png)

После перехода в данную вкладку, мы видем зеленую кнопку, с надписью **ADD NEW USER**, в открывшимся окне выставляем права "Atlas Admin". После пишите ваше имя и желаемый пароль(стоит понимать что, через эти данные вы будете входить в базу-данных. Так что запишите ваш пароль на листок или блокнот.) Сохраняем 
![](https://camo.githubusercontent.com/680a7a724d1b993eaa7301ecdb4ef4a5e04775c9/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f3636373037323132333931343831333434342f3638363335333632373332303638303436372f494d475f32303230303330395f3034303432342e706e67)

Потом идём во вкладку **Network Access**
![](https://imgs.mrlivixx.me/opera_PGfdBZDfX8.png)

Нажиманием на клопку **ADD IP ADDRESS** 
![](https://imgs.mrlivixx.me/opera_IuLkQePeI6.png)

И кликаем на **ALLOW ACCESS FROM ANYWHERE** 
![](https://imgs.mrlivixx.me/opera_1abHsyXZxs.png)

[🎉] Поздравляю! Мы создали базу, теперь нам необходима ссылка чтоб подключиться к базе. Для этого опять идем во вкладку Clusters.

![](https://imgs.mrlivixx.me/opera_DtKoVpedMu.png)

И жмём на кнопку **CONNECT**
Дальше в появившемся окне жмём на **Connect your application** 
![](https://imgs.mrlivixx.me/opera_yGeu800yF4.png)
Затем получаем ссылку на нашу базу данных, вместо <password> укажите пароль от пользователя и вместо <dbname> название базы которая будет юзать бота
![](https://imgs.mrlivixx.me/opera_96XC9195k5.png)