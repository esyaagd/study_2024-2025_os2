---
## Front matter
title: "Отчёт по лабораторной работе №11"
subtitle: "Управление загрузкой системы"
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

Получить навыки работы с загрузчиком системы GRUB2

# Ход выполнения работы

## Модификация параметров GRUB2

1. Получены административные полномочия с помощью команды `su -`.  
   После этого открыт файл **/etc/default/grub** в текстовом редакторе `nano` и изменён параметр **GRUB_TIMEOUT** с 10 секунд на 30 (см. рис. [@fig:001]).

![Редактирование параметров GRUB](image/Screenshot_1.png){ #fig:001 width=70% }

2. Для применения изменений выполнена команда `grub2-mkconfig > /boot/grub2/grub.cfg`, которая сгенерировала новый конфигурационный файл GRUB (см. рис. [@fig:002]).

![Генерация нового файла конфигурации GRUB](image/Screenshot_2.png){ #fig:002 width=70% }

3. После перезагрузки системы проверено отображение меню загрузчика GRUB, содержащее список доступных записей загрузки (см. рис. [@fig:003]).

![Меню загрузчика GRUB](image/Screenshot_4.png){ #fig:003 width=70% }

## Устранения неполадок

1. Для перехода в **режим восстановления (rescue mode)** выполнено редактирование параметров загрузки: в строке, начинающейся с `linux`, добавлен параметр `systemd.unit=rescue.target` и удалены опции `rhgb` и `quiet` (см. рис. [@fig:005]).

![Редактирование строки загрузки для режима rescue](image/Screenshot_5.png){ #fig:005 width=70% }

2. После загрузки в режиме восстановления просмотрен список активных модулей и служб с помощью команды `systemctl list-units` (см. рис. [@fig:006]).  
   Затем показаны переменные среды с использованием команды `systemctl show-environment` (см. рис. [@fig:007]).

![Список загруженных модулей в режиме rescue](image/Screenshot_6.png){ #fig:006 width=70% }

3. Аналогичным образом система была загружена в **аварийный режим (emergency mode)**, добавлением параметра `systemd.unit=emergency.target` в строку загрузки ядра (см. рис. [@fig:008]).

![Редактирование строки загрузки для режима emergency](image/Screenshot_7.png){ #fig:007 width=70% }

4. В аварийном режиме также был просмотрен список активных модулей с помощью команды `systemctl list-units`, что показало минимальный набор запущенных служб (см. рис. [@fig:009]).

![Активные модули в emergency mode](image/Screenshot_8.png){ #fig:008 width=70% }

## Сброс пароля root

1. Для сброса пароля root система была загружена с параметром `rd.break`, добавленным в строку загрузки ядра (см. рис. [@fig:010]).

![Добавление параметра rd.break в строку загрузки](image/Screenshot_9.png){ #fig:009 width=70% }

2. После остановки загрузки на этапе initramfs выполнено перемонтирование файловой системы в режим чтения-записи и предпринята попытка входа в chroot-среду, а затем смены пароля с помощью `passwd`. Однако команды не были найдены в текущей среде (см. рис. [@fig:011]).

![Попытка смены пароля root в режиме rd.break](image/Screenshot_10.png){ #fig:010 width=70% }

# Контрольные вопросы

1. **Какой файл конфигурации следует изменить для применения общих изменений в GRUB2?**  
   Необходимо отредактировать файл `/etc/default/grub`.

2. **Как называется конфигурационный файл GRUB2, в котором вы применяете изменения для GRUB2?**  
   Основной конфигурационный файл GRUB2 — `/boot/grub2/grub.cfg`.

3. **После внесения изменений в конфигурацию GRUB2, какую команду вы должны выполнить, чтобы изменения сохранились и воспринялись при загрузке системы?**  
   Команда для обновления конфигурации: `grub2-mkconfig -o /boot/grub2/grub.cfg`.

# Заключение

В ходе лабораторной работы были изучены принципы настройки и модификации загрузчика **GRUB2** в операционной системе Linux.  
Были изменены параметры конфигурационного файла `/etc/default/grub`, обновлён основной файл загрузчика `/boot/grub2/grub.cfg`, а также выполнена проверка отображения меню при загрузке системы.  
Изучены режимы **rescue** и **emergency**, их назначение и особенности функционирования.  
