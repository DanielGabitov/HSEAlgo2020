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
