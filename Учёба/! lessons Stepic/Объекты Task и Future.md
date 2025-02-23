[Урок](https://stepik.org/lesson/933701/step/1?unit=939600)
Future - родительский класс task

Объекты Task и Future представляют результат асинхронной операции, которая ещё не завершена, но уже ожидается.

``` python
future = asyncio.Future() # create future object
await future 
result = future.result() # get result
future.set_result(await_result) # set result 
```
Объект Future всегда следует запускать с оператором await, точно так же, как и объект задачи или корутину.

Состояние Future/Taks:
- Pending (ожидание) - операции еще не выполнены. Ошибка: InvalidStateError
- Competed (завершен) - операция завершена. future.done() вернет false. Объект считается завершенным, если он был отменен или если для него был установлен результат или исключение с помощью set_result и set_exception соответственно.
- Cansellled(отменён) - операция отменена: вызов функции future.cancel(). Проверка future.cancelled(). Отменить можно только незавершенную задачу. Если операция отменена, то вызов result вызовет исключение CancelledError.


> [!NOTE] ensure VS create_task
> asyncio.ensure_future() - функция доступная начиная с Python 3.4 - устарела
> asyncio.create_task() - функция была введена в Python 3.7 - предпочтительна
> 
> Разница: первый возвращает asyncio.Task, второй \_acyncio.Task.  


