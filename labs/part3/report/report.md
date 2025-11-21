---
## Front matter
title: "Отчёт по курсу Системный администратор Linux с нуля"
subtitle: ""
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

пройти курс Системный адмистратор Linux с нуля .

# Ход выполнения работы

## Часть 3

1. Тест на тему Основы сетевой конфигурации в Linux (см. рис. [@fig:001]).  

   ![Основы сетевой конфигурации в Linux](../images/01.png
){ #fig:001 }

2.Тест на тему Базовая диагностика сети  (см. рис. [@fig:007]).  

   ![Базовая диагностика сети](../images/07.png../images/08.png../images/09.png../images/010.png../images/012.png
){ #fig:007 }

3. Тест на тему настройка ssh доступа и его защита (см. рис. [@fig:013]).  

   ![настройка ssh доступа и его защита](../images/013.png../images/014.png../images/015.png../images/016.png../images/017.png
){ #fig:013 }

4.  Тест на тему повышение безопаности сетевого взаимодействия (см. рис. [@fig:018]).  

   ![настройка ssh доступа и его защита](../images/018.png../images/019.png../images/020.png../images/021.png../images/022.png../images/23.png
){ #fig:018 }

5. Тест на тему что такое пакеты и как они устроены (см. рис. [@fig:024]).  

   ![то такое пакеты и как они устроены](../images/024.png../images/025.png../images/026.png../images/027.png
){ #fig:024 }

6. Тест на тему  обновление системы и безопасность (см. рис. [@fig:028]).  

   ![ обновление системы и безопасность](../images/028.png../images/029.png../images/030.png../images/031.png
){ #fig:028 }

 
7. Тест на тему работа с зависимостями и решениями конфликтов  [@fig:032]).  

   ![работа с зависимостями и решениями конфликтов](../images/032.png../images/033.png../images/034.png../images/035.png../images/036.png
){ #fig:032 }

 
8.Тест на тему работа с локальными пакетами и сторонними источниками (см. рис. [@fig:037]).  

   ![работа с локальными пакетами и сторонними источниками](../images/037.png../images/038.png../images/039.png../images/040.png
){ #fig:037 }

9. Тест на тему Знакомство с логами(../images/041.png../images/042.png../images/043.png../images/044.png)
 (см. рис. [@fig:041]).  

   ![ Знакомство с логами](../images/041.png../images/042.png../images/043.png../images/044.png
){ #fig:041 }

10. Тест на тему система логирования  (см. рис. [@fig:045]).  

   ![система логирования ](../images/045.png../images/046.png../images/047.png../images/048.png
){ #fig:045 }

11.Тест на тему поиск и фильтрация логов под конкретные задачи  (см. рис. [@fig:049]).  

   ![поиск и фильтрация логов под конкретные задачи ](../images/049.png../images/050.png../images/051.png../images/052.png
) 
){ #fig:049 }

  
12.Тест на тему расследование инцидентов по логам (см. рис. [@fig:053]).  

   ![расследование инцидентов по логам](../images/053.png../images/054.png../images/055.png../images/056.png
){ #fig:053 }

13. Тест на тему управление жизненними циклами логов и ротация  (см. рис. [@fig:057]).  

   ![управление жизненними циклами логов и ротация](../images/057.png../images/058.png../images/059.png../images/060.png
){ #fig:057}

14. Тест на тему контейниризация как подход (см. рис. [@fig:0061]).  

   ![контейниризация как подход  ](../images/061.png../images/062.png../images/063.png../images/064.png../images/065.png../images/066.png
){ #fig:0061 width=70% }

15. Тест на тему работа с контейнерами в podman  (см. рис. [@fig:0069]).  

   ![работа с контейнерами в podman](../images/067.png../images/068.png../images/069.png../images/070.png../images/071.png../images/072.png
){ #fig:0069  }

16.  Тест на тему управление ресурсами контейнеров (см. рис. [@fig:0073]).  

   ![управление ресурсами контейнеров](../images/073.png../images/074.png../images/075.png../images/076.png../images/07.png../images/078.png
){ #fig:0073 }

17. Тест на тему образы реестры и базовая безопасность  (см. рис. [@fig:0079]).  

   ![ образы реестры и базовая безопасность](../images/079.png../images/080.png../images/081.png../images/082.png../images/083.png
){ #fig:0079 }


# Заключение

В ходе прохождения курса Системный администратор Linux с нуля были изучены основные принципы работы Linux.  
В результате работы получены практические навыки администрирования и конфигурирования Linux.


