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
