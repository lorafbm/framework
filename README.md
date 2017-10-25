![School-PHP](https://raw.githubusercontent.com/schoolphp/library/master/Installer/install/skins/img/logo2.jpg)

School-PHP FrameWork: "Fox and Wolf"
===========================

## Установка 

0) Подготовка. Для начала нам потребуется `COMPOSER`. Если ранее через него уже была установка данного Frame Work, то необходимо очистить кэш. Для начала настроим PHPStorm в `settings` и `default settings`:
 - в разделе `Languages->PHP` указать PHP Language level: php 7 , CLI Interpreter: php 7
 - в разделе `Languages->PHP->Composer` указать PHP Interpreter: php 7.
 - в разделе `Tools->Command line tool support` или `ctrl+alt+s` и добавляем запись через `+` - `composer` с галочкой на `global` 

> **Примечание:** Если уже установлен, то повторно подключать не надо!

Теперь открываем `Tools->Run command...` или `ctrl+shift+x`. Где вводим команду по очистке кэша:
```bash
c clear-cache
```


1.а) Создайте новый проект в PHPStorm, выберите способ создания `COMPOSER` и установите пакет `schoolphp/framework`.
1.б) Как альтернативу можно запустить команду в `Tools->Run command...`:
```bash
c create-project schoolphp/framework C:/OpenServer/domains/newsite.ru/ 1.1.5
```
> **Примечание:** в данном случае мы указываем путь куда устанавливаем проект, а так же последним параметром указываем версию проекта. Последнюю версию можно увидеть тут:
https://github.com/schoolphp/framework/releases
Хочу заметить, что PHPStorm хранит кэш установок, поэтому через `FILE - NEW PROJECT` может находиться не самая свежая версия. Поэтому данный способ можно считать самым эффективным.

1.в) Альтернативная установка через git: запускаем команды через `Terminal` в PHPStorm, быстрый доступ находится слева внизу:
```bash
git init
git pull https://github.com/schoolphp/framework
```

2) Подключаем `bower`. Открываем конфиг `ctrl+alt+s`: 
```bash
Languages & Frameworks -> JavaScript -> Bower
```
выбираем bower.json из проекта. Устанавливаем все пакеты `bower`, для этого открываем `Terminal` и вводим команду:
```bash
bower install
```

3) Устанавливаем все пакеты `composer` - `Tools -> Run Command` и вводим команду:
```bash
c install
```


## Настройка
1) Необходимо настроить `MySQL` , а именно `Создать новую Базу Данных` и `Нового пользователя`.

2) Запустить `install.php`, ввести данные.

3) Запускаем `Проект`

## Важные особенности
Не стоит бояться файла `install.php`, так как установки не будет, если она уже была выполнена ранее!

## Обновление проекта
- Обновление библиотек bower: открываем `Terminal` и вводим команду: `bower update`;
- Обновление библиотек composer: открываем `Tools -> Run Command` и вводим команды:
```bash
c clear-cache
c update
```
- Обновление ядра проекта: открываем `Terminal` и запустите git команду:
```bash
git pull https://github.com/schoolphp/framework
```
> **Примечания:** Если просят удалить файлы, то были нарушены принципы Фреймворка, так как нельзя лезть в файлы ядра!

## Дополнительно:
Сократить `git pull` можно, если заранее указать указать репозиторий:
```bash
git config remote.origin.url https://github.com/schoolphp/framework
```

И дальше обновлять просто командой `git pull`.