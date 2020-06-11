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

