---
## Front matter
title: "Отчёт по лабораторной работе №8"
subtitle: "Планировщики событий"
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

Получение навыков работы с планировщиками событий cron и at.

# Ход выполнения работы

## Планирование задач с помощью cron

1. Получены права суперпользователя командой `su`.  
2. Проверен статус службы **crond**, отвечающей за выполнение планировщика задач. Видно, что служба активна и запущена (см. рис. [@fig:001]).  

![Проверка статуса службы crond](image/Screenshot_1.png){ #fig:001 width=70% }

3. Просмотрено содержимое файла `/etc/crontab`, где приведены основные переменные окружения и пример формата задания cron (см. рис. [@fig:001]).  
4. Выполнена проверка списка текущих заданий пользователя root командой `crontab -l`. Так как расписание не было создано ранее, список оказался пуст.  
5. Открыт редактор crontab с помощью команды `crontab -e` и добавлена запись:  
   `*/1 * * * * logger This message is written from root cron`  
   Эта запись означает выполнение команды каждую минуту. Поля выражения cron расшифровываются следующим образом:  
   - `*/1` — каждая минута  
   - `*` — каждый час  
   - `*` — каждый день месяца  
   - `*` — каждый месяц  
   - `*` — каждый день недели  
   (см. рис. [@fig:002])  

![Редактирование файла crontab с первой записью](image/Screenshot_2.png){ #fig:002 width=70% }

6. После сохранения изменений просмотрено текущее расписание `crontab -l`, где отображается добавленная строка (см. рис. [@fig:003]).  
7. Через несколько минут проверен системный журнал `/var/log/messages` командой `grep written /var/log/messages`.  
   Убедились, что сообщения от `logger` действительно записываются каждые 1–2 минуты (см. рис. [@fig:003]).

![Результат выполнения задания cron и проверка журнала](image/Screenshot_3.png){ #fig:003 width=70% }

8. Изменена запись в crontab на выполнение задания каждый час в будние дни (понедельник–пятница):  
   `0 */1 * * 1-5 logger This message is written from root cron`  
   Это выражение означает:  
   - `0` — выполнять в начале часа  
   - `*/1` — каждый час  
   - `*` — каждый день месяца  
   - `*` — каждый месяц  
   - `1-5` — с понедельника по пятницу (см. рис. [@fig:004])

![Изменение расписания cron на выполнение каждый час в будние дни](image/Screenshot_4.png){ #fig:004 width=70% }

9. В каталоге `/etc/cron.hourly` создан файл сценария `eachhour` и в него добавлен скрипт:  
   `#!/bin/sh`  
   `logger This message is written at $(date)`  
   Скрипт регистрирует сообщение с текущей датой и временем в системном журнале (см. рис. [@fig:005]).

![Создание сценария eachhour в /etc/cron.hourly](image/Screenshot_5.png){ #fig:005 width=70% }

10. В каталоге `/etc/cron.d` создан файл `eachhour`, содержащий строку:  
    `11 * * * * root logger This message is written from /etc/cron.d`  
    Этот файл добавляет отдельное расписание, выполняющее команду `logger` от имени пользователя root каждую 11-ю минуту каждого часа (см. рис. [@fig:006]).

![Создание задания в каталоге /etc/cron.d](image/Screenshot_6.png){ #fig:006 width=70% }

## Планирование заданий с помощью at

1. Проверен статус службы **atd**, которая отвечает за отложенное выполнение задач. Служба активна (см. рис. [@fig:007]).  
2. Создано задание для однократного выполнения команды `logger` в заданное время с помощью утилиты `at`.  
3. После ввода команды `at 12:59` в интерактивном режиме добавлена строка `logger message from at`, и завершён ввод комбинацией **Ctrl+D**.  
4. Проверен список заданий командой `atq`.  
5. После наступления заданного времени проверено наличие записей в журнале `/var/log/messages` с помощью `grep 'from at' /var/log/messages`.  
   Сообщения успешно записаны в системный лог (см. рис. [@fig:007]).

![Планирование и выполнение задания с помощью at](image/Screenshot_7.png){ #fig:007 width=70% }


# Заключение

В ходе лабораторной работы были изучены средства планирования задач в Linux с использованием утилит **cron** и **at**.  
На практике выполнена настройка периодических заданий через `crontab`, создание сценариев в каталогах `/etc/cron.hourly` и `/etc/cron.d`, а также отложенное выполнение команд с помощью планировщика **atd**.  
