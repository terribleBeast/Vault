Synt: reduce(function, iterable, \*initializer)

from reduce import reduce

Apply _function_ of two arguments cumulatively to the items of _iterable_, from left to right, so as to reduce the iterable to a single value.

For example, `reduce(lambda x, y: x+y, [1, 2, 3, 4, 5])` calculates `((((1+2)+3)+4)+5)`. The left argument, _x_, is the accumulated value and the right argument, _y_, is the update value from the _iterable_. If the optional _initializer_ is present, it is placed before the items of the iterable in the calculation, and serves as a default when the iterable is empty. If _initializer_ is not given and _iterable_ contains only one item, the first item is returned.

> [!note]
>  Reduce() в python 2.X была встроенной, но в Python 3.X её решили перенести в модуль functools.
