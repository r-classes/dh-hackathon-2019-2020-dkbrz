### Проект по "Введению в науку о данных". Анализ YouTube-канала "Мама отличника"

**Сбор данных**

Для R есть специальная библиотека ```tuber``` для работы с YouTube API. 

0. Чтобы взаимодействовать с апи нужно получить токен для аутентификации в панели разработчика в гугл-аккаунте, а потом указать этот код в библиотеке и авторизоваться.
1. Получить список видео
2. Пройти по видео и получить подробную инофрмацию (типа тегов, длительности и др)
3. Достать комментарии
4. Сохранить в удобном формате

**Конвертация**
Позже оказалось, что работать с БД удобнее, поэтому csv таблицы были конвертированы в SQLite базу данных.
База лежит [здесь](https://yadi.sk/d/ztPcsIrF6AL3-w)

База позволяет удобнее (для меня) работать с данными и красиво их хранить (без лишних повторов, например)

**Идем в интернет**

Так как это проект про интернет, захотелось и результаты сделать интерактивными и чтобы они были в интернете. Поэтому в качестве итогового представления я выбрал Shiny-приложение с интерактивными графиками, чтобы можно было это выложить как сайт.

Немного возникли проблемы с библиотекой ```Wordcloud2```, потому что там все падало, если 

Приложение [здесь](https://evgenii-glazunov.shinyapps.io/a_plus_mama/)

1. График количества просмотров видео
2. Количество видео по месяцам
3. Длина видео по месяцам
4. Количество просмотров / лайков, количество лайков / дизлайков
5. Самые популярные теги
6. Главные комментаторы
7. Эмоджи в комментариях (скорее дата-арт, чем по делу)


Можно ли запустить это у себя? Да. Для этого:

1. Склонировать репозиторий
2. Скачать базу
3. Положить ее в папку a_plus_mama - папка с приложением
4. Установить пакеты
5. Открыть файлы ui.R и server.R и запустить приложение

**Библиотеки**

Какие специальные библиотеки используются в проекте:

- ```tuber``` - для взаимодействия с API YouTube
- ```wordcloud``` и ```wordcloud2``` - для вордклаудов
- ```ggplot2``` и ```plotly``` - для графиков
- ```RSQLite``` для работы с базой данных
- ```richfitz/remoji``` (guthub) - для работы с эмоджи
- ```shiny``` - для создания приложения
