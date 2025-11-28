---
## Front matter
title: "Отчёт по лабораторной работе №13"
subtitle: "Фильтр пакетов"
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

Получить навыки настройки пакетного фильтра в Linux.

# Выполнение работы

## Управление брандмауэром с помощью firewall-cmd

1. Получены права администратора. Определена текущая зона по умолчанию, просмотрены доступные зоны и список поддерживаемых сервисов  
   (см. рис. [@fig:001]).

![Определение зоны по умолчанию, доступных зон и сервисов](image/01.png){ #fig:001 width=70% }

2. Просмотрены активные сервисы в текущей зоне. Сравнён вывод информации при использовании `list-all` и `list-all --zone=public`  
   (см. рис. [@fig:002]).

![Сравнение вывода list-all и list-all --zone](image/02.png){ #fig:002 width=70% }

3. Временно добавлен сервис **vnc-server**. Выполнена проверка — сервис появился в конфигурации.  
4. Выполнен перезапуск службы брандмауэра. Сервис **vnc-server** исчез из конфигурации, так как изменение было внесено только во время выполнения и не сохранилось в постоянной конфигурации  
   (см. рис. [@fig:003]).

![Добавление vnc-server и поведение после перезапуска](image/03.png){ #fig:003 width=70% }

5. Сервис **vnc-server** добавлен повторно с сохранением в постоянной конфигурации. После перезагрузки конфигурации подтверждено его наличие  
   (см. рис. [@fig:004]).

![Добавление vnc-server в постоянную конфигурацию](image/04.png){ #fig:004 width=70% }

6. В постоянную конфигурацию добавлен порт **2022/tcp**. После перезагрузки конфигурации подтверждено его появление  
   (см. рис. [@fig:005]).

![Добавление порта 2022/tcp](image/05.png){ #fig:005 width=70% }

## Управление брандмауэром с помощью firewall-config

1. Запущен графический интерфейс `firewall-config`.  
2. В параметре **Configuration** выбрано значение *Permanent*, чтобы все изменения становились постоянными.  
3. Для зоны **public** включены службы **http**, **https** и **ftp** (см. рис. [@fig:006]).  
4. На вкладке *Ports* добавлен порт **2022/udp** (см. рис. [@fig:007]).

![Добавление сервисов в графическом интерфейсе](image/06.png){ #fig:006 width=70% }

![Добавление порта 2022/udp](image/07.png){ #fig:007 width=70% }

5. Проверка показала, что изменения ещё не применены, так как были внесены в постоянную конфигурацию.  
6. После перезагрузки конфигурации все изменения вступили в силу  
   (см. рис. [@fig:008]).

![Активированные службы после reload](image/08.png){ #fig:008 width=70% }

## Самостоятельная работа

1. Через командную строку добавлена служба **telnet**.  
2. Через графический интерфейс включены службы **imap**, **pop3** и **smtp**.  
3. Подтверждено, что все изменения сохранены и применены  
   (см. рис. [@fig:009]).

![Активированные службы: telnet, imap, pop3, smtp](image/09.png){ #fig:009 width=70% }

# Контрольные вопросы

1. **Какая служба должна быть запущена перед началом работы с firewall-config?**  
   Служба `firewalld`.

2. **Какая команда позволяет добавить UDP-порт 2355 в конфигурацию брандмауэра в зоне по умолчанию?**  
   Используется параметр `--add-port=2355/udp`.

3. **Какая команда позволяет показать всю конфигурацию брандмауэра во всех зонах?**  
   `firewall-cmd --list-all-zones`.

4. **Какая команда позволяет удалить службу vnc-server из текущей конфигурации брандмауэра?**  
   Используется параметр `--remove-service=vnc-server`.

5. **Какая команда firewall-cmd позволяет активировать новую конфигурацию, добавленную опцией --permanent?**  
   `firewall-cmd --reload`.

6. **Какой параметр firewall-cmd позволяет проверить, что новая конфигурация была добавлена в текущую зону и теперь активна?**  
   `firewall-cmd --list-all`.

7. **Какая команда позволяет добавить интерфейс eno1 в зону public?**  
   Используется параметр `--zone=public --add-interface=eno1`.

8. **Если добавить новый интерфейс в конфигурацию брандмауэра, пока не указана зона, в какую зону он будет добавлен?**  
   В зону по умолчанию (*default zone*).

# Заключение

В ходе выполнения лабораторной работы были изучены способы управления брандмауэром Linux с использованием инструментов `firewall-cmd` и графической утилиты `firewall-config`. Были получены навыки просмотра активных зон и служб, добавления сервисов и портов как во временную, так и в постоянную конфигурацию. На практике отработано различие между конфигурацией времени выполнения и постоянной конфигурацией, а также применение перезагрузки правил для их активации. В результате закреплены навыки администрирования сетевой безопасности и управления правилами доступа в системах на базе Linux.
