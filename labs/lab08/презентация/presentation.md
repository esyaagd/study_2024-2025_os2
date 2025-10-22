---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №8
subtitle: Планировщики событий
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 9 октября 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цели и задачи работы

## Цель работы

Получить навыки работы с планировщиками событий **cron** и **at** в ОС Linux.

# Ход выполнения работы

## Проверка службы cron

![Проверка статуса службы crond](image/Screenshot_1.png){ #fig:001 width=70% }

## Изучение файла /etc/crontab

![Просмотр crontab](image/Screenshot_2.png){ #fig:002 width=70% }

## Создание задания cron

![Добавление задания cron](image/Screenshot_3.png){ #fig:003 width=70% }

## Проверка выполнения задания

![Проверка логов cron](image/Screenshot_4.png){ #fig:004 width=70% }

## Создание сценария в /etc/cron.hourly

![Создание сценария eachhour](image/Screenshot_5.png){ #fig:005 width=70% }

## Добавление задания в /etc/cron.d

![Задание в /etc/cron.d](image/Screenshot_6.png){ #fig:006 width=70% }

## Проверка службы atd

![Планирование через at](image/Screenshot_7.png){ #fig:007 width=70% }


# Итоги работы

## Вывод

В ходе лабораторной работы изучены средства автоматизации в Linux:  
- Настройка и использование **cron** для периодических задач.  
- Создание скриптов и расписаний в системных каталогах cron.  
- Планирование единичных заданий с помощью **at**.  

Получены практические навыки по организации автоматического выполнения задач в операционной системе Linux.
