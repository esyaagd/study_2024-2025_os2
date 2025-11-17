---
## Front matter
title: "Отчёт по внешнему курсу часть 1"
subtitle: "Системный администратор Linux с нуля"
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

Выполнить курс Системный администратор Linux с нуля.

# Ход выполнения работы

## Часть 1

1. Тест по теме роль системного адмистратора Linux. (см. рис. [@fig:001]).  

   ![Что относится к философии свободного ПО?](<img width="1920" height="1080" alt="Снимок экрана (63)" src="https://github.com/user-attachments/assets/af80c485-903c-463c-af81-af40901d1bff" />
){ #fig:001 width=70% }


2.  Тест по теме роль системного адмистратора Linux.см .рис. [@fig:002]).
   ![Инструмент для мониторинга серверов](<img width="1920" height="1080" alt="7665b0def2d9ca7df64a9a97994ed037_%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20(64)" src="https://github.com/user-attachments/assets/9601d4fd-7ed6-46e3-ac77-b36394fa7072" />
){ #fig:002 width=70% }

3. Тест по теме роль системного адмистратора Linux. (см. рис. [@fig:003]).  

   ![Ключевые обязаности системного администратора](<img width="1920" height="1080" alt="Снимок экрана (65)" src="https://github.com/user-attachments/assets/bb70d4b4-53b4-415f-a6c1-3b6dad097196" />
){ #fig:003 width=70% }

4. Тест по теме роль системного адмистратора Linux. (см. рис. [@fig:004]).  

   ![Результат](<img width="1920" height="1080" alt="Снимок экрана (66)" src="https://github.com/user-attachments/assets/0905a92b-ed94-4b45-aa17-00f7b9fadd22" />
){ #fig:004 width=70% }

5. Тест по теме вводный урок.  (см. рис. [@fig:005]).  

   ![Самая популярная оболочка](<img width="1920" height="1080" alt="Снимок экрана (67)" src="https://github.com/user-attachments/assets/46c5a047-7054-424b-90c0-8c53f1afc38a" />
){ #fig:005 width=70% }

6.  Тест по теме вводный урок. (см. рис. [@fig:006]).  

   ![Повышении привелегии](<img width="1920" height="1080" alt="Снимок экрана (68)" src="https://github.com/user-attachments/assets/5bb1764d-b5a9-4004-8e44-77399943c19e" />
){ #fig:006 width=70% }


7. Тест по теме ввводный урок. (см. рис. [@fig:007]).  

   ![Команда выводит справочную информацию](<img width="1920" height="1080" alt="Снимок экрана (69)" src="https://github.com/user-attachments/assets/86edfb8f-ae99-4df9-b10b-6ea40370b093" />
){ #fig:007 width=70% }

8. Тест по теме ввводный урок. (см. рис. [@fig:008]).  

   ![Результат](<img width="1920" height="1080" alt="Снимок экрана (70)" src="https://github.com/user-attachments/assets/1b5647b4-8008-4fe6-ad7d-b86bbd209af0" />
){ #fig:008 width=70% }

9.Тест по теме роль командной стоки в серверной среде. (см. рис. [@fig:009]).  

   ![](<img width="1920" height="1080" alt="Снимок экрана (71)" src="https://github.com/user-attachments/assets/a10c8fc9-4da9-4e78-a4a3-1ebca16e5593" />
){ #fig:009 width=70% }
  
10. Тест по теме роль командной стоки в серверной среде. (см. рис. [@fig:010]).  

   ![Тест по теме роль командной стоки в серверной среде.](<img width="1920" height="1080" alt="Снимок экрана (72)" src="https://github.com/user-attachments/assets/410e13cd-e68d-4f3e-a9d8-7ec2534c9ef6" />
){ #fig:010 width=70% }

11. Тест по теме роль командной стоки в серверной среде. (см. рис. [@fig:011]).  

   ![Тест по теме роль командной стоки в серверной среде.](<img width="1920" height="1080" alt="Снимок экрана (73)" src="https://github.com/user-attachments/assets/ad35d5b8-08df-4a91-9641-4ac3105889f2" />

){ #fig:011 width=70% }


12. Тест по теме роль командной стоки в серверной среде. см .рис. [@fig:012]).
   ![Тест по теме роль командной стоки в серверной среде.](<img width="1920" height="1080" alt="Снимок экрана (74)" src="https://github.com/user-attachments/assets/1dddcba9-3c3b-432f-b7dc-d3a6369e3a30" />

){ #fig:012 width=70% }

13. Тест по теме файловая структура и ключевые каталоги. (см. рис. [@fig:013]).  

   ![Тест по теме файловая структура и ключевые каталоги.](<img width="1920" height="1080" alt="Снимок экрана (75)" src="https://github.com/user-attachments/assets/db9f49ba-b072-44e7-a561-9cf314ac7759" />

){ #fig:013 width=70% }

14. Тест по теме файловая структура и ключевые каталоги. (см. рис. [@fig:014]).  

   ![](<img width="1920" height="1080" alt="Снимок экрана (76)" src="https://github.com/user-attachments/assets/98d67c09-d278-47cd-88e3-6bb39a1d68ec" />

){ #fig:014 width=70% }

15.  Тест по теме файловая структура и ключевые каталоги.  (см. рис. [@fig:015]).  

   ![](<img width="1920" height="1080" alt="Снимок экрана (77)" src="https://github.com/user-attachments/assets/c2199d72-5944-4d75-8f8a-8309fc107505" />

){ #fig:015 width=70% }

16.  Тест по теме файловая структура и ключевые каталоги. (см. рис. [@fig:016]).  

   ![Результат](<img width="1920" height="1080" alt="Снимок экрана (78)" src="https://github.com/user-attachments/assets/1723f80b-e8f9-4194-8607-a06a9efecdea" />

){ #fig:016 width=70% }


17.Тест по теме Принцип Все есть файл (см. рис. [@fig:017]).  

   ![Тест по теме Принцип Все есть файл](<img width="1920" height="1080" alt="Снимок экрана (79)" src="https://github.com/user-attachments/assets/6c1c03c0-a27d-45a9-930f-2c96f84af005" />

){ #fig:017 width=70% }

18. Тест по теме Принцип Все есть файл (см. рис. [@fig:018]).  

   ![Тест по теме Принцип Все есть файл](<img width="1920" height="1080" alt="Снимок экрана (80)" src="https://github.com/user-attachments/assets/25d2fe2e-ea09-4b8f-bca3-fd1ec11af0b9" />

){ #fig:018 width=70% }

19.Тест по теме Принцип Все есть файл (см. рис. [@fig:019]).  

   ![ Принцип Все есть файл](<img width="1920" height="1080" alt="Снимок экрана (81)" src="https://github.com/user-attachments/assets/df367b5c-ae2b-46bf-aa57-0da7a8b183e5" />

){ #fig:019 width=70% }
  
20. Тест по теме роль командной стоки в серверной среде. (см. рис. [@fig:020]).  

   ![Результат](<img width="1920" height="1080" alt="Снимок экрана (82)" src="https://github.com/user-attachments/assets/b72e88a8-b91c-4f44-8d65-5b7d20adea17" />

){ #fig:020 width=70% }

21. Тест по теме Работа с базовымы командами в реальных условиях. (см. рис. [@fig:021]).  

   ![Работа с базовымы командами в реальных условиях](<img width="1920" height="1080" alt="Снимок экрана (83)" src="https://github.com/user-attachments/assets/c0a7dca4-5265-414c-b511-cee403886980" />

){ #fig:021 width=70% }


22.  Тест по теме Работа с базовымы командами в реальных условиях. .рис. [@fig:022]).
   ![ Работа с базовымы командами в реальных условиях](<img width="1920" height="1080" alt="Снимок экрана (84)" src="https://github.com/user-attachments/assets/edcf4b48-9f7e-4c8e-9e96-5f5e65b6ee77" />

){ #fig:022 width=70% }

23. Тест по теме Работа с базовымы командами в реальных условиях. (см. рис. [@fig:023]).  

   ![ Работа с базовымы командами в реальных условиях.](<img width="1920" height="1080" alt="Снимок экрана (85)" src="https://github.com/user-attachments/assets/de20ae84-2fff-49bf-b5e9-280356ddd478" />

){ #fig:023 width=70% }

24. Тест по теме Работа с базовымы командами в реальных условиях. (см. рис. [@fig:024]).  

   ![ Работа с базовымы командами в реальных условиях.](<img width="1920" height="1080" alt="Снимок экрана (86)" src="https://github.com/user-attachments/assets/6f5f7465-33c8-4098-ad6e-bf0acf8d2b68" />

){ #fig:024 width=70% }

25.  Тест по теме Работа с базовымы командами в реальных условиях.  (см. рис. [@fig:025]).  

   ![ Работа с базовымы командами в реальных условиях. ](<img width="1920" height="1080" alt="Снимок экрана (87)" src="https://github.com/user-attachments/assets/2951eec1-5244-4f84-9eb0-c5ebdae585a3" />

){ #fig:025 width=70% }

26.  Тест по теме Работа с базовымы командами в реальных условиях. (см. рис. [@fig:026]).  

   ![ Работа с базовымы командами в реальных условиях.](<img width="1920" height="1080" alt="Снимок экрана (88)" src="https://github.com/user-attachments/assets/b2a13db2-2d13-453f-a267-a34d6660583e" />

){ #fig:026 width=70% }


27. Тест по теме Работа с архивами и передачей данных с серверами. (см. рис. [@fig:027]).  

   ![Работа с архивами и передачей данных с серверами](<img width="1920" height="1080" alt="Снимок экрана (89)" src="https://github.com/user-attachments/assets/a56da1cd-d026-4a65-87e3-0646317cb555" />

){ #fig:027 width=70% }

28. Тест по теме Работа с архивами и передачей данных с серверами. (см. рис. [@fig:028]).  

   ![Работа с архивами и передачей данных с серверами.](<img width="1920" height="1080" alt="Снимок экрана (90)" src="https://github.com/user-attachments/assets/1720d6f0-4b2d-4879-a17e-07d238d8ac3e" />

){ #fig:028 width=70% }

29.Тест по теме Работа с архивами и передачей данных с серверами. (см. рис. [@fig:029]).  

   ![ Работа с архивами и передачей данных с серверами](<img width="1920" height="1080" alt="Снимок экрана (91)" src="https://github.com/user-attachments/assets/6bcf2bdb-1ee8-46b0-945b-b35bee1f19af" />

){ #fig:029 width=70% }
  
30. Тест по теме Работа с архивами и передачей данных с серверами. (см. рис. [@fig:030]).  

   ![Работа с архивами и передачей данных с серверами](<img width="1920" height="1080" alt="Снимок экрана (92)" src="https://github.com/user-attachments/assets/ca83f901-29ce-48ed-b1d8-0e15a8764755" />


){ #fig:030 width=70% }

31. Тест по теме основы автоматизации с помощью Bash-скриптов. (см. рис. [@fig:031]).  

   ![Тест по теме основы автоматизации с помощью скриптов.](<img width="1920" height="1080" alt="Снимок экрана (93)" src="https://github.com/user-attachments/assets/4b606eb7-c307-46b6-bec0-35289b0eb715" />


){ #fig:031 width=70% }


32. Тест по теме основы автоматизации с помощью Bash-скриптов. см .рис. [@fig:032]).
   ![ основы автоматизации с помощью Bash-скриптов.](<img width="1920" height="1080" alt="Снимок экрана (94)" src="https://github.com/user-attachments/assets/bf5b5903-49e6-453f-b68f-f36031d8f6b3" />


){ #fig:032 width=70% }

33. Тест по теме основы автоматизации с помощью Bash-скриптов. (см. рис. [@fig:033]).  

   ![основы автоматизации с помощью Bash-скриптов.](<img width="1920" height="1080" alt="Снимок экрана (95)" src="https://github.com/user-attachments/assets/3a1fc4b5-1694-42ad-b8ea-5b78447af3a3" />


){ #fig:033 width=70% }

34. Тест по теме основы автоматизации с помощью Bash-скриптов. (см. рис. [@fig:034]).  

   ![Результат](<img width="1920" height="1080" alt="Снимок экрана (96)" src="https://github.com/user-attachments/assets/167a422d-b94e-416a-864b-e96950d15a6d" />


){ #fig:034 width=70% }


# Заключение

В ходе выполнения 1 части курса Системный администратор Linux с нулябыли изучены основные принципы работы Linux
В результате работы получены практические навыки администрирования и конфигурирования Linux, необходимых для обеспечения безопасности и стабильности работы системы.
