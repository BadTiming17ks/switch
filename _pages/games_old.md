---
permalink: /games_old.html
title: Установка игр, DLC, обновлений по USB с помощью DBIv49 и NS USB Loader
author_profile: true
---
{% include toc title="Разделы" %}

{% spoiler Видеоинструкция %}

{% include youtube.html id="0OMXAYJcTS0" %}
{: .text-center}
{: .notice--info}

{% endspoiler %}

## Важная информация

Эта инструкция для тех, кто по каким-либо причинам не смог совладать с DBI backend и DBIv60 и выше. Установка через DBI backend и DBIv60 и выше, которая описана в [основной инструкции](games){:target="_blank"} является рекомендуемой. 

### Что понадобится

* Настроенная и работающая [кастомная прошивка](cfw){:target="_blank"}
* Умение [запускать пейлоады через Fusée Gelée](fusee-gelee){:target="_blank"}
* Свежая версия [прошивки приставки](update-to-latest){:target="_blank"}
* Установленный [DBIv49](files/DBI_old.zip){:target="_blank"}
   - **ВНИМАНИЕ!** Описанный метод работает **только** с DBIv49! Более свежие версии программы не совместимы с NS USB Loader!

### Подготовительные работы (выполняются едино-разово)
{% spoiler Установка драйвера (только Windows) %}

Необходимо сделать только раз для корректной работы установки по USB 
{: .notice--warning}

Пользователи mac и linux пропускают установку драйверов
{: .notice--warning}

* Свежая версия [`Zadig.exe`](https://zadig.akeo.ie/){:target="_blank"}
Эти драйвера отличаются от тех, что используются для передачи пейлоада на switch! Если вы ни разу не устанавливали игры этим методом, ставить драйвера нужно обязательно!

1. Выполните [подготовительные работы](games#подготовительные-работы){:target="_blank"}, если ещё не сделали этого
1. Подключите switch к ПК по USB 
1. На ПК запустите [`Zadig.exe`](https://zadig.akeo.ie/){:target="_blank"} от имени Администратора 
   * Если программа не видит Switch, [запустите на консоли DBI](hbl){:target="_blank"} и попробуйте еще раз 
1. В верхнем поле (на изображении '1') вы должны увидеть строку "**libnx USB comms**" или "**Nintendo Switch**"
   * Если вместо "**libnx USB comms**" или "**Nintendo Switch**" вы видите "**Unknown Device**", подключите switch в другой USB и перезапустите ПК, после чего вернитесь к установке драйвера 
   * Если там ничего нет, пробуйте подключиться в другой USB-порт, перезагрузить ПК, сменить кабель

   ![](/images/screenshots/zadig_old.png) 
   {: .text-center}
   {: .notice--info}
   
1. В поле "**Driver**" (на изображении '2') выберите `libusbK (v3.0.7.0)`
1. Нажмите "**Install Driver**" ('3')
1. После успешной установки драйвера нажмите "**Close**" и закройте программу 

{% endspoiler %}


{% spoiler Настройка ПО %}

1. Скачайте программу [ns-usbloader](https://github.com/developersu/ns-usbloader/releases/latest){:target="_blank"} и поместите её в удобную папку 
1. Скачайте и установите [JRE](https://java.com/ru/download/){:target="_blank"} для вашей ОС
1. Запустите [`ns-usbloader.jar`](https://github.com/developersu/ns-usbloader/releases/latest){:target="_blank"}
1. В главном окне программы выберите **Tinfoil** и **USB**
    
    ![]({{ basecolo_path }}/images/screenshots/nsu.png) 
    {: .text-center}
    {: .notice--info}

1. Перейдите в настройки программы и установите галочку напротив пункта "**Разрешить выбирать XCI файлы для TinFoil**" 

    ![]({{ base_path }}/images/screenshots/nsu_setup.png) 
    {: .text-center}
    {: .notice--info}
        
{% endspoiler %}

### Установка игр 

1. На приставке запустите **DBI** через [Homebrew Launcher](hbl){:target="_blank"}
1. Подключите консоль к ПК 
1. Выберите пункт "**Install title from USB**"
1. Запустите [`ns-usbloader.jar`](https://github.com/developersu/ns-usbloader/releases/latest){:target="_blank"}
	* Убедитесь, что в программе выбран **Tinfoil** и **USB**
    * Убедитесь, в настройках программы установлена галочка напротив пункта "**Разрешить выбирать XCI файлы для TinFoil**"
1. Нажмите "**Выбрать .NSP файлы**" и выберите необходимые для установки `.nsp`, `.nsz` или `.xci`
	* Для выбора нескольких игр, удерживайте клавишу (Ctrl)
1. Нажмите "**Отправить в NS**"
1. На приставке с помощью клавиши (X) выберите необходимые игры
	* Нажмите (Y), если нужно выбрать все или инвертировать выбор
1. Нажмите (A), чтобы начать установку
1. Выберите необходимые опции в "**Install options**"
	* **Install target** - место установки. NAND или Sdcard соответствуют внутренней памяти и карте памяти
	* **Ignore version** - указывает на то будет ли игнорироваться параметр версии, прописанный в данных игры при установке. То есть, если игра говорит, что ей нужна прошивка 7.0, а у вас 6.2, то включение этой опции рзрешит установить такую игру 
		* **Не будет работать, если игра подписана ключем версии выше, чем ваша! [Обновитесь](update-to-latest){:target="_blank"} на прошивку {% include /vars/sys_version.txt %}, чтобы не задумываться об этом**
		* Рекомендуемое значение **Yes**
1. Выберите **Start install** для начала установки
1. Нажмите (B) для выхода из установщика в папку 
1. Нажмите (+) для закрытия программы

___

[Закрыть страницу](javascript:window.close();)
{: .notice--success}