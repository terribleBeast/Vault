

Для передачи параметров в **Bot API** доступны 4 способа:
- [Запрос в URL](https://dzen.ru/away?to=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FQuery_string) команда `https://api.telegram.org/bot<token>/название_метода.
    
- application/x-www-form-urlencoded
    
- application/json (не подходит для загрузки файлов)
    
- multipart/form-data (для загрузки файлов)


Получение сводки апдейтов: `getUpdates` (TG хранит апдейты не более 24 часов)
Отправка сообщений через URl: `sendMessage?chat_id=<id>text=<text_message>

Схема взаимодействия с ботом:
* Пользователь отправляет боту какое-либо сообщение
* Бэкэнд бота получает апдейт с сервера 
* Бэкэнд бота обрабатывает апдейт
* Бэкэнд боты отправляет "инструкцию" на сервер Телеграмм, в которой показано, что нужно сделать боту 





>[!TODO]
>Описать принцип работы программы для запросов 



Ресурсы:
* Приятное отображение [json](https://jsoneditoronline.org/)
* [Статья](https://dzen.ru/a/XuuyWxUXzh1fpiRj)
