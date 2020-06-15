# Билет 1
## Компоненты сильной связности
![Screenshot](../algo_data/ticket_1_1.png)

##### [Более подробное обьяснение](https://e-maxx.ru/algo/strong_connected_components)

# Билет 2
- Эйлеров путь -  путь, который проходит по каждому ребру графа, причем ровно один раз
- Эйлеров цикл - замкнутый эйлеров путь
- Граф эйлеров, если все вершины графа имеют четную степень, если же граф ориентированный, то его эйлеровость определяется равенством входящих и исходящих ребер каждой вершины

![Доказательство](../algo_data/ticket_2_1.png)

##### [Ссылка на еще одно более подробное доказательство](http://neerc.ifmo.ru/wiki/index.php?title=%D0%AD%D0%B9%D0%BB%D0%B5%D1%80%D0%BE%D0%B2%D0%BE%D1%81%D1%82%D1%8C_%D0%B3%D1%80%D0%B0%D1%84%D0%BE%D0%B2)

## Построение Эйлерова цикла


![Построение](../algo_data/ticket_2_2.png)


- Для ориентированного случая делаем 
все то же самое, только теперь ребра не нужно удалять, все хранить можно в ```vector<vector<Edge>>```
# Билет 3
##  Определения
- Ребро (a, b) называется **мостом**, если после его удаления a и b не связны.
- **Точка сочленения** – вершина, при удалении которой увеличивается число ком- понент связности.
## Мосты
- Замечание:  После удаления из графа мостов, компоненты связности и рёберной двусвязности будут совпадать. Доказательство: ((𝑎, 𝑏) – не мост) ⇔ (𝑎 и 𝑏 рёберно двусвязны).
### Алгоритмы поиска мостов


![Алгоритмы поиска мостов](../algo_data/points_1.png)
## Точки сочленения 

- Замечание: точки сочленения – ровно те вершины, у которых есть смежные рёбра из разных компонент вершинной двусвязности.
- Два ребра называют **вершинно двусвязными**, если существуют вершинно непересекающиеся пути, соединяющие их концы.

### Алгоритмы поиска

![Алгоритмы поиска точек сочленения](../algo_data/ticket_3_2.png)

- Доказательство корректности, которого почему-то нет в конспекте:


![Доказательство](../algo_data/ticket_3_3.png)



# Билет 4
## Двусвязность определения через отношение эквивалентности
### Реберная
![Определение и теорема](../algo_data/ticket_4_1.png)
### Вершинная
![Определение и теорема](../algo_data/ticket_4_2.png)
## Алгоритм поска компонент вершинной двусвязности 
![Алгоритмы поиска точек сочленения](../algo_data/ticket_3_2.png)

# Билет 5
## 2-SAT
![2 list clolring](../algo_data/ticket_5_1.png)
- Тут необходимо пояснение: ```pos[a][c]``` - это индекс цвета ```c``` в списке ```l``` вершины ```a```
![2 list clolring](../algo_data/ticket_5_2.png)

## Решение 2-SAT
![2 list clolring](../algo_data/ticket_5_3.png)

###### [Ссылка на более подробное обьяснение](https://e-maxx.ru/algo/2_sat)
# Билет 6
## Неразрешимость Halting Problem
- Halting Problem - "Дана программа, остановится ли она когда-нибудь на данном входе?"
![Теорема](../algo_data/ticket_6_1.png)
## Понятие Decision, Search задачи, языка
![Задачи](../algo_data/ticket_6_2.png)
## Определения DTime, P, EXP

![Определения](../algo_data/ticket_6_3.png)

### Более простым языком:
- **DTime(f(n))** - называется множество языков, для которых существует машина Тьюринга такая, что она всегда останавливается, и время ее работы не превосходит f(n), где n — длина входа.
- **P** - множество задач, для которых существуют полиномиальные алгоритмы решения.
- **EXP** - множество задач, сложность которых ограничена экспонентой от полинома от размерности задачи, то есть ограничена функцией exp(P(n)), где P - некоторый многочлен, а n - размер задачи.

## Cледствие P != EXP из теоремы об иерархии по времени

![Теорема](../algo_data/ticket_6_4.png)
# Билет 7
## Классы NP, coNP, coNEXP
![Определение](../algo_data/ticket_7_1.png)
![Определение](../algo_data/ticket_7_2.png)
### Простым языком:
- **NP** - класс языков (задач), ответ на которые можно проверить за полиномиальное время.
- **coNP** - это множество языков, для которых
 существует работающая за полиномиальное время детерминированная программа-верификатор R(x,y) а для каждого слова из языка (и только для слова из языка) можно предъявить сертификат полиномиальной длины, подтверждающий принадлежность слова языку и проверяемый верификатором.
- **coNEXP** - то же, что и выше, только время экспоненциальное.

## Примеры
![Примеры](../algo_data/ticket_7_3.png)
- **MAX-CLIQUE** - лежит в NP. Сводится к 3-SAT. [ссылка на пояснения](https://www.cs.cmu.edu/~avrim/451f11/lectures/lect1108.pdf)
- **coPRIME** - нужно проверить, является ли число составным. лежит в coNP
# Билет 8
## Классы NP-hard, NP-complete
![Определение](../algo_data/ticket_8_1.png)

### Простым языком: 
- **NP-трудная** задача имеет тот смысл, что эта задача не проще, чем «самая трудная в NP».
- Задача называется **NP-трудной** если каждая задача из NP полиномиально сводится к ней.
- Задача называется **NP-полной**, если она входит в NP и каждая задача из NP полиномиально сводится к ней (т.е. является NP-трудной).
- **NP-полные** задачи понимаются как самые трудные задачи из класса NP.

## Полиномиальное сведение
![Определение](../algo_data/ticket_8_2.png)
![Определение](../algo_data/ticket_8_3.png)

## Сведение по Куку
![Определение](../algo_data/ticket_8_4.png)

### Простым языком:
- Обращаться к задаче можем сколько угодно раз за время O(1)

## BH ∈ NP-complete
![Определение](../algo_data/ticket_8_5.png)
### Напоминалка 
![Определение](../algo_data/ticket_8_6.png)
# Билет 9
## Задачи максимизации
![Определение](../algo_data/ticket_9_1.png)
## search → decision
![Определение](../algo_data/ticket_9_2.png)
- **Говорим уверенным голосом:** у нас есть алгоритм который решает decision версию теперь возьмем и сведем ее к SAT, там восстанавливаем набор 
из этого набора как-то получаем решение к search (если кто-то читает это и считает что это неправильно поправьте)
## search 3-SAT → search k-IND
[СП обьясняет](https://www.coursera.org/lecture/advanced-algorithms-and-complexity/3-sat-to-independent-set-L47nL)

## Решение NP - задач
![Определение](../algo_data/ticket_9_3.png)
# Билет 10
## Машина Тьюринга
![Определение](../algo_data/ticket_10_1.png)
### Авторское объяснение: 
Есть какой-то заданный алфавит, который может принимать машина. Есть лента, на ней просто хаданы входные данные из алфавита.
То просто какие-то бесконечные входные данные. Алгоритм задается примерно так: есть таблица, строки этой таблицы - символы, используемые во входных данных; столбцы - состояния.
Алгоритм ходит по входной ленте и изменяет состояние наших входных данных. Алгоритм выполняется по столбцам, то есть столбцы(состояния) как-то на друг друга ссылаются и говорят как именно изменять входные данные. 
После завершения работы получаем ленту выходных данных. (это если совсем просто, правильнее читать с конспекта)

## RAM-машина
![Определение](../algo_data/ticket_10_2.png)
### Тут немного понятнее:
[Википедия](https://ru.wikipedia.org/wiki/RAM-машина)

## Другое определение класса NP
- Язык L принадлежит классу NP, если существует полином q и недетерминированная машина Тьюринга, которая распознает L за время q(n).
- Тут есть доказательство эквивалентности
[конспект МГУ](http://web.archive.org/web/20180712225703/http://lpcs.math.msu.su/~krupski/Complexity/krupski/part3.pdf)

## Понятие строгой-нестрогой полиномиальности
![Определение](../algo_data/ticket_10_3.png)

# Билет 11
## Теорема об иерархии по времени
### Теорема: DTime(f) \subsetneq􏰅 DTime(f log^2 f)
![Определение](../algo_data/ticket_11_1.png)

## Доказательство через диагонализацию
 
Последний абзац доказательства выше
# Билет 12
## BH → CIRCUIT-SAT
![Определение](../algo_data/ticket_12_1.png)
## CIRCUIT-SAT → SAT
![Определение](../algo_data/ticket_12_2.png)
## SAT → 3-SAT
![Определение](../algo_data/ticket_12_3.png)# Билет 13
## 3-SAT → k-IND
![Определение](../algo_data/ticket_13_1.png)
## k-IND → k-CLIQUE
![Определение](../algo_data/ticket_13_2.png)
## k-CLIQUE → VERTEX-COVER
[stackexchange](https://cs.stackexchange.com/questions/37527/reduce-clique-to-vertex-cover)

![Определение](../algo_data/ticket_13_3.png)
# Билет 14
## Классы RP, coRP
![Определение](../algo_data/ticket_14_1.png)
### Простыми словами: 
![Определение](../algo_data/ticket_14_2.png)
## Связь с классом NP
![Определение](../algo_data/ticket_14_3.png)
##  Понижение ошибки
![Определение](../algo_data/ticket_14_4.png)
## Формулировки трёх гипотез
![Определение](../algo_data/ticket_14_5.png)
# Билет 15
##  Поиск невычета
![Определение](../algo_data/ticket_15_1.png)
##  Тест Ферма
![Определение](../algo_data/ticket_15_2.png)
## Тест Миллера Рабина
![Определение](../algo_data/ticket_15_3.png)
## Частый элемент
![Определение](../algo_data/ticket_15_4.png)
## 3-LIST-COLORING
![Определение](../algo_data/ticket_15_5.png)
## Matrix multiplication testing
![Определение](../algo_data/ticket_15_6.png)
# Билет 16
## Теорема
![Определение](../algo_data/ticket_16_1.png)

### Для большего понимания:
![Определение](../algo_data/ticket_16_2.png)

![Определение](../algo_data/ticket_16_3.png)

## Вложение классов
![Определение](../algo_data/ticket_16_4.png)# Билет 17
## Класс BPP
![Определение](../algo_data/ticket_17_1.png)
### Для понимания:
![Определение](../algo_data/ticket_17_2.png)

[Ссылка на конспект МГУ](http://web.archive.org/web/20060717055429/http://lpcs.math.msu.su/~krupski/Complexity/krupski/part4.pdf)
## Понижение ошибки
![Определение](../algo_data/ticket_17_3.png)
# Билет 18
## Парадокс дней рождений + анализ вероятности в две стороны
![Определение](../algo_data/ticket_18_1.png)

- Если вдруг непонятно откуда берется такая вероятность читаем это: 
нам нужно посчитать вероятность того, что ДР не совпадет для первого человека берем 365/365. Тогда для второго убираем один день, получаем вероятность 354/365. (перемножаем это значение)
Заметим, что проделывая это дальше получаем то что нужно.
- Ещё нужно осознать какой-то матанализ с оценками
# Билет 19
## Алгоритм Полларда
![Определение](../algo_data/ticket_19_1.png)# Билет 20
## Решение 3-SAT
### Детерминированный алгоритм
![Определение](../algo_data/ticket_20_1.png)

### Рандомизированное решение
![Определение](../algo_data/ticket_20_2.png)

- Для понимания:

![Определение](../algo_data/ticket_20_3.png)

- [Расстояние Хемминга](https://qna.habr.com/q/255468)

## Приближенный алгоритм для MAX-3-SAT

![Определение](../algo_data/ticket_20_4.png)
![Определение](../algo_data/ticket_20_5.png)
# Билет 21
## Лемма Шварца-Зиппеля
![Определение](../algo_data/ticket_21_1.png)

### Для понимания: 
[Статья на википелии](https://ru.wikipedia.org/wiki/Лемма_Шварца_—_Зиппеля)

## Матрица Татта
![Определение](../algo_data/ticket_21_2.png)
![Определение](../algo_data/ticket_21_3.png)

## Поиск совершенного паросочетания
![Определение](../algo_data/ticket_21_4.png)# Билет 22
## Применение случайных чисел
### Идеальное кодирование
![Определение](../algo_data/ticket_22_1.png)

### Вычисление средней зарплаты без разглашения
![Определение](../algo_data/ticket_22_2.png)

### Доказательство гамильтонового пути без разглашения
[Википедия](https://ru.wikipedia.org/wiki/Доказательство_с_нулевым_разглашением#Гамильтонов_цикл_для_больших_графов)
# Билет 23
## Random shuffle массива
![Определение](../algo_data/ticket_23_1.png)

## Игра на 0-1-дереве
![Определение](../algo_data/ticket_23_2.png)

![Определение](../algo_data/ticket_23_3.png)

## Игра на min-max-дереве
- бинпоиск по ответу + игра на 0-1-дереве
- альфа-бетта отсечение
- [хабр с картинками и хорошим объяснением](https://habr.com/ru/post/146088/)## Билет 25
Автор: Габитов Даниил.

### Поиск в ширину. Решение очередью

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_25_1.jpg" alt="."/>
</p>

### Вещественный 0-1 BFS
* Решение с пракики.
<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_25_2.jpg" alt="."/>
</p>

### Структура кратчайших путей

Необходимо понимание стркутуры, в частности, что BFS строит дерево.
// I do not know what to say beside that
## Билет 26
Автор: Габитов Даниил.

### Решение для 0-k BFS

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_26_1.png" "width = 800" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_26_2.png" alt="home"/>
</p>

* Так же есть более подробное [описание основ](https://wiki.algocode.ru/index.php?title=0-K_BFS) алгоритма

### 0-1 BFS на деке

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_26_3.png" alt="home"/>
</p>
## Билет 27
Автор: Габитов Даниил

### Матрица расстояний

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_27_1.png" alt="home"/>
</p>

# Comment on solution

Как будем перебирать единицы в current? Можем найти минимальный бит у числа за единицу: x & -x. Давайте перебирать все числа(!) в битсете. Если число ноль - пропускаем, иначе у числа нужно взять минимальный бит, пока берется, занулять его и запоминать, что это за вершина была. Ассимптотика верная: Перебираем все числа за O(V / w), берем минимум O(n_{d}) раз. 

### 1-k bfs

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_27_2.png" alt="home"/>
</p>

## Билет 28
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_28_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_28_2.png" alt="home"/>
</p>
## Билет 29
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_29_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_29_2.png" alt="home"/>
</p>
## Билет 30
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_30_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_30_2.png" alt="home"/>
</p>
## Билет 31
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_31_1.png" alt="home"/>
</p>


## Билет 32
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_32_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_32_2.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_32_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_31_2.png" alt="home"/>
</p>

* Подробнее про [транзитивное замыкание](https://neerc.ifmo.ru/wiki/index.php?title=%D0%A2%D1%80%D0%B0%D0%BD%D0%B7%D0%B8%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B5_%D0%B7%D0%B0%D0%BC%D1%8B%D0%BA%D0%B0%D0%BD%D0%B8%D0%B5)

* Идея для обычного Флойда должна быть тривиальна. Чтобы понять, почему переход на битсет так работает, помогает нарисовать табличку и вспомнить определение транзитивности.
## Билет 33
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_33_1.png" alt="home"/>
</p>


* Алгоритм восстановления == просто обратные ссылки?
## Билет 34
Автор: Габитов Даниил



<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_2.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_3.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_34_4.png" alt="home"/>
</p>
## Билет 35
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_35_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_35_2.png" alt="home"/>
</p>
## Билет 36
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_36_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_36_2.png" alt="home"/>
</p>
## Билет 37
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_37_1.png" alt="home"/>
</p>
## Билет 38
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_38_1.png" alt="home"/>
</p>



<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_38_2.png" alt="home"/>
</p>
## Билет 39
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_39_1.png" alt="home"/>
</p
# Билет 40
## MST
![Определение](../algo_data/ticket_40_1.png)
## Лемма о разрезе
![Определение](../algo_data/ticket_40_2.png)
## Краскал. Прим. Доказательства
![Определение](../algo_data/ticket_40_3.png)

![Определение](../algo_data/ticket_40_4.png)# Билет 41
## MST
![Определение](../algo_data/ticket_40_1.png)

## Борувка
![Определение](../algo_data/ticket_41_1.png)

## Доказательство
![Определение](../algo_data/ticket_41_2.png)

- Лемма о разрезе говорит лишь про возможность добавить к остову одно ребро# Билет 42
## Алгоритм Йена
![Определение](../algo_data/ticket_42_1.png)
## Билет 45
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_4.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_5.png" alt="home"/>
</p>

### Еще картиночки

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_45_2.png" alt="home"/>
</p>

[Статья по приближениям](http://www.cs.tufts.edu/~cowen/advanced/2002/adv-lect3.pdf)

[Ссылка на лекцию CSS](http://www.cs.tufts.edu/~cowen/advanced/2002/adv-lect3.pdf)

### Правило Варнсдорфа.


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_additional_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_additional_2.png" alt="home"/>
</p>

ссылка на [лекцию](https://youtu.be/ph56-iCvAXY?t=2378)
## Билет 46
Автор: Даниил Габитов


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_46_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_46_2.png" alt="home"/>
</p>
## Билет 47
Автор: Даниил Габитов
// TODO спросить на консультации. Непонятно что хотят услышать.
## Билет 48
Автор: Даниил Габитов


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_48.png" alt="home"/>
</p>
## Билет 49
Автор: Даниил Габитов


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_49.png" alt="home"/>
</p>
# Билет 50
## Два станка
![Определение](../algo_data/ticket_50_1.png)
## Билет 51
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_51_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_51_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_51_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_51_4.png" alt="home"/>
</p>

## Билет 52
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_52_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_52_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_52_4.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_52_5.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_52_1.png" alt="home"/>
</p>

## Билет 53
Автор: Габитов Даниил


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_53_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_53_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_53_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_53_4.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_53_5.png" alt="home"/>
</p>
## Билет 54
Автор: Габитов Даниил

Легче посмотреть [лекцию](https://youtu.be/ph56-iCvAXY?t=834)...
# Билет 55
## Set cover
![Определение](../algo_data/ticket_55_1.png)
## ln(n)-приближение во взвешенном случае
- **|A|** – число ещё не покрытых элементов, а не исходный размер

![Определение](../algo_data/ticket_55_2.png)

## Реализация за линейное время в невзвшенном случае

![Определение](../algo_data/ticket_55_3.png)

## 2-OPT приближение для Vertex Cover

![Определение](../algo_data/ticket_55_4.png)## Билет 56
Автор: Габитов Даниил

Легче посмотреть [лекцию](https://youtu.be/ph56-iCvAXY?t=1635), в коспекте ничего нет...
# Билет 57
## Центроидная декомпозиция
![Определение](../algo_data/ticket_57_1.png)

## Построение
![Определение](../algo_data/ticket_57_2.png)

## Минимум на пути
![Определение](../algo_data/ticket_57_3.png)

![Определение](../algo_data/ticket_57_4.png)## Билет 58


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_centroid_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_centroid_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_centroid_4.png" alt="home"/>
</p>
## Билет 59
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_59_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_59_2.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_59_3.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_59_4.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_59_5.png" alt="home"/>
</p>
## Билет 60
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_60_1.png" alt="home"/>
</p>

### Доказательство леммы

Пусть высота дерева == 2h. Учитывая инвариант AVL, при каждом спуске вниз высота уменьшается либо на 1, либо на 2. Тогда, рассмотрим наше дерево только до глубины h. Оно будет полным (по-любому пути длины h будем спускаться и достигнем корня только в конце). Тогда, 2^h <= n, значит, h = O(logn).

### Вращения

В принципе, чтобы рассказать вращения и их крутизну достаточно пристально посмотреть на [картинки](https://www.geeksforgeeks.org/avl-tree-set-1-insertion/) с примером вращений и понять, что инвариант BST не нарушается, а именно, прямой обход дерева остается неизменным.

### Add и Del

Воспользуемся обычным вариантом из BST. Заметим, что мог поломаться  инвариант AVL. Для этого откатываясь назад после выполнения операции будем проверять инвариант и лечить поворотами при необходимости.

### Число вращений при добавлении

- При добавлении произойдет ровно одно вращение. На слайде ниже показаны варианты, когда это может произойти. Заметим, что обведенный вариант не возможен, так как avl было сломлено до этого (как и я ха-ха-ха)

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/rotate_1.png" alt="home"/>
</p>

- После поворотов высота стала такой же, как и до добавления (Не забываем, что высота изначальная была на единицу меньше)

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/rotate_2.png" alt="home"/>
</p>

#### Число вращений при удалении


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/delete_rotate.png" alt="home"/>
</p>
## Билет 61
Автор: Габитов Даниил

### Merge за log

  Есть две AVL дерева A и B, причем все ключи в B больше ключей в A. Давайте извлечем минимум из B сделаем его новым корнем дерева, подвесив A и B слева и справа соответственно. Осталось восстановить инвариант для корня (могут быть беды). Тогда, если дисбаланс равен k, то мы умеем восстанавливать баланс за O(k). Заметим, что k = O(log(n)), то есть меньше чем высота одного из деревтьев.

### Split за log^2

  Вместо тысячи [слов](https://youtu.be/a1N8mEAxNh4?t=3376)...
## Билет 62
Автор: Габитов Даниил

### Общие идеи: BST и неявный ключ.

* Давайте из BST сделаем массив. Тогда научимся делать add и delete из середины массива за log. Обычные операции с массивом тоже работают за log. *No pain no gain*

* Как получить по индексу элемент? Будем хранить для каждой вершины размер ее поддерева. Это свойство легко пересчитывается. Начнем спускаться с корня, если индекс <= v->l->get_size() пойдем в лево, если индекс == v->l->get_size() + 1, то v и есть искомая вершина, иначе, если индекс > v->l->get_size() + 1, то идем вправо, при этом уменьшив индекс на v->l->get_size() + 1.

* Аналогично можно по элементу восстановить индекс. Тогда del и add реализуются через IndexOf().

### Общие идеи: персистентность.

* Хотим при изменении дерева не терять предыдущую верисию. Тогда необходимо делать операции персистентыми. Самый простой способ добится этого - выполнять операции, как в BST, но при этом создавать копии вершин при подьеме наверх, строя как бы копию дерева, но уже измененную. Тогда после любой такой операции у нас появится еще один корень, который и будет являтся новой версией, а старое дерево останется нетронутым.

* Любое дерево поиска, где не обязательно нужны отцы, можно сделать персистентным. В частности AVL. Время работы останется пропорциональным глубине дерева, для AVL это 𝒪(log 𝑛).

* Следствие. ∃ персистентное дерево по неявному ключу с операциями за 𝒪(log 𝑛). 

* Следствие. Любую структуру данных можно сделать персистентной, с замедлением в 𝒪(log 𝑛) раз. Просто поменяем все массивы на персистентные массивы.

### Общие идеи: групповые операции.

* Задача: находить min 𝑦_𝑖: 𝐿 < 𝑥𝑖 < 𝑅 за 𝒪(ℎ). Давайте в кажом поддереве будем хранить диапазон x_min, x_max, y_min. Будем спускаться под дереву и смотреть на диапозон ключей. Если он попадает в наш, то можно взять минимум на всем поддереве, если он не входит совсем, забиваем на него. Что делать если есть пересечение? Когда-то он разобьется на входящий и не входящий отрезки. 

* Почему работает за быстро? Потому что на каждом уровне рекурсии рассматривается не более чем 4 вершины. Док-во - увражнение. Рассмотреть, как могжет делится отрезок, который не полностью входит в промежуток.

* Так же можно делать, например, присвоение на отрезке. Поддеревья ищем аналогично + ленивое изменения с проталкиваюищи операциями.
## Билет 63
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_63_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_63_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_63_3.png" alt="home"/>
</p>

### [Видео](https://youtu.be/_b_mFvR6v_o) лекции.
## Билет 64
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_64_1.png" alt="home"/>
</p>

##### [Запись](https://youtu.be/iYZNLe2U5sc?t=184) практики.
## Билет 65
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_65.png" alt="home"/>
</p>

##### [Разбор на практике](https://www.youtube.com/watch?v=iYZNLe2U5sc&list=PLxMpIvWUjaJsrvC18SslESWGeauRH2Zrn&index=7)

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_65_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_65_2.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_65_3.png" alt="home"/>
</p>

## Билет 66
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_66_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_66_2.png" alt="home"/>
</p>

### Второе определение

Шафлим все значения вершин. Делаем add в этом порядке.

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_66_3.png" alt="home"/>
</p>

### Эквивалентность

Заметим, что там и там каждый раз выбор кореня - случайный. Значит, все эквивалентно.
## Билет 45
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_67_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_67_2.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_67_3.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_67_4.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_67_5.png" alt="home"/>
</p>

##### [Ссылка](https://youtu.be/_b_mFvR6v_o?t=2504) на лекцию

## Билет 68
Автор: Габитов Даниил



### *Эффективный* merge и split

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_68_1.png" alt="home"/>
</p>

###### [Ссылка на практику](https://youtu.be/iYZNLe2U5sc?t=2302)

### Персистентные декартовы деревья без y

  Давайте сделаем персистентный Trep + Implisit Key. НО! При merge частей одного и того же дерева могут повторятся y и из-за этого будет образовываться микробамбуки из одинаковых y. Значит, нужно избавиться от y. Для этого нужно изменить только merge (split не зависит от y). 
  
  Давайте будем выбирать на каждом шаге вершину, которая будет корнем, равновероятно. Есть два дерева A, B. Берем корень из левого поддерева с вероятностью  A/(A+B) справа с вероятностью B/(A+B).
  
  ###### [Ссылка на лекцию](https://youtu.be/_b_mFvR6v_o?t=4139)
## Билет 69
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_69_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_69_2.png" alt="home"/>

</p><p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_69_3.png" alt="home"/>
</p>

###### [Ссылка на повороты](https://neerc.ifmo.ru/wiki/index.php?title=Splay-%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE), такие же как в AVL

  Чтобы доказать амортизированное время работы Splay необходимо провести амортизированный анализ. Давайте за потеницал возьмем сумму по всем вершинам: log от размера поддерева. Утверждается, что тогда splay займет log амортищированно. 
## Билет 70
Автор: Габитов Даниил

##### Напоминалка того, как устроен арматизированный анализ

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_70_1.png" alt="home"/>
</p>

##### Вспомогательные леммы + доказательство

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_70_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_70_3.png" alt="home"/>
</p>

//TODO ask if this is enought to prove only zig-zig


[Ссыкла на лекцию](https://youtu.be/17E92eX9uvw?t=1450)
## Билет 71
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_71_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_71_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_71_3.png" alt="home"/>
</p>


##### [Ссылка на лекцию](https://youtu.be/17E92eX9uvw?t=4355)
## Билет 72
Автор: Габитов Даниил



### Персистентный стек и персистентная очередь через 5 стеков

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/tachka_prokachka.jpg" alt="home"/>
</p>

##### [Ссылка на лекцию](https://youtu.be/17E92eX9uvw?t=26)


## Билет 73
Автор: Габитов Даниил

### Персистентный Deque. Pairing.

##### [Ссылка на лекцию](https://youtu.be/17E92eX9uvw?t=373)

  Напишу немного пояснений. Зачем нужен пейринг? наша цель - сохранять копии. Чтобы не копировать каждый раз полностью дек можно использовать ссылки. Вот на этих ссылках и строится весь пейринг. 
  
  Что делать если отщепили из центра пару, а там снова пара? Уходим в рекурсию. Эта рекурсия максимум глубины log_n т.к. каждый раз уменьшаем размер пары в два раза.

### Персистентный массив

Я не уверен, что хотят услышать в этом билете, но... Чтобы получить персистентрный массив можно просто использовать любое bst которое умеет поддерживать глубину + неявный ключ. Например, Trap (Самый простой вариант в реализации)
## Билет 74
Автор: Габитов Даниил

### Skip List
  Давайте сделаем logn слоев(списков). В самом низу будет располагаться наш полный список. Пойдем снизу вниз и каждый раз будем проталкивать элемент в список выше и соед. ребром два списка, если подкинули монетку и выпал орел (1/2 вер. крч). На каждом из ребер будем хранить вес: длину до след. вершины если список был бы полным.
  
  Как сделать Find? Давайте пойдем вправо пока можем идти. Если нет - идем в список ниже, пока не найдем наш элемент. Это работает за log_n. Почему так? Всего log уровней. Утверждение, на каждом уровне сделаем не более чем константа операции.
  
  Почему константа? Вероятность того, что мы пройдем x шагов вперед равна 1/2^x. Все элементы должны были умереть. Тогда мат ожидание кол-ва шагов sum_x: x/2^x. Этот ряд сходится (По Даламберу ааа как сдать матан ее бляттавтовоаылваь).
  
  Как сделать erase? Сделаем find + поднимемся наверх и перекидаем реба, удалим вершину, сделаем -1 в правое ребро т.к. -1 элемент.
  
  Как сделать insert? Начнем с вернхнего уровня спускаться с позиции вставки вниз, пока не упремся в нижний слой. После этого на обратном шаге кидаем монетку и пересчитываем ребра, вставляем если нужно.
  
  Все работает за log.
  
[Ссылка на лекцию](https://youtu.be/17E92eX9uvw?t=3015)
## Билет 75
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_75_1.png" alt="home"/>
</p>
## Билет 76
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_76_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_76_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_76_3.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_76_4.png" alt="home"/>
</p>

###### [Ссылка на лекцию]
## Билет 77
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_77_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_77_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_77_3.png" alt="home"/>
</p>

##### [Ссылка на лекцию](https://youtu.be/XNRiaZjCxzc?t=541) (Когда не степень двойки + док-во непересечения).
## Билет 78
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_78_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_78_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_78_3.png" alt="home"/>
</p>
## Билет 79
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_79_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_79_2.png" alt="home"/>
</p>
## Билет 80
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_80_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_80_2.png" alt="home"/>
</p>

##### [Реализация на мапе](http://acm.math.spbu.ru/~sk1/algo/segment-tree/cs-center/up_dynamic.cpp.html)

##### [Реализация на ссылках](https://site.ada.edu.az/~medv/acm/Docs%20e-olimp/Volume%2033/3252.htm)
## Билет 81
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_81_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_81_2.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_81_3.png" alt="home"/>
</p>

##### [Ссылка на лекцию](https://youtu.be/XNRiaZjCxzc?t=3335)

## Билет 82
Автор: Габитов Даниил

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_82_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_82_2.png" alt="home"/>
</p>

  [Ссылка на практику](https://youtu.be/bI5OXoyI7Sg?t=4224), я там очень сильно туплю, но я узнал, что такое ДО за 10 минут до практики...
## Билет 83
Автор: Габитов Даниил

### K-ая порядковая статистика.

* За log^3 бинпоиск + 2D ДО

* За log^2 заменяем 2D ДО на разницу преффиксов. Для этого поддерживаем персистентное дерево отрезков по значению.

* За log заметим, что строение двух версий деревьев не отличается по строению, значит, можно одно вычесть из другого и получить отрезок [l, r]. Тогда бинпоиск можно заменить на 1 спуск. Спускаясь ищем минимальное значение >= k.

##### [Ссылка на лекцию](https://youtu.be/d9fBIjjOcaI?t=624)
## Билет 86
Автор: Габитов Даниил

### Обычный Sparse Table

  Предподсчитаем для всех индексов минимум на отрезке [i, i + 2^k], k <= logn. В итоге nlog памяти и времени. Тогда гет на промежутке [l, r] это взять наибольший такой k который помещается в наш отрезок и посмотреть лучший ответ на промежутке [l, l + 2^k] и [r - 2^k, r]. Они всегда будут покрывать весь промежуток (Возможно, пересекатся, но для минимума это не важно).

[Ссылка на лекцию](https://youtu.be/d9fBIjjOcaI?t=222)


### Еще есть Sparse Table++

// Вроде это 88 билет. На всякий случай можно глянуть - вдруг спросят...
## Билет 87
Автор: Габитов Даниил

#### Проще посмотреть [лекцию](https://youtu.be/d9fBIjjOcaI?t=1741), и тогда все сведения вспомнятся, они не сложные.

  Первый переход через Декартач, второй через эйлеров обход

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_87_1.png" alt="home"/>
</p>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_87_2.png" alt="home"/>
</p>

#### Итог: умеем решать RMQ за <nlog, 1>, тогда умеем и LCA за это же время.
## Билет 88
Автор: Габитов Даниил

Давайте поделим массив на k кусочков длины logn и построим на них Sparse Table за линию. Что делать если запрос не ровно по разделениям? Для этого предподсчитываем префиксы и суффиксы. Осталось научится обрабатывать случай, когда запрос внутри 1 блока. Чтобы это решить, давайте построим внутри каждого отрезка еще один Sparse Table

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/tachka_prokachka.jpg" alt="home" width="500" height="350"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_88_1.png" alt="home"/>
</p>
## Билет 89
Автор: Габитов Даниил

  Давайте вспомним, что ранее свели RMQ и LCA к RMQ+-1. Тогда, решив последний, решим все.
  
  Вспомним предыдущий билет. Линию нам обламывает SparceTable в каждом блоке, всего блоков k штук. Давайте очень крутом запрекалькаем. Сколько... И тут я понял, что Дима обьясняет этот билет за 5 минут, а это 2.5 минуты на скорости 2x, послушайте лучше [его](https://youtu.be/d9fBIjjOcaI?t=3154)...
## Билет 90
Автор: Габитов Даниил


##### Вообще, мне очевидно как делается это, поэтому подробных обьяснений нет. МОжно глянуть [лекцию](https://youtu.be/d9fBIjjOcaI?t=3586). 

  Кратко: через эйлеров обход выражаем isAncestor. Прагыаем из одной из вершин, пока не встретим самого нижнего предка. По сути, бинарикм. Второй вариант - Поднимаемся на один уровень и снова бинарим, только теперь критерий - слились ли мы в одну вершину. В итоге <nlog, log>

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_90_1.png" alt="home"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_90_2.png" alt="home"/>
</p>
## Билет 91
Автор: Габитов Даниил

На [лекции](https://youtu.be/d9fBIjjOcaI?t=4912) за 5 минут.

## LCA в offline, алгоритм Тарьян
![Определение](../algo_data/ticket_91_1.png)

## [Тут без логарифма](https://e-maxx.ru/algo/lca_linear_offline)
## Билет 92
Автор: Габитов Даниил

На [лекции](https://youtu.be/d9fBIjjOcaI?t=4566) обьяснили за 5 минут. Note: спуск как в k-ой статистике за log.
И еще чуть-чуть Вишкина на след [лекции](https://youtu.be/TSRPgTLfZt8?t=11)

## Алгоритм Вишкина
![Определение](../algo_data/ticket_92_1.png)

## Напоминалка: эйлеров обход второго типа
![Определение](../algo_data/ticket_92_2.png)

## Напоминалка: ДО
![Определение](../algo_data/ticket_92_3.png)
# Билет 95
Автор: Габитов Даниил

- **Идея простая:** разобьем наше дерево на пути, на которых построим ДО. Построим так, чтобы было не больше log переходов между путями. Поэтому будем соединять вершины по самым тяжелым ребрам. Тогда на пути будет не более log ребер перехода т.к. они легкие и уменьшают размер дерева в 2 раза.
  
- **Пример:** поиск минимума на пути. NOTE: в hld веса в вершинах.
  
- **Можно сделать еще лучше:** добавить возможность запросов по поддереву. Для этого немного переструктурируем дерево так, чтобы все наши выбранные ребра были слева. Сделаем Эйлеров обход. Тогда, запрос на дереве превращается в запрос на массиве(рассматриваем интересующее нас поддерево). Заметим, что теперь вершины стоят в удобном нам порядке, а именно образуют тяжелые пути. 

## [Лекция](https://youtu.be/TSRPgTLfZt8?t=246)
## Heavy-Light Decomposition
![Определение](../algo_data/ticket_95_1.png)

## Построение
![Определение](../algo_data/ticket_95_2.png)

## Пример использования
![Определение](../algo_data/ticket_95_3.png)
# Билет 96
## [Лекция](https://youtu.be/TSRPgTLfZt8?t=1806)

## Euler-Tour Tree
![Определение](../algo_data/ticket_96_1.png)
## Билет 97
Автор: Габитов Даниил

Я устал писать билеты...

### Link Cut Tree

![Определение](../algo_data/ticket_97_1.png)

### Потенциал, оценка Expose

![Определение](../algo_data/ticket_97_2.png)

#####  [Ссылка на статью](https://neerc.ifmo.ru/wiki/index.php?title=Link-Cut_Tree)
#####  [Ссылка на лекцию](https://youtu.be/TSRPgTLfZt8?t=1824)
# Билет 98

### Link Cut Tree

![Определение](../algo_data/ticket_97_1.png)

### Оценка MakeRoot

![Определение](../algo_data/ticket_97_2.png)

### Оценка Link, Cut

![Определение](../algo_data/ticket_98_1.png)

#####  [Ссылка на статью](https://neerc.ifmo.ru/wiki/index.php?title=%D0%94%D0%B5%D1%80%D0%B5%D0%B2%D1%8C%D1%8F_%D0%AD%D0%B9%D0%BB%D0%B5%D1%80%D0%BE%D0%B2%D0%B0_%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B0)
#####  [Ссылка на лекцию](https://youtu.be/TSRPgTLfZt8?t=1824)
