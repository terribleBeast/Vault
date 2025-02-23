[Traceback](Traceback.md)
Модуль `traceback` в Python используется для извлечения, форматирования и вывода трассировок стека, что особенно полезно при отладке программ. Он позволяет получить информацию о том, где и почему произошла ошибка.

Основные функции модуля `traceback`:  

**`traceback.print_tb(tb, limit=None, file=None)`**: Выводит до `limit` записей трассировки стека из объекта `tb`. Если `limit` не указан или равен `None`, выводятся все записи. Если `file` не указан, вывод идет в `sys.stderr`  
 

**`traceback.print_exception(exc, /, [value, tb, ]limit=None, file=None, chain=True)`**: Выводит информацию об исключении и записи трассировки стека из объекта `tb`. Если `tb` не `None`, выводится заголовок “Traceback (most recent call last):”. Также выводится тип и значение исключения.  
 

**`traceback.print_exc(limit=None, file=None, chain=True)`**: Сокращение для `print_exception(sys.exception(), limit, file, chain)`.  
 

**`traceback.format_exc(limit=None, chain=True)`**: Возвращает строку с информацией об исключении и трассировкой стека.

Примеры использования:  
**Пример из курса**

```python
from sys import exc_info
import traceback

try:
    х = 1 / 0
except Exception as err:
    tb = exc_info()[2]
    print("Тип ошибки:", exc_info()[0])          # Тип ошибки: <class 'ZeroDivisionError'>
    print("Сообщение об ошибке:", exc_info()[1]) # Сообщение об ошибке: division by zero
    print("Трассировка стека:")                  # Трассировка стека:
    traceback.print_tb(tb) 
    
    #   File "d:\My_folder\Python\main.py", line 5, in <module>
    # х = 1 / 0
```

  
**Пример с `print_tb`**

```python
import traceback
try:
    1 / 0
except ZeroDivisionError as e:
    tb = e.__traceback__
    traceback.print_tb(tb)
```

  
**Пример с `print_exception`**

```python
import traceback
try:
    1 / 0
except ZeroDivisionError as e:
    traceback.print_exception(e)
```

  
**Пример с `format_exc`**

```python
import traceback
try:
    1 / 0
except ZeroDivisionError:
    error_message = traceback.format_exc()
    print(error_message)
```