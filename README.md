# Kittygram - социальная сеть  для размещение фотографий котиков. Учебный проект Яндекс.Практикум.

## Описание проекта
Проект написан в рамках учебного курса по Python от Яндекс.Практикум.
Пользователи могут регистрироваться, загружать фотографии своих котов с кратким описанием, и смотреть котиков других пользователей. Основная задача  - обучение деплою проекта на сервер.

## Технологии

 - Python 3.9
 - Django==3.2.3
 - djangorestframework==3.12.4
 - Nginx
 - gunicorn

## Запуск проекта из исходников GitHub

Клонируем себе репозиторий: 

```bash 
git clone https://github.com/ingarbi/kittygram_final.git
```

Выполняем запуск:

```bash
sudo docker compose -f docker-compose.yml up
```

## После запуска: Миграции, сбор статистики

После запуска необходимо выполнить сбор статистики и миграции бэкенда. Статистика фронтенда собирается во время запуска контейнера, после чего он останавливается. 

```bash
sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py migrate

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py collectstatic

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend cp -r /app/collected_static/. /static/static/
```

И далее проект доступен на: 

```
http://localhost:9000/
```

## Остановка оркестра контейнеров

В окне, где был запуск **Ctrl+С** или в другом окне:

```bash
sudo docker compose -f docker-compose.yml down
```


## Примеры взаимодействия с приложением через API используя следующие пути:
1. /api/cats/ - принимает GET и POST, для добавления новых и получения существующих объектов
2. /api/achievements/ - принимает GET и POST, для добавления новых и получения существующих навыков домашнего питомца


## Автор
Arby - [GitHub](https://github.com/ingarbi)
