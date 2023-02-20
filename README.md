### API YATUBE

### Описание:
Учебный проект социальной сети.
Доступные функции:
  -Создание записей;
  -Создание комментариев к записям;
  -Подписка на пользователей.

### Как запустить проект:
Клонировать репозиторий:
```git@github.com:Glebchik57/api_final_yatube.git```

```cd api_final_yatube```

Cоздать и активировать виртуальное окружение:

```python3 -m venv env```

```source env/bin/activate```


```python3 -m pip install --upgrade pip```

Установить зависимости из файла requirements.txt:

```pip install -r requirements.txt```

Выполнить миграции:

```python3 manage.py migrate```

Запукстить проект:

```python3 manage.py runserver```

### Примеры запросов и ответов. 

##### Получение GET запроса .../api/v1/posts/ 

Пример ответа:

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```
Выполнение POST запроса постов .../api/v1/posts/ 
```json
{
  "text": "string",
  "image": "string",
  "group": 0
}
``` 
Пример ответа: 
```json
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
##### Получение всех комментариев к публикации через GET запрос .../api/v1/posts/{post_id}/comments/ 

Пример ответа: 
```json
[
  {
    "id": 0,
    "author": "string",
    "text": "string",
    "created": "2019-08-24T14:15:22Z",
    "post": 0
  }
]
```
#####  Добавление нового комментария к публикации через POST .../api/v1/posts/{post_id}/comments/ 

Пример ответа: 

```json
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
} 
```
##### Получение информации о сообществе по id через GET запрос .../api/v1/groups/id/ 

Пример ответа: 
```json
{
  "id": 0,
  "title": "string",
  "slug": "string",
  "description": "string"
}
```
##### GET-запрос возвращает все подписки пользователя, сделавшего запрос GET .../api/v1/follow/

Пример ответа: 
```json
[
  {
    "user": "string",
    "following": "string"
  }
]
```
##### Подписка пользователя от имени которого сделан запрос на пользователя переданного в теле запроса POST .../api/v1/posts/{post_id}/comments/ 

Пример ответа: 

```json
{
  "user": "string",
  "following": "string"
}
```
