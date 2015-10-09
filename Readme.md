# uLogin

Donate link: http://ulogin.ru  
Tags: ulogin, login, social, authorization  
Requires at least: 5.x.x
Tested up to: 5.4.11.10
Stable tag: 2.0  
License: GNU General Public License, version 2

**uLogin** — это инструмент, который позволяет пользователям получить единый доступ к различным Интернет-сервисам без необходимости повторной регистрации,
а владельцам сайтов — получить дополнительный приток пользователей из социальных сетей и популярных порталов (Google, Яндекс, Mail.ru, ВКонтакте, Facebook и др.)

## Установка
- Распакуйте архив модуля в корень сайта.
- Включите модуль в разделе **Настройки - Модули и БД"**.
- Добавьте панель авторизации в шаблон сайта, например, в файле themes/site_start.php добавьте:

		<!-- шаблонный тег вывода блока авторизации uLogin. modules/ulogin/views/ulogin.view.show_block_auth.php. -->
		<insert name="show_block_auth" module="ulogin">

- Добавьте панель синхронизации в шаблон сайта, например, в конец файла modules/usersettings/views/usersettings.view.form.php добавьте:

		<!-- Вывод шаблонного тега блока синхронизации uLogin. modules/ulogin/views/ulogin.view.show_block_sync.php. -->
		echo $this->htmleditor('<insert name="show_block_sync" module="ulogin">');

- Если панель авторизации/синхронизации не появилась, отчистите Кэш сайта в Админке "Параметры сайта - Режим разработки - Сбросить кэш".

Более детальную информацию смотрите на сайте https://ulogin.ru/help.php

## Модуль "uLogin"

Настройки данного модуля находится в Админке в разделе *"Контент - uLogin - Настройки модуля uLogin"*.

Здесь задаются: 
 
**uLogin ID форма входа:** общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);  
**uLogin ID форма синхронизации:** общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);
**Сохранять ссылку на профиль:** записывать в Базу Данных поле пользователя *Identity*;

## Настройки виджета uLogin

При установке расширения uLogin авторизация пользователей будет осуществляться с настройками по умолчанию.  
Для более детальной настройки виджетов uLogin Вы можете воспользоваться сервисом uLogin.  

Вы можете создать свой виджет uLogin и редактировать его самостоятельно:

- для создания виджета необходимо зайти в "Личный Кабинет" (ЛК) на сайте http://ulogin.ru/lk.php
- добавить свой сайт к списку "Мои сайты" и на вкладке "Виджеты" добавить новый виджет. После этого вы можете отредактировать свой виджет.

В графе "Возвращаемые поля профиля пользователя" вы можете включить необходимые поля, например, **Телефон** или **Аватарка**, Diafan CMS запишет эти параметры
в соответствующие поля Пользователя при регистрации.

**Важно!** Для успешной работы плагина необходимо включить в обязательных полях профиля поле **Еmail** в Личном кабинете uLogin.  
Заполнять поля в графе "Тип авторизации" не нужно, т.к. uLogin настроен на автоматическое заполнение данного параметра.

Созданный в Личном Кабинете виджет имеет параметры **uLogin ID**.  
Скопируйте значение **uLogin ID** вашего виджета в соответствующее поле в настройках плагина на вашем сайте и сохраните настройки.   

Если всё было сделано правильно, виджет изменится согласно вашим настройкам.

## Особенности

**Панель авторизации/регистрации отображается только для неавторизованных пользователей.**

**Панель синхронизации отображается только для авторизованных пользователей.**

Для вывода панели регистрации/авторизации в любом месте шаблона Diafan CMS используйте следующий код:

		<insert name="show_block_auth" module="ulogin">

Для вывода блока синхронизации используйте в любом месте шаблона Diafan CMS используйте следующий код:

		<insert name="show_block_sync" module="ulogin">

Для вывода панели регистрации/авторизации в любом месте модулей Diafan CMS используйте следующий код:

		echo $this->htmleditor('<insert name="show_block_auth" module="ulogin">');

Для вывода блока синхронизации используйте в любом месте модулей Diafan CMS используйте следующий код:

		echo $this->htmleditor('<insert name="show_block_sync" module="ulogin">');

## Изменения

####2.0.0.
* Релиз.
