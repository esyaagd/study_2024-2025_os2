---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №12
subtitle: Настройки сети в Linux
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 31 октября 2025

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

Получить навыки настройки сетевых параметров системы, освоить команды `ip`, `ping`, `ss`, `nmcli` и `nmtui`.

# Ход выполнения работы

## Проверка конфигурации сети

![Информация о сетевых интерфейсах и статистике пакетов](image/01.png){ #fig:001 width=70% }

## Проверка подключения к Интернету

![Проверка соединения командой ping](image/02.png){ #fig:002 width=70% }

## Сравнение ifconfig и ip addr

![Вывод команд ifconfig ](image/03.png){ #fig:003 width=70% }

## Просмотр подключений

![Вывод команды nmcli connection show](image/04.png){ #fig:004 width=70% }

## Добавление DHCP и Static соединений

![Вывод команды ip addr](image/05.png){ #fig:005 width=70% }

## Переключение обратно на DHCP

![Переключение на соединение dhcp](image/06.png){ #fig:006 width=70% }

## Настройка DNS и IP-адресов

![Изменение параметров соединения static](image/07.png){ #fig:007 width=70% }

## Просмотр параметров через nmtui

![Просмотр параметров static в nmtui](image/08.png){ #fig:008 width=70% }

## Графический интерфейс сети

![Сетевые настройки в графическом интерфейсе](image/10.png){ #fig:010 width=70% }

# Итоги работы

## Вывод

В ходе лабораторной работы были изучены принципы настройки сетевых интерфейсов в Linux.  
Получены навыки конфигурации DHCP и статической адресации, добавления маршрутов и DNS-серверов, а также использования инструментов `nmcli` и `nmtui` для управления соединениями.
