# Групповой проект Yamdb

## Описание 

Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка». 

Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

Произведению может быть присвоен жанр. Новые жанры может создавать только администратор. Читатели оставляют к произведениям текстовые отзывы и выставляют произведению рейтинг (оценку в диапазоне от одного до десяти). Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число); из пользовательских оценок формируется усреднённая оценка произведения — рейтинг (целое число). На одно произведение пользователь может оставить только один отзыв.

## Шаблон наполнения .env файла

DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД 

## Команды для запуска приложения в контейнерах:

docker-compose up (-d) - разворачивает docker-compose проект

docker-compose stop - остановка контейнеров

winpty docker-compose exec web python manage.py migrate

winpty docker-compose exec web python manage.py createsuperuser

winpty docker-compose exec web python manage.py collectstatic --no-input 

## Команды для заполнения базы данными

sudo docker-compose exec web python manage.py loaddata fixtures.json

### Над проектом работали:

- Денис Кудаков | [Github](https://github.com/DK0894) | Разработчик, разработка части, касающейся управления пользователями (Auth и Users): система регистрации и аутентификации, права доступа, работа с токеном, система подтверждения через e-mail
- Галиева Ляйсан | [Github](https://github.com/killyourasta) | Разработчик, написание части с категориями (Categories), жанрами (Genres) и произведениями (Titles): моделями, представлениями и эндпойнтами для них.
- Шелепин Дмитрий | [Github](https://github.com/oladushkin) | Тимлид, написание части с отзывами (Review) и комментариями (Comments): описание модели, представления, настройка эндпойнтов, определение прав доступа для запросов. Рейтинги произведений.

### Статус workflow

![status workflow](https://github.com/DK0894/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

### Адрес сервера

1) http://51.250.106.249/api/v1/
2) http://51.250.106.249/admin
3) http://51.250.106.249/redoc

### MIT License

Copyright (c) 2022 Denis Kudakov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.