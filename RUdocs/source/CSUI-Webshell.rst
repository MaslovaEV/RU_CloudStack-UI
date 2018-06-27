.. _WebShell:

Плагин WebShell
=================

Общая информация
---------------------


Инструкции по установке
--------------------------

Для запуска плагина `WebShell <https://github.com/bwsw/webshell>`_ CloudStack-UI необходимо:

1. Запустить контейнер WebShell на backend'е.

2. Подключить и настроить плагин WebShell в ``config.json``.


Запуск WebShell Backend
-------------------------------
Пожалуйста, изучите `раздел <https://github.com/bwsw/webshell#usage>`_ в репозитории  `WebShell <https://github.com/bwsw/webshell>`_.

Настройка WebShell
------------------------------

Включите ``webShell`` в блоке ``extentions`` в файле конфигураций ``config.json``:

::

  "extensions": {
   ...,
   "webShell": true
  }

``webShell.address``  - адрес backend'a WebShell, необходим для доступа к WebShell.


Запуск ``cloudstack-ui`` c WebShell из контейнера 
----------------------------------------------------

::

docker run -d -p 80:80 --name cloudstack-ui \
           ...
           -e WEBSHELL_PLUGIN_ENDPOINT=http://url/to/webshell-server \
           ...
           -v /path/to/config.json:/static/config/config.json \
           bwsw/cloudstack-ui