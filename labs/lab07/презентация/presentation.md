---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №7
subtitle: Управление журналами событий в системе
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 2 октября 2025

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

Получить навыки работы с журналами мониторинга различных событий в системе.

# Ход выполнения работы

## Мониторинг системных событий

![Мониторинг системных событий в реальном времени](image/01.png){ #fig:001 width=70% }

## Ошибка авторизации и команда logger

![Ошибка при вводе неправильного пароля](image/02.png){ #fig:002 width=70% }

## Сообщение через logger

![Сообщение, записанное с помощью logger](image/03.png){ #fig:003 width=70% }

## Просмотр журнала secure

![Просмотр сообщений безопасности](image/04.png){ #fig:004 width=70% }

## Установка и запуск Apache

![Установка и запуск Apache](image/05.png){ #fig:005 width=70% }

## Перенаправление ошибок Apache в syslog

![Добавление правила ErrorLog в httpd.conf](image/07.png){ #fig:007 width=70% }

## Настройка rsyslog для ошибок Apache

![Создание файла конфигурации для ошибок Apache](image/08.png){ #fig:008 width=70% }

## Отладочные сообщения через rsyslog

![Вывод отладочного сообщения через logger](image/10.png){ #fig:010 width=70% }

## Использование journalctl

![Просмотр журнала с момента запуска](image/11.png){ #fig:011 width=70% }

## Фильтрация в journalctl

![Фильтрация только ошибок](image/17.png){ #fig:017 width=70% }

## Постоянный журнал journald

![Включение постоянного журнала journald](image/22.png){ #fig:022 width=70% }

# Итоги работы

## Вывод

В ходе лабораторной работы были изучены принципы работы с системными журналами в Linux.  
Рассмотрена настройка rsyslog, перенаправление сообщений Apache и отладочных логов.  
Освоено использование `journalctl` с фильтрацией и настройка постоянного журнала journald.  
Получены практические навыки администрирования системных журналов.
