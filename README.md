# match_master

## Алгоритм
Так как у всех проектов одинаковые приоритеты по студентам(отсортированы по рейтингу), то гейл-шепли вырождается в такой алгоритм:
1) Подаем на вход студентов отсортированных по рейтингу, алгоритм начинает двигаться вниз по студентам
2) На текущем студенте алгоритм начинает движение по его приоритетам(проектам) от 1 приоритета и так далее до последнего
3) Если алгоритм видит, что на проекте есть свободные места, то назначает студента на этот проект
4) Процесс продолжается вниз по студентам
Таким образом, можно сказать, что лучшие студенты просто выбирают первыми

Если студент не заполнил какие-то приоритеты(например, только 5 из 10) или вообще ничего не заполнил, 
то мы добавляем ему в конец приоритетов все оставшиеся проекты(которые он не выбирал) и рандомно их перемешиваем.

## Корнер-кейсы
В алгоритме критически важно, чтобы количество студентов по каждому направлению было строго равно количеству мест. 
Если студентов меньше(как и было сейчас, так как кто-то отваливался), то все ломается и нужно в каких-то проектах уменьшать количество мест.
Ситуации, когда студентов больше быть не должно, так как отсекают ровно нужно кол-во(с этом случае надо где-то увеличить места).

## Группы
Изначально, была идея отдельно мэтчить студентов внутри хаба+направления(например собирать всех Москва+ШБР Python и запускать алгоритм внутри них). 
Но сказали, что допустим в казахстане питонистов меньше чем нужно и поэтому их привезут из других хабов. 
В итоге, просто просили студентов сначала ставить в приоритетах свой хаб и учитывали всех вместе, только внутри направления(например Python) без учёта хаба.
