---
## Front matter
title: "Отчёт по лабораторной работе №12"
subtitle: "Настройки сети в Linux"
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

Получить навыки настройки сетевых параметров системы.

# Ход выполнения работы

## Проверка конфигурации сети

1. Получены полномочия администратора с помощью команды `su`.  
2. Выполнена команда `ip -s link`, отобразившая информацию о сетевых интерфейсах и статистике пакетов. Интерфейс **enp0s3** находится в состоянии `UP`, что свидетельствует о его активности.  
   Показаны данные о количестве переданных и полученных байтов и пакетов, а также об ошибках при передаче (см. рис. [@fig:001]).

![Информация о сетевых интерфейсах и статистике пакетов](image/01.png){ #fig:001 width=70% }

3. Просмотрены текущие маршруты с помощью команды `ip route show`.  
   Из вывода видно, что используется интерфейс **enp0s3**, а основной шлюз маршрутизации — **10.0.2.2** (см. рис. [@fig:001]).

4. Проверена текущая адресация командой `ip addr show`.  
   Интерфейс **enp0s3** имеет IPv4-адрес **10.0.2.15/24** и IPv6-адрес **fd17:625c:f037:2:a00:27ff:fe03:1394** (см. рис. [@fig:001]).

5. Проверено сетевое подключение к Интернету с помощью команды `ping -c 4 8.8.8.8`.  
   Все четыре пакета были успешно переданы и получены, потерь нет, что подтверждает исправность соединения (см. рис. [@fig:002]).

![Проверка соединения командой ping](image/02.png){ #fig:002 width=70% }

6. Добавлен дополнительный IP-адрес **10.0.0.10/24** к интерфейсу **enp0s3** с помощью команды  
   `ip addr add 10.0.0.10/24 dev enp0s3`.  
   Проверено, что адрес добавился, — он отображается в выводе `ip addr show` (см. рис. [@fig:002]).

7. Сравнены данные команд `ip addr` и `ifconfig`.  
   Обе утилиты показывают активный интерфейс **enp0s3** с одинаковыми адресами и состоянием `UP` (см. рис. [@fig:004]).

![Вывод команд ifconfig ](image/03.png){ #fig:003 width=70% }

8. Выполнен просмотр всех прослушиваемых портов TCP и UDP с помощью команды `ss -tul`.  
   В списке присутствуют службы **ssh**, **http**, **ftp**, **ipp** и **websm** (см. рис. [@fig:003]).

## Управление сетевыми подключениями с помощью nmcli

1. Получены административные права и выведен список существующих подключений командой `nmcli connection show` (см. рис. [@fig:004]).

![Вывод команды nmcli connection show](image/04.png){ #fig:004 width=70% }

2. Добавлено новое Ethernet-соединение с именем **dhcp**, а затем — соединение **static** с ручной настройкой адресации.  
   Проверено наличие обоих подключений в списке (см. рис. [@fig:004]).

3. Активировано статическое соединение командой `nmcli connection up static`.  
   В выводе команд `nmcli connection show` и `ip addr` видно, что интерфейс **enp0s3** получил статический адрес **10.0.0.10/24** (см. рис. [@fig:005]).

![Вывод команды ip addr](image/05.png){ #fig:005 width=70% }

4. Выполнено переключение обратно на соединение **dhcp**.  
   После активации интерфейс снова получил адрес **10.0.2.15/24**, что подтверждено выводом `ip addr` (см. рис. [@fig:006]).

![Переключение на соединение dhcp](image/06.png){ #fig:006 width=70% }

## Изменение параметров соединения с помощью nmcli

1. Отключено автоподключение для профиля **static** и добавлены DNS-серверы **10.0.0.10** и **8.8.8.8**.  
   Также изменён IP-адрес на **10.0.0.20/24** и добавлен дополнительный адрес **10.20.30.40/16**.  
   После активации соединения `nmcli connection up static` изменения применились успешно (см. рис. [@fig:007]).

![Изменение параметров соединения static](image/07.png){ #fig:007 width=70% }

2. Используя `nmtui`, просмотрены параметры соединения **static**, где отображаются оба IP-адреса, шлюз **10.0.0.1** и DNS-серверы **10.0.0.10**, **8.8.8.8** (см. рис. [@fig:008]).

![Просмотр параметров static в nmtui](image/08.png){ #fig:008 width=70% }

3. Аналогично проверена конфигурация соединения **dhcp**, использующего автоматическую настройку IPv4 и IPv6 (см. рис. [@fig:009]).

![Проверка параметров dhcp в nmtui](image/09.png){ #fig:009 width=70% }

4. В графическом интерфейсе операционной системы отображены оба соединения (**dhcp** и **static**) с актуальными параметрами: IPv4-адресом **10.20.30.40**, шлюзом **10.0.0.1** и DNS-серверами **10.0.0.10**, **8.8.8.8** (см. рис. [@fig:010]).

![Сетевые настройки в графическом интерфейсе](image/10.png){ #fig:010 width=70% }


# Контрольные вопросы

1. **Какая команда отображает только статус соединения, но не IP-адрес?**  
   Команда: `nmcli device status`.

2. **Какая служба управляет сетью в ОС типа RHEL?**  
   Служба: `NetworkManager`.

3. **Какой файл содержит имя узла (устройства) в ОС типа RHEL?**  
   Файл: `/etc/hostname`.

4. **Какая команда позволяет вам задать имя узла (устройства)?**  
   Команда: `hostnamectl set-hostname <имя_узла>`.

5. **Какой конфигурационный файл можно изменить для включения разрешения имён для конкретного IP-адреса?**  
   Файл: `/etc/hosts`.

6. **Какая команда показывает текущую конфигурацию маршрутизации?**  
   Команда: `ip route show`.

7. **Как проверить текущий статус службы NetworkManager?**  
   Команда: `systemctl status NetworkManager`.

8. **Какая команда позволяет вам изменить текущий IP-адрес и шлюз по умолчанию для вашего сетевого соединения?**  
   Команда:  
   `nmcli connection modify <имя_соединения> ipv4.addresses <ip>/<маска> ipv4.gateway <шлюз>`.

# Заключение

В ходе лабораторной работы были изучены основные принципы настройки и управления сетевыми интерфейсами в операционной системе Linux.  
Были рассмотрены команды `ip`, `ping`, `ss`, `ifconfig`, а также средства управления соединениями `nmcli` и `nmtui`.  
В процессе работы выполнена настройка интерфейса с динамической (DHCP) и статической адресацией, добавлены дополнительные IP-адреса, маршруты и DNS-серверы.  
