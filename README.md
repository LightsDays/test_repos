Codingame. The Labyrinth. Перваначальная идея
-----------------------------------
Перед движением Крик оценивает обстановку и мысленно пытается пройти по клеткам и посмотреть, куда это его приведет.

### Каждая клетка поля - объект
У каждой клетки есть свои координаты и статус (wall, question, free и т.д.), а так же 4 указателя на все 4 возможных направления движения.
Распространение пути будет во всех направлениях от старта. Во избежания зацикливаний, клетка, по которой уже проложен путь, будет считаться "занятой"
![alt text](https://sun9-49.userapi.com/c200624/v200624318/495e8/86tqb0r51lk.jpg)

Клетки со статусами wall и quesion не могут иметь направлений для движения.

Если обычная клетка "упирается" в клетки со статусом "wall" то в неё идти смысла нет, и она сама становится "wall"

![alt text](https://sun9-54.userapi.com/c200624/v200624318/49612/7YJWxBmKP24.jpg)

![alt text](https://sun9-62.userapi.com/c200624/v200624318/49627/WiFohLEbwBU.jpg)

После первоначальной оценки Крик двигается, и открывает новые клетки, которые сразу "связываются" с текущими. Снова блокируются "бесполезные" клетки и Крик продолжает движение, пока "на горизонте" не будет клетки со статусом "finish".

### Клетка со статусом "finish"
Если такая клетка найдена, и она связана с другими, то Крик идет прямо к ней

Если не связана, то Крик продолжает "исследование", пока связь не будет установлена

### Обратный путь (потом)
- Либо запустить волновой алгоритм и пойти обратно

- Обратная связь с клетками и по ним обратно
