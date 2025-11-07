---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №10
subtitle: Основы работы с модулями ядра операционной системы
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 21 октября 2025

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

Получить навыки работы с утилитами управления модулями ядра операционной системы Linux.

# Ход выполнения работы

## Просмотр устройств и связанных модулей

![Вывод команды lspci -k](image/01.png){ #fig:001 width=70% }

## Список загруженных модулей

![Вывод команды lsmod | sort](image/02.png){ #fig:002 width=70% }

## Проверка и загрузка модуля ext4

![Загрузка и проверка модуля ext4](image/03.png){ #fig:003 width=70% }

## Попытка выгрузки модулей ext4 и xfs

![Выгрузка модулей ext4 и xfs](image/04.png){ #fig:004 width=70% }

## Загрузка и анализ модуля bluetooth

![Модуль bluetooth](image/05.png){ #fig:005 width=70% }

## Проверка версии ядра

![Просмотр версии ядра](image/06.png){ #fig:006 width=70% }

## Обновление ядра системы

![Обновление ядра и системы](image/07.png){ #fig:007 width=70% }

## Проверка новой версии ядра

![Проверка обновлённого ядра](image/08.png){ #fig:008 width=70% }

# Итоги работы

## Вывод

В ходе лабораторной работы были изучены команды и механизмы управления модулями ядра Linux.  
Освоены утилиты `lsmod`, `modprobe`, `modinfo`, `lspci`, а также процесс обновления ядра при помощи `dnf`.  
Получены практические навыки администрирования системы и анализа работы модулей ядра.
