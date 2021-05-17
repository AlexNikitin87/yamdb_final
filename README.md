# api_yamdb
REST API для сервиса YaMDb — базы отзывов о фильмах, книгах и музыке.
## Описание
API для сервиса YaMDb. Позволяет работать со следующими ресурсами:

Ресурс AUTH(Регистрирует, отправляет токен по почте)

Ресурс USERS(Получить список всех пользователей, создание пользователя, получить пользователя по username, изменить данные пользователя по username, удалить пользователя по username, получить данные своей учетной записи, изменить данные своей учетной записи)

Ресурс TITLES(Получить список всех объектов, создать произведение для отзывов, информация об объекте, обновить информацию об объекте, удалить произведение)

Ресурс CATEGORIES(Получить список всех категорий, создать категорию, удалить категорию)

Ресурс GENRES(Получить список всех жанров, создать жанр, удалить жанр)

Ресурс REVIEWS(Получить список всех отзывов, создать новый отзыв, получить отзыв по id, частично обновить отзыв по id, удалить отзыв по id)

Ресурс COMMENTS(Получить список всех комментариев к отзыву по id, создать новый комментарий для отзыва, получить комментарий для отзыва по id, частично обновить комментарий к отзыву по id, удалить комментарий к отзыву по id)

## Запуск 
Для запуска запустите следующие команды:
  $ docker-compose up --build
При первом запуске необходимо выполнить миграции:
  $ docker-compose exec web python manage.py migrate

## Создание суперпользователя
  docker-compose exec web python manage.py shell
   from users.models import User
   User.objects.create_superuser(username='TestUser', email='admin@yamdb.fake', password='1234567')


## Загрузка тестовых данных 
 $ docker-compose exec web python manage.py loaddata fixtures.json   

## Бейдж
yamdb_final
[![Yamdb workflow](https://github.com/AlexNikitin87/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)](https://github.com/AlexNikitin87/yamdb_final/actions/workflows/yamdb_workflow.yml)
## Деплой
http://84.201.176.88 

