---
tags:
  - Python
---
---
Дата создания: 2025-01-20 14:37
Дата последнего изменения: 2025-01-20 14:37
---
## Основные идеи
1) 
---
Время в компьютере хранится, как количество секунд прошедших с получнои 1 января 1970 года (00:00:00 ==UTC==) этот момент называют "[эпохой Unix](https://ru.wikipedia.org/wiki/Unix-время#:~:text=Unix-время%20(англ.,Unix%20Epoch).)", так как в таком формате удобнее с ней работать.
## Модуль `datetime`
Для работы с датой и временем в Python есть модуль `datetime`. 
Методы `datetime`:
- получение текущих системных даты и времени
- арифметические операции над датами
- сравнение даты и времени
- форматированный вывод информации о дате и времени

## Типы данных модуля `datetime`


| Тип данных    | Характеристика                                                                              |
| ------------- | ------------------------------------------------------------------------------------------- |
| date          | информация о дате (без времени), на основе Григорианского календаря                         |
| time          | информация о времени (без даты)                                                             |
| datetime      | информация о дате и времени, на основе Григорианского каленадаря                            |
| ==timedelta== | описывает определённый период во времени, который находится между двумя различными моментам |
| tzinfo        | представляет различные сведения о часовом поясе                                             |
| timezone      | описывает время, руководствуясь стандартом UTC                                              |


> [!NOTE] Title
> Объекты `date` и `time` неизменяемы.


## Константы

`datetime.MINYEAR`

`datetime.MAXYEAR`

`datetime.UTC`

Замена для [`datetime.timezone.utc`](https://docs.python.org/3/library/datetime.html#datetime.timezone.utc "datetime.timezone.utc").

Added in version 3.11.

### Тип данных `date`

Представляет информацию о дате (год, месяц, день). Учитывает ограничения на вход данных.

Сигнатура: 
`date(year, month, day)`


``` python
from datetime import date

my_date = date(1930, 10, 6)

print(my_date) 
print(type(my_date))


print(date.today()) # текущая дата


print(my_date.weekday()) # день недели (нумерация с 0), если с одного, то 
						 # isoweekday()

date1 = date.fromordinal(365) # дата, соответствуюшая номеру дня 365 
date2 = date(1999, 12, 26) 

print(date1) 
print(date2.toordinal()) # номер дня, соответствующий дате 1999-12-26
```

Для получения атрибута года, месяца, дня используется точечную нотацию.

### Тип данных `time`

Представляет информацию о времени (часы, минуты, секунды, микросекунды). 

Сигнатура: 
`time(hour=0, minute=0, second=0, microsecond=0)`

- `hour` — часы времени
- `minute` — минуты времени
- `second` — секунды времени
- `microsecond` — микросекунды времени

Учитываются разумные (реальные) ограничения (нельзя hour > 24)

``` python
from datetime import time 

time1 = time(11, 20, 54, 1234) 
time2 = time(11, 20, 54) 
time3 = time(11, 20) 
time4 = time(11) 
time5 = time() 
time6 = time(minute=23, second=56) 

print(time1, time2, time3, time4, time5, sep='\n')
print(time6)
```

## Сравнение дат и времени 

Дату (тип `date`) и время (тип `time`) можно сравнивать с помощью операторов ` ==`, `!=`, `<`, `>`, `<=` и  `>=`.

``` python
from datetime import date, time 

date1 = date(2022, 10, 15) 
date2 = date(1999, 12, 26) 
time1 = time(13, 10, 5) 
time2 = time(21, 32, 59) 

print(date1 < date2) 
print(time1 < time2)
```

## Встроенные функции `str()` и `repl()`

Встроенная функция `str()` возвращает объект **в неформальном (понятном человеку)** строковом представлении.

Встроенная функция `repr()` возвращает объект **в формальном (понятном интерпретатору)** строковом представлении.

``` python
from datetime import date, time 

my_date = date(2021, 12, 31) 

my_time = time(11, 20, 54) 

print(repr(my_date)) 
print(repr(my_time))

print(str(my_date)) 
print(str(my_time))
```

## Форматирование даты и времени

По умолчанию вывод даты и времени осуществляется в ISO формате:

- дата имеет вид: `YYYY-MM-DD`
- время имеет вид: `HH:MM:SS` или `HH:MM:SS.ffffff`

Для форматированного вывода даты и времени используется метод `strftime()` (string format time) (для обоих типов `date` и `time`).

``` python
from datetime import date, time 


my_date = date(2021, 8, 10) 
my_time = time(7, 18, 34) 

print(my_date) # вывод в ISO формате 
print(my_time) # вывод в ISO формате 
print(my_date.strftime('%d/%m/%y')) # форматированный вывод даты 
print(my_date.strftime('%A %d, %B %Y')) # форматированный вывод даты 
print(my_time.strftime('%H.%M.%S')) # форматированный вывод времени
```

Смотри спецификаторы в документации или [Step 2](https://stepik.org/lesson/570048/step/1?unit=564591) 

``` python
from datetime import date, time 

my_date = date(2021, 8, 10) 
my_time = time(7, 18, 34) 

print(my_date.strftime('%a %A %w %d %b %B %m %y %Y %H %I %p %M %S %f %z %Z %j %U %W %c %x %X')) 

print(my_time.strftime('%a %A %w %d %b %B %m %y %Y %H %I %p %M %S %f %z %Z %j %U %W %c %x %X'))
```

Для вывода в ISO: `isoformat()`

``` python
from datetime import date, time 

my_date = date(2021, 12, 31) 
my_time = time(21, 15, 17) 

print('Дата: ' + my_date.isoformat()) 
print('Время: ' + my_time.isoformat())
```

Преобразование строки в дату `fromisoformat()`. Работает только с датой и временем. Добавлен в версии 3.7.
``` python
from datetime import date, time 


my_date = date.fromisoformat('2020-01-31')
my_time = time.fromisoformat('10:20:30') 

print(my_date) 
print(my_time) 
print(type(my_date))
print(type(my_time))
```


> [!NOTE] Title
> - str**f**time - string **format** time
> - str**p**time - string **parse** time




### Использование локализации

``` python
from datetime import date 
import locale 

locale.setlocale(locale.LC_ALL, 'ru_RU.UTF-8') 

my_date = date(2021, 8, 10) 
print(my_date.strftime("%A %d, %B %Y")) # форматированный вывод даты в русской локализации
```


## Примечания
1. `replace()` - для замены значения атрибута в `date`, `time` (создает новый объект). 
2. По умолчанию объекты типов `date` и `time` выводятся в ISO 8601 формате:
	- дата в формате ISO 8601 имеет вид: `YYYY-MM-DD`
	- время в формате ISO 8601 имеет вид: `HH:MM:SS` или `HH:MM:SS.ffffff`
	Прочитать подробнее про ISO 8601 формат можно [тут](https://ru.wikipedia.org/wiki/ISO_8601).
3. Модули (пакеты) для работы с
	1. [`calendar`](https://docs.python.org/3/library/calendar.html#module-calendar "calendar: Functions for working with calendars, including some emulation of the Unix cal program.") - общие фукнции для работы с календарем
	2. [`time`](https://docs.python.org/3/library/time.html#module-time "time: Time access and conversions.") - доступ ко времени и его преобразование
	3. [`zoneinfo`](https://docs.python.org/3/library/zoneinfo.html#module-zoneinfo "zoneinfo: IANA time zone support") - конкретный часовой пояс представляющий IANA
	4. [dateutil](https://dateutil.readthedocs.io/en/stable/) - сторонняя библиотека с расширенными часовыми поясами и поддержкой парсинга
	5. [DateType](https://pypi.org/project/DateType/) - сторонняя библиотека, которая включает четкие статические типы, например, даёт возможность статической проверки между ==наивными и осознанными объектами== `datetime`

---
## Ресурсы:
1) [документация](https://docs.python.org/3/library/datetime.html)
2) [Step 1. Stepic](https://stepik.org/lesson/609341/step/1?unit=604560)
3) [Step 2. Stepic](https://stepik.org/lesson/570048/step/1?unit=564591)
