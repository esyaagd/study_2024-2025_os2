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

   ![Основы сетевой конфигурации в Linux](<img width="1920" height="1080" alt="Снимок экрана (169)" src="https://github.com/user-attachments/assets/36ca68d0-7272-4d30-8bb1-caaebda5dca3" />
<img width="1920" height="1080" alt="Снимок экрана (168)" src="https://github.com/user-attachments/assets/8070a9b9-b0fe-450b-8ae1-d7ff7421fd62" />
<img width="1920" height="1080" alt="Снимок экрана (167)" src="https://github.com/user-attachments/assets/e52dd3d2-d244-41e4-b382-ebd8844ef093" />
<img width="1920" height="1080" alt="Снимок экрана (166)" src="https://github.com/user-attachments/assets/2193d37d-989f-467c-928e-17cb0e6563e8" />
<img width="1920" height="1080" alt="Снимок экрана (165)" src="https://github.com/user-attachments/assets/98d2dca7-3aa5-4140-8a5b-2141acb51ef7" />
<img width="1920" height="1080" alt="Снимок экрана (164)" src="https://github.com/user-attachments/assets/9b0a0f8c-c0b5-48b4-bcd1-4d9c40be246e" />

){ #fig:001 width=70% }

2.Тест на тему Базовая диагностика сети  (см. рис. [@fig:002]).  

   ![Базовая диагностика сети](<img width="1920" height="1080" alt="Снимок экрана (171)" src="https://github.com/user-attachments/assets/14c91472-d380-4d04-8332-d7b9398c9061" />
<img width="1920" height="1080" alt="Снимок экрана (170)" src="https://github.com/user-attachments/assets/930f952c-1243-4682-948f-39caf8939490" />
<img width="1920" height="1080" alt="Снимок экрана (174)" src="https://github.com/user-attachments/assets/f13328db-07e5-4e0b-b3b5-91b4caa78c99" />
<img width="1920" height="1080" alt="Снимок экрана (173)" src="https://github.com/user-attachments/assets/2725adbf-7197-4ac2-afc1-1d949aef615a" />
<img width="1920" height="1080" alt="Снимок экрана (172)" src="https://github.com/user-attachments/assets/4ff74aef-827c-4768-809d-f00275eb42f2" />

){ #fig:002 width=70% }

3. Тест на тему настройка ssh доступа и его защита (см. рис. [@fig:003]).  

   ![настройка ssh доступа и его защита](<img width="1920" height="1080" alt="Снимок экрана (175)" src="https://github.com/user-attachments/assets/fe5fa94b-186f-4b69-bb71-dfe72f4d611e" />
<img width="1920" height="1080" alt="Снимок экрана (180)" src="https://github.com/user-attachments/assets/99a3260a-89cd-4731-b33a-4581e82ddf7f" />
<img width="1920" height="1080" alt="Снимок экрана (179)" src="https://github.com/user-attachments/assets/248dcf3a-4d7c-4434-8f2e-e68fba2d86fc" />
<img width="1920" height="1080" alt="Снимок экрана (178)" src="https://github.com/user-attachments/assets/85cd0723-07d2-4a1c-9ee5-40b432f6a038" />
<img width="1920" height="1080" alt="Снимок экрана (177)" src="https://github.com/user-attachments/assets/b1443212-f64b-43d4-8127-3d4c22422263" />
<img width="1920" height="1080" alt="Снимок экрана (176)" src="https://github.com/user-attachments/assets/ffbd5ced-c94b-4b77-b261-b06e7e6239db" />

){ #fig:003 width=70% }

4.  Тест на тему повышение безопаности сетевого взаимодействия (см. рис. [@fig:004]).  

   ![настройка ssh доступа и его защита](<img width="1920" height="1080" alt="Снимок экрана (183)" src="https://github.com/user-attachments/assets/7a0ab9dc-966c-4a43-83f6-396ca61001fd" />
<img width="1920" height="1080" alt="Снимок экрана (182)" src="https://github.com/user-attachments/assets/3f1d9618-66e1-465d-a195-66392019c142" />
<img width="1920" height="1080" alt="Снимок экрана (181)" src="https://github.com/user-attachments/assets/caf323ce-0ffd-49a2-99de-2a3d72075403" />
<img width="1920" height="1080" alt="Снимок экрана (186)" src="https://github.com/user-attachments/assets/1d41f33c-0de9-4090-94d8-d5242fe2d9ce" />
<img width="1920" height="1080" alt="Снимок экрана (185)" src="https://github.com/user-attachments/assets/2e9a9b82-33ff-4572-b083-09517f80ef5b" />
<img width="1920" height="1080" alt="Снимок экрана (184)" src="https://github.com/user-attachments/assets/95012633-08a3-4ba5-8c57-e1aeae6381f9" />

){ #fig:004 width=70% }

5. Тест на тему что такое пакеты и как они устроены (см. рис. [@fig:005]).  

   ![то такое пакеты и как они устроены](<img width="1920" height="1080" alt="Снимок экрана (187)" src="https://github.com/user-attachments/assets/abade5b6-ce7f-4588-a240-3bb9b55246d8" />
<img width="1920" height="1080" alt="Снимок экрана (190)" src="https://github.com/user-attachments/assets/776904b5-8c18-409a-8c48-2c18c7aa6706" />
<img width="1920" height="1080" alt="Снимок экрана (189)" src="https://github.com/user-attachments/assets/6262ef71-e4c3-4c01-bd63-5d2fadb3b2b3" />
<img width="1920" height="1080" alt="Снимок экрана (188)" src="https://github.com/user-attachments/assets/3fa67d23-3bf0-43f7-95d6-064fc4615e0d" />

){ #fig:005 width=70% }

6. Тест на тему  обновление системы и безопасность (см. рис. [@fig:006]).  

   ![ обновление системы и безопасность](<img width="1920" height="1080" alt="Снимок экрана (191)" src="https://github.com/user-attachments/assets/af6fc814-baf5-4932-b3c8-589e35e136e3" />
<img width="1920" height="1080" alt="Снимок экрана (194)" src="https://github.com/user-attachments/assets/fcb6885b-66a9-444d-a7fb-c9fc10f1f261" />
<img width="1920" height="1080" alt="Снимок экрана (193)" src="https://github.com/user-attachments/assets/281f7b16-f90c-4ebe-8518-08a6675e808b" />
<img width="1920" height="1080" alt="Снимок экрана (192)" src="https://github.com/user-attachments/assets/f09dc313-96c3-445d-bb5b-cf6acce30e1e" />
){ #fig:006 width=70% }

 
7. Тест на тему работа с зависимостями и решениями конфликтов  [@fig:007]).  

   ![работа с зависимостями и решениями конфликтов](<img width="1920" height="1080" alt="Снимок экрана (195)" src="https://github.com/user-attachments/assets/e469b359-080d-4b53-b295-59a3d654ddfc" />
<img width="1920" height="1080" alt="Снимок экрана (199)" src="https://github.com/user-attachments/assets/b75ed85b-3df4-401e-9d25-afa3d73824ea" />
<img width="1920" height="1080" alt="Снимок экрана (198)" src="https://github.com/user-attachments/assets/b7aee1fd-e982-426c-b751-43eb9a51d440" />
<img width="1920" height="1080" alt="Снимок экрана (197)" src="https://github.com/user-attachments/assets/25b929e8-274d-4576-9a01-df825feb2a40" />
<img width="1920" height="1080" alt="Снимок экрана (196)" src="https://github.com/user-attachments/assets/bb40c3e7-f16b-484f-aa93-ae2dbb96a6fa" />

){ #fig:007 width=70% }

 
8.Тест на тему работа с локальными пакетами и сторонними источниками (см. рис. [@fig:008]).  

   ![работа с локальными пакетами и сторонними источниками](<img width="1920" height="1080" alt="Снимок экрана (203)" src="https://github.com/user-attachments/assets/e859743a-4273-444f-ba27-91ae1e745542" />
<img width="1920" height="1080" alt="Снимок экрана (202)" src="https://github.com/user-attachments/assets/6a85d9a7-a947-4850-ae17-07375f75490c" />
<img width="1920" height="1080" alt="Снимок экрана (201)" src="https://github.com/user-attachments/assets/d475934c-6806-47f6-bb0b-c6918292682b" />
<img width="1920" height="1080" alt="Снимок экрана (200)" src="https://github.com/user-attachments/assets/9c9d213c-5f3a-4ce4-bf52-7666087ab02b" />

){ #fig:008 width=70% }

9. Тест на тему Знакомство с логами<img width="1920" height="1080" alt="Снимок экрана (207)" src="https://github.com/user-attachments/assets/8eaa28a8-c051-4817-8350-1cee3024af15" />
<img width="1920" height="1080" alt="Снимок экрана (206)" src="https://github.com/user-attachments/assets/e43d000d-fe9f-41ac-b12d-ff201ec0c07f" />
<img width="1920" height="1080" alt="Снимок экрана (205)" src="https://github.com/user-attachments/assets/d4e211a8-6620-4556-a342-89fd8deb156f" />
 (см. рис. [@fig:009]).  

   ![ ](<img width="1920" height="1080" alt="Снимок экрана (204)" src="https://github.com/user-attachments/assets/6187c79f-dce2-4866-9cbf-74a865481bb5" />

){ #fig:009 width=70% }

10. Тест на тему система логирования  (см. рис. [@fig:010]).  

   ![система логирования ](<img width="1920" height="1080" alt="Снимок экрана (211)" src="https://github.com/user-attachments/assets/f99b4ee2-5346-41ee-9ac6-4fa3b1b5f5a7" />
<img width="1920" height="1080" alt="Снимок экрана (210)" src="https://github.com/user-attachments/assets/861d2c25-ead2-4aa1-9450-ee042cba21af" />
<img width="1920" height="1080" alt="Снимок экрана (209)" src="https://github.com/user-attachments/assets/7c1c1976-a561-4e5e-81e7-45b8ba3fb140" />
<img width="1920" height="1080" alt="Снимок экрана (208)" src="https://github.com/user-attachments/assets/3c510ccd-4f18-408c-816b-3c018152e738" />

){ #fig:010 width=70% }

11.Тест на тему поиск и фильтрация логов под конкретные задачи  (см. рис. [@fig:011]).  

   ![поиск и фильтрация логов под конкретные задачи ](<img width="1920" height="1080" alt="Снимок экрана (215)" src="https://github.com/user-attachments/assets/4cd3c0da-e40e-4c67-8828-ae1472efab85" />
<img width="1920" height="1080" alt="Снимок экрана (214)" src="https://github.com/user-attachments/assets/5a312571-8fda-43b8-89cc-567e1a53f1f1" />
<img width="1920" height="1080" alt="Снимок экрана (213)" src="https://github.com/user-attachments/assets/c631d008-51a6-4dca-8b3c-1c5b1e80bbb7" />
<img width="1920" height="1080" alt="Снимок экрана (212)" src="https://github.com/user-attachments/assets/08a106f2-556a-4caf-932d-78c49fa564a4" />
) 
){ #fig:011 width=70% }

  
12.Тест на тему расследование инцидентов по логам (см. рис. [@fig:012]).  

   ![расследование инцидентов по логам](<img width="1920" height="1080" alt="Снимок экрана (219)" src="https://github.com/user-attachments/assets/727b61a2-7bbf-427a-9930-161b3d125988" />
<img width="1920" height="1080" alt="Снимок экрана (218)" src="https://github.com/user-attachments/assets/7a546295-375c-4b1f-9e38-0add9f3c50a6" />
<img width="1920" height="1080" alt="Снимок экрана (217)" src="https://github.com/user-attachments/assets/ad2a3c31-fc89-438c-9540-fa0b89e2c005" />
<img width="1920" height="1080" alt="Снимок экрана (216)" src="https://github.com/user-attachments/assets/ad4b8380-8e96-4ea2-af6e-d313b9653eb0" />

){ #fig:012 width=70% }

13. Тест на тему управление жизненними циклами логов и ротация  (см. рис. [@fig:013]).  

   ![управление жизненними циклами логов и ротация](<img width="1920" height="1080" alt="Снимок экрана (223)" src="https://github.com/user-attachments/assets/0fc16711-fb55-42c3-9fff-335d7c6ed6a8" />
<img width="1920" height="1080" alt="Снимок экрана (222)" src="https://github.com/user-attachments/assets/4d6b49fe-f1c6-40e7-860f-a48f17756d7a" />
<img width="1920" height="1080" alt="Снимок экрана (221)" src="https://github.com/user-attachments/assets/4d678f88-97c3-4f81-9783-898346cb0989" />
<img width="1920" height="1080" alt="Снимок экрана (220)" src="https://github.com/user-attachments/assets/4c055269-f51b-4fb8-b61e-0b29b99ffcd0" />

){ #fig:013 width=70% }

14. Тест на тему контейниризация как подход (см. рис. [@fig:0014]).  

   ![контейниризация как подход  ](<img width="1920" height="1080" alt="Снимок экрана (229)" src="https://github.com/user-attachments/assets/583f2ac2-1c50-438e-be18-38b382ea543a" />
<img width="1920" height="1080" alt="Снимок экрана (228)" src="https://github.com/user-attachments/assets/172cfa56-bf5f-4d22-ab3a-e64d8a573c84" />
<img width="1920" height="1080" alt="Снимок экрана (227)" src="https://github.com/user-attachments/assets/f8bcabe1-86b7-4991-9516-9c048545cad3" />
<img width="1920" height="1080" alt="Снимок экрана (226)" src="https://github.com/user-attachments/assets/3d379b60-694b-46e2-9b03-73815d756b77" />
<img width="1920" height="1080" alt="Снимок экрана (225)" src="https://github.com/user-attachments/assets/122d11b3-e090-4bb1-a274-a07a409bc0c8" />
<img width="1920" height="1080" alt="Снимок экрана (224)" src="https://github.com/user-attachments/assets/1443d709-db4a-4b5c-927b-8dae1e9c3a46" />

){ #fig:014 width=70% }

15. Тест на тему работа с контейнерами в podman  (см. рис. [@fig:0015]).  

   ![работа с контейнерами в podman](<img width="1920" height="1080" alt="Снимок экрана (235)" src="https://github.com/user-attachments/assets/25392dd3-1d40-44e2-a7a8-e1a2f03f6bd6" />
<img width="1920" height="1080" alt="Снимок экрана (234)" src="https://github.com/user-attachments/assets/a9284a9a-d69f-4ab0-be38-ceadbcfd9587" />
<img width="1920" height="1080" alt="Снимок экрана (233)" src="https://github.com/user-attachments/assets/3df9e7cb-3456-4bf8-94cf-7d42799a9509" />
<img width="1920" height="1080" alt="Снимок экрана (232)" src="https://github.com/user-attachments/assets/bc2ade3c-f529-4a02-8a08-9aa38b3e75fa" />
<img width="1920" height="1080" alt="Снимок экрана (231)" src="https://github.com/user-attachments/assets/1c4d798d-bcb3-49eb-a80c-582d07ac7dbb" />
<img width="1920" height="1080" alt="Снимок экрана (230)" src="https://github.com/user-attachments/assets/73a4e786-89b9-4925-8cda-b2182aca911a" />

){ #fig:015 width=70% }

16.  Тест на тему управление ресурсами контейнеров (см. рис. [@fig:016]).  

   ![управление ресурсами контейнеров](<img width="1920" height="1080" alt="Снимок экрана (241)" src="https://github.com/user-attachments/assets/59f14413-0533-4123-83b3-458abc1ee226" />
<img width="1920" height="1080" alt="Снимок экрана (240)" src="https://github.com/user-attachments/assets/7316d46c-78b7-4628-8318-9eb981167dd1" />
<img width="1920" height="1080" alt="Снимок экрана (239)" src="https://github.com/user-attachments/assets/a69b5f4f-6413-413e-90b1-af4a436f2920" />
<img width="1920" height="1080" alt="Снимок экрана (238)" src="https://github.com/user-attachments/assets/448eb7a8-196f-412c-be52-9858bfdeedea" />
<img width="1920" height="1080" alt="Снимок экрана (237)" src="https://github.com/user-attachments/assets/c95f01c9-4825-4e3e-9236-7dc814629438" />
<img width="1920" height="1080" alt="Снимок экрана (236)" src="https://github.com/user-attachments/assets/ebc666f3-2d36-415e-8074-8bf8faf73616" />

){ #fig:016 width=70% }

17. Тест на тему образы реестры и базовая безопасность  (см. рис. [@fig:017]).  

   ![ образы реестры и базовая безопасность](<img width="1920" height="1080" alt="Снимок экрана (246)" src="https://github.com/user-attachments/assets/3e86e19a-0858-403a-8f82-d789c42757b5" />
<img width="1920" height="1080" alt="Снимок экрана (245)" src="https://github.com/user-attachments/assets/311e167a-0dbf-4791-8e41-796e0f9ca5e9" />
<img width="1920" height="1080" alt="Снимок экрана (244)" src="https://github.com/user-attachments/assets/ecb70cfa-891f-46a7-8815-9c0257e5805c" />

){ #fig:017 width=70% }


# Заключение

В ходе прохождения курса Системный администратор Linux с нуля были изучены основные принципы работы Linux.  
В результате работы получены практические навыки администрирования и конфигурирования Linux.


