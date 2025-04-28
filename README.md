# Yatube API

## Описание

Yatube API - это RESTful API для социальной сети блогов. Проект предоставляет возможность:
- Создавать и управлять постами
- Добавлять комментарии к постам
- Подписываться на других пользователей
- Аутентифицироваться с помощью JWT-токенов

API полностью документировано и доступно по адресу `/redoc/` после запуска проекта.

## Установка

1. Клонируйте репозиторий:
```bash
git clone <ссылка на репозиторий>
cd api_final_yatube

2. Создайте и активируйте виртуальное окружение:
python -m venv venv
source venv/bin/activate  # для Linux/MacOS
venv\Scripts\activate     # для Windows
3. Установите зависимости:
pip install -r requirements.txt
4. Примените миграции:
python manage.py migrate
5. Запустите сервер:
python manage.py runserver

Примеры запросов
Получение JWT-токена

POST /api/v1/jwt/create/
Content-Type: application/json

{
    "username": "ваш_username",
    "password": "ваш_password"
}

Получение списка постов

GET /api/v1/posts/
Authorization: Bearer ваш_токен

Создание поста

POST /api/v1/posts/
Authorization: Bearer ваш_токен
Content-Type: application/json

{
    "text": "Текст нового поста",
    "group": 1  # необязательное поле
}

Подписка на пользователя

POST /api/v1/follow/
Authorization: Bearer ваш_токен
Content-Type: application/json

{
    "following": "username_пользователя"
}

Получение списка комментариев

GET /api/v1/posts/1/comments/
Authorization: Bearer ваш_токен

Полная документация API доступна после запуска проекта по адресу:
http://localhost:8000/redoc/