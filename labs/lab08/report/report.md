---
## Front matter
title: "Отчёт по лабораторной работе 8"
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

Целью работы является приобретение навыков написания программ с использованием циклов и обработкой аргументов командной строки..

# Выполнение лабораторной работы

## Реализация циклов в NASM

Создал каталог для программ лабораторной работы №8 и файл lab8-1.asm (рис. [-@fig:001]).

![Создан каталог](image/01.png){ #fig:001 width=70%, height=70% }

При реализации циклов в NASM с использованием инструкции loop необходимо помнить, что эта инструкция использует регистр ecx в качестве счетчика и на каждом шаге уменьшает его значение на единицу. В качестве примера рассмотрим программу, которая выводит значение регистра ecx.

Записал в файл lab8-1.asm текст программы из листинга 8.1 (рис. [-@fig:002]). Создал исполняемый файл и проверил его работу (рис. [-@fig:003]).

![Программа lab8-1.asm](image/02.png){ #fig:002 width=70%, height=70% }

![Запуск программы lab8-1.asm](image/03.png){ #fig:003 width=70%, height=70% }

Данный пример демонстрирует, что изменение значения регистра ecx в теле цикла loop может привести к некорректной работе программы. Изменил текст программы, добавив изменение значения регистра ecx в цикле (рис. [-@fig:004]). Программа запускает бесконечный цикл при нечетном N и выводит только нечетные числа при четном N (рис. [-@fig:005]).

![Программа lab8-1.asm](image/04.png){ #fig:004 width=70%, height=70% }

![Запуск программы lab8-1.asm](image/05.png){ #fig:005 width=70%, height=70% }

Для корректного использования регистра ecx в цикле можно использовать стек. Внес изменения в текст программы, добавив команды push и pop для сохранения и восстановления значения счетчика цикла loop (рис. [-@fig:006]). Создал исполняемый файл и проверил его работу (рис. [-@fig:007]). Программа корректно выводит числа от N-1 до 0, при этом число проходов цикла соответствует N.

![Программа lab8-1.asm](image/06.png){ #fig:006 width=70%, height=70% }

![Запуск программы lab8-1.asm](image/07.png){ #fig:007 width=70%, height=70% }

Создал файл lab8-2.asm в каталоге ~/work/arch-pc/lab08 и записал в него текст программы из листинга 8.2 (рис. [-@fig:008]). Скомпилировал исполняемый файл и запустил его с указанием аргументов. Программа обработала 4 аргумента — слова или числа, разделенные пробелом (рис. [-@fig:009]).

![Программа lab8-2.asm](image/08.png){ #fig:008 width=70%, height=70% }

![Запуск программы lab8-2.asm](image/09.png){ #fig:009 width=70%, height=70% }

Рассмотрел пример программы, которая вычисляет сумму чисел, переданных в программу в качестве аргументов (рис. [-@fig:010], рис. [-@fig:011]).

![Программа lab8-3.asm](image/10.png){ #fig:010 width=70%, height=70% }

![Запуск программы lab8-3.asm](image/11.png){ #fig:011 width=70%, height=70% }

Изменил текст программы из листинга 8.3 для вычисления произведения аргументов командной строки (рис. [-@fig:012], рис. [-@fig:013]).

![Программа lab8-3.asm](image/12.png){ #fig:012 width=70%, height=70% }

![Запуск программы lab8-3.asm](image/13.png){ #fig:013 width=70%, height=70% }

## Самостоятельное задание

Написал программу, которая вычисляет сумму значений функции $f(x)$ для $x = x_1, x_2, ..., x_n$, где значения $x$ передаются как аргументы. Функция $f(x)$ выбрана из таблицы 8.1 
в соответствии с вариантом 6: $$f(x) = 4x - 3.$$ Программа корректно работает, выводя сумму значений $f(x_1) + f(x_2) + ... + f(x_n)$. Создал исполняемый файл и проверил его работу на нескольких наборах $x$ (рис. [-@fig:014], рис. [-@fig:015]).

![Программа lab8-prog.asm](image/14.png){ #fig:014 width=70%, height=70% }

![Запуск программы lab8-prog.asm](image/15.png){ #fig:015 width=70%, height=70% }

Программа правильно считает, например, $f(1) = 1$, $f(2) = 5$.

# Выводы

В ходе работы освоил использование стека, инструкции loop и работу с аргументами командной строки в языке ассемблера NASM.
