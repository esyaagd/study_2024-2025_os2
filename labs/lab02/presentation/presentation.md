---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №2
subtitle: Управление пользователями и группами
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 8 сентября 2025

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

Получить практические навыки работы с учётными записями пользователей и группами в ОС Linux, изучить механизмы разграничения доступа и администрирования.

# Ход выполнения работы

## Определение текущего пользователя

![Вывод команд whoami и id](image/01.png){ #fig:001 width=70% }

## Работа с root и sudoers

![Работа с файлом sudoers](image/02.png){ #fig:002 width=70% }

## Создание пользователей alice и bob

![Создание пользователя bob](image/03.png){ #fig:003 width=70% }

## Настройка параметров login.defs

![Редактирование login.defs](image/04.png){ #fig:004 width=70% }

## Изменение скелетного каталога и .bashrc

![Изменение .bashrc](image/05.png){ #fig:005 width=70% }

## Создание пользователя carol

![Создание пользователя carol и проверка каталогов](image/06.png){ #fig:006 width=70% }

## Настройка параметров пароля carol

![Изменение свойств пароля carol](image/07.png){ #fig:007 width=70% }

## Создание и проверка групп

![Проверка групп пользователей](image/08.png){ #fig:008 width=70% }

# Итоги работы

## Вывод

В ходе работы были освоены приёмы управления пользователями и группами в Linux:  
создание учётных записей, настройка параметров паролей, изменение конфигурационных файлов, работа с группами и sudo. Получены практические навыки администрирования.
