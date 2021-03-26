---
# Front matter
lang: ru-RU
title: "Лабораторная работа №7 по математическому моделированию"
subtitle: "Эффективность рекламы "
author: "Хусайнова Фароиз Дилшодовна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Ознакомиться с моделью Мальтуса и моделью логистической кривой на примере рекламной кампании и построить их с помощью языка программирования Modelica.

# Задание

Построить график распространения рекламы, математическая модель которой описывается следующим уравнением:

1. $\frac{dn}{dt} = (0.84+0.00022n(t))(N-n(t))$
2. $\frac{dn}{dt} = (0.000022+0.74n(t))(N−n(t))$
3. $\frac{dn}{dt} = (0.74sin⁡(t)+0.35cos(t)n(t))(N−n(t))$

При этом объем аудитории $N$ = 1005, в начальный момент о товаре знает 11 человек.
Для случая 2 определите в какой момент времени скорость распространения рекламы будет иметь максимальное значение.

# Выполнение лабораторной работы

Организуется рекламная кампания нового товара или  услуги.  Необходимо, чтобы  прибыль  будущих  продаж  с  избытком  покрывала  издержки  на  рекламу. 
Вначале  расходы  могут  превышать  прибыль,  поскольку  лишь  малая  часть потенциальных покупателей  будет  информирована  о  новинке.  
Затем,  при увеличении  числа  продаж,  возрастает  и  прибыль,  и,  наконец,  наступит  момент, когда рынок насытиться, и рекламировать товар станет бесполезным.
Предположим,  что  торговыми  учреждениями  реализуется  некоторая продукция, о которой в момент времени t из числа потенциальных покупателей $N$ знает лишь $n$ покупателей. 

Математическая модель распространения рекламы описывается уравнением:

$$ \frac{\partial n}{\partial t} = (\alpha_1(t) + \alpha_2(t)n(t))(N - n(t))$$

1. Построим график распространения рекламы, математическая модель которой описывается следующим уравнением: $\frac{dn}{dt} = (0.84+0.00022n(t))(N-n(t))$ (рис -@fig:001)  

![График для первого случая](images/1.PNG){ #fig:001 width=70% }

2. График распространения рекламы, математическая модель которой описывается следующим уравнением: $\frac{dn}{dt} = (0.000022+0.74n(t))(N-n(t))$ (рис -@fig:002)  

![График для второго случая](images/2.PNG){ #fig:002 width=70% }

Необходимо определить, каким будет максимальное значение скорости распространения рекламы в данном случае. Скорость распространения рекламы - производная по графику распространения рекламы.
Следовательно, максимальное значение будет там, где значение графика скорости максимально. По данному графику видно, что максимальное значение при t~0~ = 0. (рис. @fig:003)

![Максимальное значение скорости распространения рекламы](images/3.PNG){ #fig:003 width=70% }

3. График распространения рекламы, математическая модель которой описывается следующим уравнением: $\frac{dn}{dt} = (0,74sin⁡(t)+0,35cos(t)n(t))(N-n(t))$ (рис. -@fig:004)  

![График для третьего случая](images/4.PNG){ #fig:004 width=70% }

# Ответы на вопросы к лабораторной работе

1. Записать модель Мальтуса (дать пояснение, где используется данная модель)

$$ \frac{\partial N}{\partial t} = rN $$

Модель используется в экологии для расчета изменений популяции особей животных.

2. Записать уравнение логистической кривой (дать пояснение, что описывает данное уравнение)

$$ \frac{\partial P}{\partial t} = rP(1 - \frac{P}{K}) $$

Исходные предположения для вывода уравнения при рассмотрении популяционной динамики выглядят следующим образом:

- скорость размножения популяции пропорциональна её текущей численности, при прочих равных условиях;
- скорость размножения популяции пропорциональна количеству доступных ресурсов, при прочих равных условиях. Таким образом, второй член уравнения отражает конкуренцию за ресурсы, которая ограничивает рост популяции.

3. На что влияет коэффициент $\alpha_1(t)$ и $\alpha_2(t)$ в модели распространения рекламы
$\alpha_1(t)$ — интенсивность рекламной кампании, зависящая от затрат

$\alpha_2(t)$ — интенсивность рекламной кампании, зависящая от сарафанного радио

4. Как ведет себя рассматриваемая модель при $\alpha_1(t) \gg \alpha_2(t)$
При $\alpha_1(t) \gg \alpha_2(t)$ получается модель типа модели Мальтуса (рис. -@fig:005)

![График решения уравнения модели Мальтуса](images/1.PNG){ #fig:005 width=70% }

5. Как ведет себя рассматриваемая модель при $\alpha_1(t) \ll \alpha_2(t)$
При $\alpha_1(t) \ll \alpha_2(t)$ получаем уравнение логистической кривой (рис. -@fig:006)

![График логистической кривой](images/2.PNG){ #fig:006 width=70% }

# Выводы

1. Ознакомилась с моделью Мальтуса и моделью логистической кривой на примере эффективности рекламы. 
2. Построила графики для трех случаев.