---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе №13
subtitle: Фильтр пакетов (firewalld)
author:
  - Агджабекова Эся Рустамовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 05 ноября 2025

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

## Цель работы

Получить навыки настройки пакетного фильтра в Linux с использованием инструментов **firewall-cmd** и **firewall-config**.

# Ход выполнения работы

## Управление брандмауэром с помощью firewall-cmd

![Определение зоны и доступных сервисов](image/01.png){ width=70% }

## Временное добавление сервиса

![Добавление vnc-server и поведение после перезапуска](image/03.png){ width=70% }

## Добавление сервиса в постоянную конфигурацию

![Добавление vnc-server в постоянную конфигурацию](image/04.png){ width=70% }

## Добавление порта

![Добавление порта 2022/tcp](image/05.png){ width=70% }

## Настройка постоянной конфигурации

![Добавление сервисов через GUI](image/06.png){ width=70% }

## Добавление порта через GUI

![Добавление порта 2022/udp](image/07.png){ width=70% }

## Применение конфигурации

![Загруженные изменения](image/08.png){ width=70% }

## Добавление дополнительных служб

![telnet, imap, pop3, smtp](image/09.png){ width=70% }

# Вывод

В ходе работы освоены методы управления сетевыми правилами Linux с помощью **firewalld**:

- просмотр и анализ зон и сервисов,
- временное и постоянное добавление сервисов и портов,
- применение настроек через `firewall-cmd` и интерфейс `firewall-config`.

Получены практические навыки управления сетевой безопасностью и доступом.
