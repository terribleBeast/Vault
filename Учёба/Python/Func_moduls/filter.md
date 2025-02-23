Synt: filter(function, iterable)

Construct an iterator from those elements of _iterable_ for which _function_ is true. _iterable_ may be either a sequence, a container which supports iteration, or an iterator. If _function_ is `None`, the identity function is assumed, that is, all elements of _iterable_ that are false are removed.

**Note**: that `filter(function, iterable)` is equivalent to the generator expression `(item for item in iterable if function(item))` if function is not `None` and `(item for item in iterable if item)` if function is `None`.


Interesting example:

``` python
numbers = filter(lambda x: x > 0, [-3, -2, -1, 0, 1, 2, 3])
if 1 in numbers: 
    print('bee') 
if 1 in numbers: 
    print('geek')

# bee
```

Ресурсы:
1) [Поколение](https://stepik.org/lesson/640044/step/14?unit=636564) 