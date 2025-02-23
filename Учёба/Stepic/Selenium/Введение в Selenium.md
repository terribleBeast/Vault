## Введение

**Selenium** - популярный инструмент тестирования веб-приложений. Он позволяет взаимодействовать с элементами страницы. 

> [!note]
> Selenium поддерживает все основные браузеры

## Основные понятия в Selenium Webdriver

**Weddriver** - это интерфейс, который позволяет отправлять команды напрямую в браузер и контролировать его. Инициирует сессию.

*Создание экземпляра Webdriver для Google Chrome*

``` python
from selenium import webdriver

driver = webdriver.Chrome()
driver.get("http://example.com")
```

Это замена? [ссылка](https://playwright.dev/python/docs/api/class-playwright)