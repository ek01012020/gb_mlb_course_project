# python-flask-docker
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные взяты с сайта https://play.google.com/store/apps/details?id=ru.homecredit.mycredit&showAllReviews=true
Отзывы спарсены с помощью scrapy

Задача: предсказать по тексту отзыва, полезен ли он, и стоит ли техподдержке и разработчикам обращать на него внимание. 
Классификация проводится по полю content. Бинарная классификация

Используемые признаки:

- content (text)

Преобразования признаков: tfidf

Модель: logreg

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/ek01012020/gb_mlb_course_project.git
$ cd gb_mlb_course_project
$ docker build -t elena/gb_mlb_course_project .
```

### Запускаем контейнер

Модель хранится в /app/models
```
$ docker run -d -p 8180:8180 -p 8181:8181 elena/gb_mlb_course_project
```

### Переходим на localhost:8181
