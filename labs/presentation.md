---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №9
subtitle: Управление SELinux
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 13 октября 2025

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

# Цель работы

## Цель

Получить навыки работы с контекстом безопасности и политиками SELinux, освоить управление режимами работы, восстановление контекстов безопасности и настройку SELinux для различных служб.

# Ход выполнения работы

## Проверка состояния SELinux

![Проверка текущего состояния SELinux](image/01.png){ #fig:001 width=70% }

## Переключение режима SELinux

![Переключение режима SELinux в Permissive](image/02.png){ #fig:002 width=70% }

## Отключение SELinux

![Отключение SELinux в конфигурационном файле](image/03.png){ #fig:003 width=70% }

## Проверка отключённого режима

![Попытка включить SELinux после отключения](image/04.png){ #fig:004 width=70% }

## Восстановление enforcing-режима

![Процесс relabeling при включении SELinux](image/05.png){ #fig:005 width=70% }

## Проверка состояния после relabeling

![Проверка состояния SELinux после восстановления](image/06.png){ #fig:006 width=70% }

## Использование restorecon

![Восстановление контекста безопасности с помощью restorecon](image/07.png){ #fig:007 width=70% }

## Настройка контекста для веб-сервера

![Изменение конфигурационного файла httpd.conf для новой директории](image/08.png){ #fig:008 width=70% }

## Проверка работы веб-сервера

![Отображение пользовательской страницы веб-сервера](image/11.png){ #fig:011 width=70% }

## Настройка boolean-переменных

![Настройка переключателя SELinux для службы FTP](image/12.png){ #fig:012 width=70% }

# Итоги работы

## Вывод

В ходе лабораторной работы были изучены режимы работы SELinux, механизмы управления контекстами безопасности и настройка политик для различных служб.  
Получены практические навыки администрирования, необходимые для обеспечения безопасности и стабильности системы Linux.
