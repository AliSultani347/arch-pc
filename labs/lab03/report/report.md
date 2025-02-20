---
## Front matter
title: "Отчёт по лабораторной работе 3"
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

Целью работы является освоение процедуры оформления отчетов с помощью легковесного языка разметки Markdown.

# Теоретическое введение

## Базовые сведения о Markdown

**Markdown** — это лёгкий язык разметки, который используется для форматирования текста. Он преобразуется в различные форматы, такие как HTML, PDF и другие. В основе Markdown лежат простые символы, которые задают стиль текста без использования сложных тегов.

# Выполнение лабораторной работы

## Знакомство с Markdown

В процессе выполнения лабораторной работы установил необходимые программы: `pandoc` и `TexLive`, как было указано в инструкциях.

Перешел в каталог курса, созданный в ходе выполнения лабораторной работы №3, затем в директорию с шаблоном отчета по лабораторной работе №3.

Для компиляции шаблона использовал `Makefile`, выполнив команду `make`. (рис. [-@fig:001])

Создание PDF-файла с первого раза не удалось, так как потребовалась установка дополнительных шрифтов.

![Компиляция шаблона с использованием Makefile](image/01.png){ #fig:001 width=70%, height=70% }

После успешной компиляции были сгенерированы файлы `report.pdf` (рис. [-@fig:003]) и `report.docx` (рис. [-@fig:002]), что я проверил.

![Файл report.docx](image/02.png){ #fig:002 width=70%, height=70% }

![Файл report.pdf](image/03.png){ #fig:003 width=70%, height=70% }

Затем с помощью команды `make clean` удалил сгенерированные файлы. После выполнения команды убедился, что файлы `report.pdf` и `report.docx` были удалены. (рис. [-@fig:004])

![Удаление файлов report.docx и report.pdf](image/04.png){ #fig:004 width=70%, height=70% }

Открыл файл `report.md` в текстовом редакторе, например, `gedit`, и внимательно изучил его структуру. (рис. [-@fig:005])

![Открытие шаблона отчета](image/05.png){ #fig:005 width=70%, height=70% }

После изучения структуры заполнил отчет. (рис. [-@fig:006])

![Заполнение шаблона отчета](image/06.png){ #fig:006 width=70%, height=70% }

## Задание для самостоятельной работы

В рамках самостоятельной работы заполнил отчет для лабораторной работы №2, как это было указано в задании. (рис. [-@fig:007])

![Заполнение шаблона для второй лабораторной работы](image/07.png){ #fig:007 width=70%, height=70% }

Экспортировал файлы отчета в форматы для загрузки. (рис. [-@fig:008])

![Экспорт отчетных файлов](image/08.png){ #fig:008 width=70%, height=70% }

# Выводы

Изучили синтаксис языка разметки Markdown, получили отчет из шаблона при помощи Makefile. 

# Список литературы{.unnumbered}

1. Архитектура ЭВМ - Материалы курса

2. Markdown Документация
