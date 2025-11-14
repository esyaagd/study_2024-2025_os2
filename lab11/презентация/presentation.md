---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №11
subtitle: Управление загрузкой системы
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 26 октября 2025

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

Получить навыки работы с загрузчиком **GRUB2**, научиться изменять его параметры и устранять неполадки при загрузке системы.

# Ход выполнения работы

## Модификация параметров GRUB2

![Редактирование параметров GRUB](image/Screenshot_1.png){ #fig:001 width=70% }

## Генерация нового файла конфигурации

![Создание нового grub.cfg](image/Screenshot_2.png){ #fig:002 width=70% }

## Проверка меню загрузчика

![Меню загрузчика GRUB](image/Screenshot_4.png){ #fig:003 width=70% }

## Переход в режим восстановления (rescue)

![Редактирование строки загрузки для режима rescue](image/Screenshot_5.png){ #fig:004 width=70% }

## Просмотр загруженных модулей и переменных среды

![Список загруженных модулей](image/Screenshot_6.png){ #fig:005 width=70% }

## Загрузка в аварийном режиме (emergency)

![Режим emergency](image/Screenshot_8.png){ #fig:006 width=70% }

## Загрузка с параметром rd.break

![Добавление параметра rd.break](image/Screenshot_9.png){ #fig:007 width=70% }

## Перемонтирование и попытка смены пароля

![Попытка смены пароля root](image/Screenshot_10.png){ #fig:008 width=70% }

# Итоги работы

## Вывод

В ходе лабораторной работы были изучены принципы настройки и модификации загрузчика **GRUB2**.  
Выполнено редактирование конфигурационных файлов, генерация обновлённого `grub.cfg`, а также изучены режимы **rescue** и **emergency**.  
Получены практические навыки восстановления системы и сброса пароля **root**.
