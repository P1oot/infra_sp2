# infra_sp2

## Описание.

Данный проект позволяет делать обзоры и давать оценку различным произведенияя, оставлять комментарии.
Проек сделан с контейнеризацией, что позволяет не беспокоиться о совместимости.

## Установка.

Клонировать репозиторий и перейти в него в командной строке:
`git clone git@github.com:P1oot/infra_sp2.git`
`cd infra_sp2`

Создать и заполнить файл .env:
`cd infra`
`touch .env`
`nano .env`
*Пример заполнения .env ниже

Запустите docker-compose:
`docker-compose up -d`

Выполнить миграции:
`docker-compose exec web python manage.py migrate`

Создать суперпользователя:
`docker-compose exec web python manage.py createsuperuser`

Подключить статику:
`docker-compose exec web python manage.py collectstatic --no-input`

Остановить контейнеры можно комадой:
`docker-compose stop`

## *Пример заполнения .env
`DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql`
`DB_NAME=postgres # имя базы данных`
`POSTGRES_USER=postgres # логин для подключения к базе данных`
`POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)`
`DB_HOST=db # название сервиса (контейнера)`
`DB_PORT=5432 # порт для подключения к БД`

## Примеры запросов.

"Регистрация нового пользователя": "http://127.0.0.1:8000/api/v1/auth/signup/"

"Получение JWT-токена": "http://127.0.0.1:8000/api/v1/auth/token/"

"Обращение к категориям": "http://127.0.0.1:8000/api/v1/categories/"

"Обращение к жанрам": "http://127.0.0.1:8000/api/v1/genres/"

"Обращение к произведениям": "http://127.0.0.1:8000/api/v1/titles/"

"Обращение к отзывам": "http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/"

"Обращение к комментариям": "http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/{review_id}/comments/"

### Авторы:

**Бердинских Даниил** https://github.com/P1oot

**Крицина Анна** https://github.com/cistellula

**Куликов Андрей** https://github.com/Kulikov1
