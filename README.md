# api_yamdb
### API сервис который собирает отзывы пользователей на различные произведения.

Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий может быть расширен администратором.
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.
Произведению может быть присвоен жанр из списка предустановленных. Новые жанры может создавать только администратор.
Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку; из пользовательских оценок формируется усреднённая оценка произведения — рейтинг. На одно произведение пользователь может оставить только один отзыв. Добавлять отзывы, комментарии и ставить оценки могут только аутентифицированные пользователи.

## Настройка и запуск проекта:

Клонировать репозиторий на локальную машину:

```
git clone git@github.com:tychka89/api_final_yamdb.git
```

Перейти в репозиторий в командной строке:

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python -m venv env
```

```
source env/bin/activate
```

```
python -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```

## Документация доступна по ссылке: 
http://127.0.0.1:8000/redoc/

## Роли пользователей
Аноним — может просматривать описания произведений, читать отзывы и комментарии.

Аутентифицированный пользователь (user) — может читать всё, как и Аноним, дополнительно может публиковать отзывы и ставить рейтинг произведениям (фильмам/книгам/песенкам), может комментировать чужие отзывы и ставить им оценки; может редактировать и удалять свои отзывы и комментарии.

Модератор (moderator) — те же права, что и у Аутентифицированного пользователя плюс право удалять и редактировать любые отзывы и комментарии.

Администратор (admin) — полные права на управление проектом и всем его содержимым. Может создавать и удалять произведения, категории и жанры. Может назначать роли пользователям.

Суперюзер Django — должен всегда обладать правами администратора, пользователя с правами admin. Даже если изменить пользовательскую роль суперюзера — это не лишит его прав администратора. Суперюзер — всегда администратор, но администратор — не обязательно суперюзер.

## Доступные эндпоинты
```
Регистрация:
/api/v1/auth/signup/
```
```
Получение токена:
/api/v1/auth/token/
```
```
Получить список всех произведений:
/api/v1/titles/
```
```
Получение информации о произведении:
/api/v1/titles/{titles_id}/
```
```
Удалить произведение:
/api/v1/titles/{titles_id}/
```
## Примеры запросов

## Стек технологий: 
- Python 3.7,
- Django 2.2.16,
- djangorestframework 3.12.4,
- djangorestframework-simplejwt 4.7.2,
- Pillow 8.3.1,
- requests 2.26.0,

## Авторы:
