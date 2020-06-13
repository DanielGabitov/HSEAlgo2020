## Билет 88
Автор: Габитов Даниил

Давайте поделим массив на k кусочков длины logn и построим на них Sparse Table за линию. Что делать если запрос не ровно по разделениям? Для этого предподсчитываем префиксы и суффиксы. Осталось научится обрабатывать случай, когда запрос внутри 1 блока. Чтобы это решить, давайте построим внутри каждого отрезка еще один Sparse Table

<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/tachka_prokachka.jpg" alt="home" width="500" height="350"/>
</p>


<p align="center">
  <img src="https://github.com/DanielGabitov/HSEAlgo2020/raw/master/algo_data/ticket_88_1.png" alt="home"/>
</p>
