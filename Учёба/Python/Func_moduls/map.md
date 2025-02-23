Synt: map(function, iterable, \*iterables)

Return an iterator that applies _function_ to every item of _iterable_, yielding the results. If additional _iterables_ arguments are passed, _function_ must take that many arguments and is applied to the items from all iterables in parallel. With multiple iterables, the iterator stops when the shortest iterable is exhausted.

Map - отобразить. Название пришло из математики, где так называется  функция, отображающая одно множество значений в другое путём преобразования всех элементов с помощью некой трансформации.

Если передать несколько последовательностей, то элементы будут брать с каждого объекта по одному, начинаю с первого. Наименьшая длина объекта является ограничителем.

Ресурсы
1) [Поколение](https://stepik.org/lesson/640044/step/14?unit=636564) 