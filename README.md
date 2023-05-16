# Yamdb API 

### Описание проекта
Реализация API для социальной сети Yamdb, собранье ревью на различные произведения

### Требования
* Python 3.7+

### Технологии
Python 3.7
Django 2.2.19

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
https://github.com/DeLaMia/api_yamdb
```

```
cd api_yamdb
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:
```
python3 manage.py makemigrations
```

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```
Импорт данных из csv файлов:
Если в дб уже есть данные, перед этим очистить ее
```
python3 manage.py delete_all
```

```
python3 manage.py load_db_csv
```

## Ресурсы API YaMDb
### Примеры запросов API
#### Запросы для регистрация нового пользователя (AUTH)
`http://127.0.0.1:8000/api/v1/auth/signup/`
`POST`: Получить код подтверждения на переданный email

`http://127.0.0.1:8000/api/v1/auth/token/`
`POST`: Получение JWT-токена в обмен на username и confirmation code



#### Управление пользователями (users)
`http://127.0.0.1:8000/api/v1/users/`
`GET`: Получение пользователей
`POST`: Создание пользователя
`PUT`: Обновление публикации
`PATCH`: Частичное обновление публикации
`DEL`: Удаление публикации

`http://127.0.0.1:8000/api/v1/users/{username}/`
`GET`: Получение пользователя по username
`PATCH`: Частичное обновление пользователя
`DEL`: Удаление пользователя

`http://127.0.0.1:8000/api/v1/users/me/`
`GET`: Получение данных своей учетной записи
`PATCH`: Частичное обновление своей учетной записи

#### Произведения, к которым пишут отзывы (определённый фильм, книга или песенка).
`http://127.0.0.1:8000/api/v1/titles/`
`GET`: Получение списка всех произведений
`POST`: Добавление произведения

`http://127.0.0.1:8000/api/v1/titles/{titles_id}/`
`GET`: Получение информации о произведении
`PATCH`: Частичное обновление информации о произведении
`DEL`: Удаление произведения

#### Категории (типы) произведений
`http://127.0.0.1:8000/api/v1/categories/`
`GET`: Получение списка всех категорий
`POST`: Добавление новой категории

`http://127.0.0.1:8000/api/v1/categories/{slug}/`
`DEL`: Удаление категории


#### Категории жанров
`http://127.0.0.1:8000/api/v1/genres/`
`GET`: Получение списка всех жанров
`POST`: Добавление жанра

`http://127.0.0.1:8000/api/v1/genres/{slug}/`
`DEL`: Удаление жанра

#### Отзывы
`http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/`
`GET`: Получение списка всех отзывов
`POST`: Добавление отзыва

`http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/{review_id}/`
`GET`: Полуение отзыва по id
`PATCH`: Частичное обновление отзыва по id
`DEL`: Удаление отзыва по id

#### Комментарии к отзывам
`http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/{review_id}/comments/`
`GET`: Получение списка всех комментариев к отзыву
`POST`: Добавление комментария к отзыву

`http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/{review_id}/comments/{comment_id}/`
`GET`: Получение комментария к отзыву
`PATCH`: Частичное обновление комментария к отзыву
`DEL`: Удаление комментария к отзыву

### Авторы
* https://github.com/DeLaMia
* https://github.com/alekpodyachev
* https://github.com/Kethave1
