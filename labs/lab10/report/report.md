---
## Front matter
title: "Отчёт по лабораторной работе 10"
subtitle: "Архитектура компьютеров"
author: "Султани Али НКАбд-06-24"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью работы является приобретение навыков написания программ для работы с файлами.

# Выполнение лабораторной работы

Создал каталог для программ лабораторной работы №10, перешел в него и создал файлы lab10-1.asm, readme-1.txt и readme-2.txt.

Добавил в файл lab10-1.asm текст программы из листинга 10.1 (программа записи сообщения в файл). Скомпилировал программу, создал исполняемый файл и проверил его работу.

![Код программы lab10-1.asm](image/01.png){ #fig:001 width=70%, height=70% }

Программа запрашивает строку у пользователя и записывает её в файл readme.txt. Если файл отсутствует, сообщение не сохраняется.

![Результат выполнения программы lab10-1.asm](image/02.png){ #fig:002 width=70%, height=70% }

Изменил права доступа к исполняемому файлу lab10-1 с помощью команды chmod, запретив его выполнение. Попытался запустить файл.

Файл не выполняется, так как были удалены права на выполнение (атрибут x снят для всех пользователей).

![Файл с запрещенным запуском](image/03.png){ #fig:003 width=70%, height=70% }

С помощью команды chmod добавил права на выполнение файла lab10-1.asm, содержащего текст программы. Попытался выполнить его.

Терминал воспринимает содержимое файла как набор консольных команд. Так как инструкции ассемблера не являются командами, появляются ошибки. Если в файл записать команды терминала, его можно будет выполнить.

![Запуск asm-файла с правами выполнения](image/04.png){ #fig:004 width=70%, height=70% }

Установил права доступа к файлам readme в соответствии с вариантом в таблице 10.4. Проверил результат с помощью команды ls -l.

Для варианта 6: права доступа -w- r-x -w-  и в восьмеричном представлении 011 001 111.

![Изменение прав доступа](image/05.png){ #fig:005 width=70%, height=70% }

## Задание для самостоятельной работы

Написал программу, реализующую следующий алгоритм:

1. Вывод приглашения: "Как Вас зовут?".
2. Ввод фамилии и имени с клавиатуры.
3. Создание файла name.txt.
4. Запись в файл сообщения: "Меня зовут".
5. Дополнение файла введённой строкой.
6. Закрытие файла.

![Код программы lab10-2.asm](image/06.png){ #fig:006 width=70%, height=70% }

![Результат выполнения программы lab10-2.asm](image/07.png){ #fig:007 width=70%, height=70% }

# Выводы

Научился работать с файлами и изменять права доступа. 
