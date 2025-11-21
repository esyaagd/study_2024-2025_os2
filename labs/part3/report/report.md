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

   ![Базовая диагностика сети](../images/07.png
){ #fig:007 }

3. Тест на тему настройка ssh доступа и его защита (см. рис. [@fig:013]).  

   ![настройка ssh доступа и его защита](../images/013.png
){ #fig:013 }

4.  Тест на тему повышение безопаности сетевого взаимодействия (см. рис. [@fig:018]).  

   ![настройка ssh доступа и его защита](../images/018.png
){ #fig:018 }

5. Тест на тему что такое пакеты и как они устроены (см. рис. [@fig:024]).  

   ![то такое пакеты и как они устроены](../images/024.png
){ #fig:024 }

6. Тест на тему  обновление системы и безопасность (см. рис. [@fig:028]).  

   ![ обновление системы и безопасность](../images/028.png
){ #fig:028 }

 
7. Тест на тему работа с зависимостями и решениями конфликтов  [@fig:032]).  

   ![работа с зависимостями и решениями конфликтов](../images/032.png
){ #fig:032 }

 
8.Тест на тему работа с локальными пакетами и сторонними источниками (см. рис. [@fig:037]).  

   ![работа с локальными пакетами и сторонними источниками](../images/037.png
){ #fig:037 }

9. Тест на тему Знакомство с логами(../images/041.png../images/042.png../images/043.png../images/044.png)
 (см. рис. [@fig:041]).  

   ![ Знакомство с логами](../images/041.png
){ #fig:041 }

10. Тест на тему система логирования  (см. рис. [@fig:045]).  

   ![система логирования ](../images/045.png
){ #fig:045 }

11.Тест на тему поиск и фильтрация логов под конкретные задачи  (см. рис. [@fig:049]).  

   ![поиск и фильтрация логов под конкретные задачи ](../images/049.png
) 
){ #fig:049 }

  
12.Тест на тему расследование инцидентов по логам (см. рис. [@fig:053]).  

   ![расследование инцидентов по логам](../images/053.png
){ #fig:053 }

13. Тест на тему управление жизненними циклами логов и ротация  (см. рис. [@fig:057]).  

   ![управление жизненними циклами логов и ротация](../images/057.png
){ #fig:057}

14. Тест на тему контейниризация как подход (см. рис. [@fig:0061]).  

   ![контейниризация как подход  ](../images/061.png
){ #fig:0061 width=70% }

15. Тест на тему работа с контейнерами в podman  (см. рис. [@fig:0069]).  

   ![работа с контейнерами в podman](../images/067.png
){ #fig:0069  }

16.  Тест на тему управление ресурсами контейнеров (см. рис. [@fig:0073]).  

   ![управление ресурсами контейнеров](../images/073.png
){ #fig:0073 }

17. Тест на тему образы реестры и базовая безопасность  (см. рис. [@fig:0079]).  

   ![ образы реестры и базовая безопасность](../images/079.png
){ #fig:0079 }


# Заключение

В ходе прохождения курса Системный администратор Linux с нуля были изучены основные принципы работы Linux.  
В результате работы получены практические навыки администрирования и конфигурирования Linux.


