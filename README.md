# tmdb_api
Набор скриптов для создания локальной базы фильмов по каталогу themoviedb.org. Есть система рекомендаций.

## Как установить
Python3 должен быть уже установлен. 
Затем используйте `pip` (или `pip3`, есть есть конфликт с Python2) для установки зависимостей:
```bash
pip install -r requirements.txt
```

## Как использовать

### hello_api_TMDB.py
Скрипт для проверки ключа API. Запрашивает ввод ключа с клавиатуры. 
При успешном запросе выводит в консоль бюджет фильма, иначе - 'Invalid api key'.
```
>python hello_api_TMDB.py
Enter your api key v3:
100
```

### make_own_db.py
Скрипт для создания локальной базы информации о фильмах. По умолчанию - 1000 первых фильмов, сохраняет в корне скрипта как `MyFilmDB.json`.
Выводит процент выполнения в консоль. Время загрузки информации около 15-20 минут.
```
>python make_own_db.py
please, wait, this operation may take smth like 15-20 minutes
0.1 percent complete
0.2 percent complete
```

### search_in_db.py
Скрипт для поиска информаци о фильме в локальной базе по названию. Запрашивает ввод пути до базы данных, название фильма в консоли.
Выводит информацию о фильме, или 'File not found, sorry...' если фильм не найден.
```
>python search_in_db.py
Enter path to DataBase:
./MyFilmDB.json
Enter film to search for:
Dracula
film_info...
```

### find_similar.py
Скрипт для поиска похожих фильмов в локальной базе. 
Запрашивает ввод пути до базы данных, название фильма в консоли.
Если фильм есть в базе данных - выводит рекомендации к просмотру: список фильмов (по умолчанию 8), кторые наиболее близки по языку, жанру, бюджету.
Иначе выводит 'No such film in FilmsDB'.
```
>python find_similar.py
Enter path to DataBase:
./MyFilmDB.json
Enter film to search for:
Dracula
recommendation...
```

### tmdb_helpers.py
Вспомогательные функции для работы основных скриптов. Помогают получить ключ и сделать запрос к API.

### own_db_helpers.py
Вспомогательные функции для работы с локальной базой данных. Помогают загрузить данные в основные скрипты.





