---
## Front matter
title: "Отчёт по лабораторной работе №7"
subtitle: "Управление журналами событий в системе"
author: "Агджабекова Эся Рустамовна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true
toc-depth: 2
lof: true
lot: true
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
    - spelling=modern
    - babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float}
  - \floatplacement{figure}{H}
---

# Цель работы

Получить навыки работы с журналами мониторинга различных событий в системе.

# Ход выполнения работы

## Мониторинг журнала системных событий в реальном времени  

1. В трёх вкладках терминала получены полномочия администратора командой `su -`.  
2. Во второй вкладке запущен мониторинг системных событий в реальном времени:  
   tail -f /var/log/messages  
   (см. рис. [@fig:001]).  

![Мониторинг системных событий в реальном времени](image/01.png){ #fig:001 width=70% }  

3. В третьей вкладке выполнена попытка получить права администратора с неверным паролем. В результате в журнале зафиксирована ошибка авторизации `FAILED su (to root)` (см. рис. [@fig:002]).  

![Ошибка при вводе неправильного пароля](image/02.png){ #fig:002 width=70% }  

4. В оболочке пользователя выполнена команда:  
   logger hello  
   Сообщение появилось в окне мониторинга и было сохранено в журнале `/var/log/messages` (см. рис. [@fig:003]).  

![Сообщение, записанное с помощью logger](image/03.png){ #fig:003 width=70% }  

5. Мониторинг системных сообщений во второй вкладке остановлен комбинацией `Ctrl + C`. Затем просмотрены последние 20 строк файла журнала безопасности командой:  
   tail -n 20 /var/log/secure  
   В нём отобразились записи о неудачной попытке авторизации (см. рис. [@fig:004]).  

![Просмотр сообщений безопасности](image/04.png){ #fig:004 width=70% }  

## Изменение правил rsyslog.conf  

1. Установлен Apache (если ранее не был установлен) и запущена веб-служба:  
   dnf -y install httpd  
   systemctl start httpd  
   systemctl enable httpd  
   (см. рис. [@fig:005]).  

![Установка и запуск Apache](image/05.png){ #fig:005 width=70% }  

2. Во второй вкладке терминала просмотрен журнал ошибок веб-службы командой  
   tail -f /var/log/httpd/error_log  
   (см. рис. [@fig:006]).  

![Просмотр журнала ошибок Apache](image/06.png){ #fig:006 width=70% }  

3. В файле `/etc/httpd/conf/httpd.conf` добавлена строка перенаправления ошибок в syslog:  
   ErrorLog syslog:local1  
   (см. рис. [@fig:007]).  

![Добавление правила ErrorLog в httpd.conf](image/07.png){ #fig:007 width=70% }  

4. В каталоге `/etc/rsyslog.d` создан файл `httpd.conf` со строкой:  
   local1.* -/var/log/httpd-error.log  
   (см. рис. [@fig:008]).  

![Создание файла конфигурации для ошибок Apache](image/08.png){ #fig:008 width=70% }  

5. Перезагружены службы `rsyslog` и `httpd`. Сообщения об ошибках веб-сервера начали записываться в `/var/log/httpd-error.log`.  

6. Создан файл `/etc/rsyslog.d/debug.conf` с правилом:  
   *.debug /var/log/messages-debug  
   (см. рис. [@fig:009]).  

![Создание конфигурации для отладочных сообщений](image/09.png){ #fig:009 width=70% }  

7. После перезапуска `rsyslog` запущен мониторинг нового файла:  
   tail -f /var/log/messages-debug  

8. С помощью команды  
   logger -p daemon.debug "Daemon Debug Message"  
   в журнал отправлено тестовое сообщение, которое успешно отобразилось в логе (см. рис. [@fig:010]).  

![Вывод отладочного сообщения через logger](image/10.png){ #fig:010 width=70% }  

## Использование journalctl  

1. Просмотрен журнал событий с момента последнего запуска системы командой  
   journalctl  
   (см. рис. [@fig:011]).  

![Просмотр журнала с момента запуска](image/11.png){ #fig:011 width=70% }  

2. Выведено содержимое журнала без использования пейджера:  
   journalctl --no-pager  
   (см. рис. [@fig:012]).  

![Вывод журнала без пейджера](image/12.png){ #fig:012 width=70% }  

3. Включён режим просмотра журнала в реальном времени:  
   journalctl -f  
   Для выхода использована комбинация `Ctrl + C` (см. рис. [@fig:013]).  

![Просмотр журнала в реальном времени](image/13.png){ #fig:013 width=70% }  

4. Для изучения доступных параметров фильтрации к команде journalctl была добавлена двойная клавиша Tab. Отобразился список поддерживаемых ключей (см. рис. [@fig:014]).  

![Параметры фильтрации journalctl](image/14.png){ #fig:014 width=70% }  

5. Отображены события, связанные с пользователем UID 0:  
   journalctl _UID=0  
   (см. рис. [@fig:015]).  

![Фильтрация по UID=0](image/15.png){ #fig:015 width=70% }  

6. Выведены последние 20 строк журнала:  
   journalctl -n 20  
   (см. рис. [@fig:016]).  

![Просмотр последних 20 строк](image/16.png){ #fig:016 width=70% }  

7. Получены только сообщения с уровнем «ошибка»:  
   journalctl -p err  
   (см. рис. [@fig:017]).  

![Фильтрация только ошибок](image/17.png){ #fig:017 width=70% }  

8. Просмотрены все события со вчерашнего дня:  
   journalctl --since yesterday  
   (см. рис. [@fig:018]).  

![Просмотр событий со вчерашнего дня](image/18.png){ #fig:018 width=70% }  

9. Отображены только ошибки со вчерашнего дня:  
   journalctl --since yesterday -p err  
   (см. рис. [@fig:019]).  

![Ошибки со вчерашнего дня](image/19.png){ #fig:019 width=70% }  

10. Использован режим детализированного вывода:  
    journalctl -o verbose  
    (см. рис. [@fig:020]).  

![Детализированный вывод сообщений](image/20.png){ #fig:020 width=70% }  

11. Для просмотра дополнительной информации о модуле `sshd` использована команда:  
    journalctl _SYSTEMD_UNIT=sshd.service  
    В выводе отобразились записи о запуске службы (см. рис. [@fig:021]).  

![Просмотр информации о модуле sshd](image/21.png){ #fig:021 width=70% }  

## Постоянный журнал journald  

1. Создан каталог для хранения постоянных записей журнала:  
   mkdir -p /var/log/journal  

2. Для каталога `/var/log/journal` скорректированы права доступа, чтобы служба `systemd-journald` могла вести туда запись:  
   chown root:systemd-journal /var/log/journal  
   chmod 2755 /var/log/journal  

3. Чтобы принять изменения без перезагрузки системы, journald был принудительно перезапущен сигналом:  
   killall -USR1 systemd-journald  

4. После этого просмотрен журнал с момента последней перезагрузки с помощью команды:  
   journalctl -b  
   (см. рис. [@fig:022]).  

![Включение постоянного журнала journald](image/22.png){ #fig:022 width=70% }  

# Контрольные вопросы

1. **Какой файл используется для настройки rsyslogd?**  
   Основной конфигурационный файл — `/etc/rsyslog.conf`. Дополнительные правила могут храниться в каталоге `/etc/rsyslog.d/`.

2. **В каком файле журнала rsyslogd содержатся сообщения, связанные с аутентификацией?**  
   Сообщения об аутентификации и авторизации записываются в файл `/var/log/secure`.

3. **Если вы ничего не настроите, то сколько времени потребуется для ротации файлов журналов?**  
   По умолчанию лог-файлы ротируются **еженедельно**, настройки задаются в `/etc/logrotate.conf`.

4. **Какую строку следует добавить в конфигурацию для записи всех сообщений с приоритетом info в файл `/var/log/messages.info`?**  
	`*.info /var/log/messages.info`


5. **Какая команда позволяет вам видеть сообщения журнала в режиме реального времени?**  
Используются команды:  
- `tail -f /var/log/имя_журнала` — для файлов rsyslog.  
- `journalctl -f` — для systemd-journald.

6. **Какая команда позволяет вам видеть все сообщения журнала, которые были написаны для PID 1 между 9:00 и 15:00?**  
	`journalctl _PID=1 --since "09:00" --until "15:00"`


7. **Какая команда позволяет вам видеть сообщения journald после последней перезагрузки системы?**  
	`journalctl -b`
	

8. **Какая процедура позволяет сделать журнал journald постоянным?**  
- Создать каталог `/var/log/journal`.  
- Назначить права доступа:  
  `chown root:systemd-journal /var/log/journal`  
  `chmod 2755 /var/log/journal`  
- Перезапустить journald командой `killall -USR1 systemd-journald` или выполнить перезагрузку.  


# Заключение

В ходе лабораторной работы были изучены принципы работы с системными журналами в Linux. Рассмотрена настройка службы rsyslog, включая перенаправление сообщений веб-сервера Apache и регистрацию отладочной информации в отдельные файлы. Освоены приёмы мониторинга логов в реальном времени с помощью `tail` и `journalctl`, выполнена фильтрация событий по различным параметрам. Настроен постоянный журнал `journald`, что позволило сохранять сообщения после перезагрузки системы. Получены практические навыки администрирования, связанные с управлением логами и диагностикой работы служб.  
