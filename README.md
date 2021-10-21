# Ml_i_B_Course_Project

Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: [Датасет](https://www.kaggle.com/andrewmvd/trip-advisor-hotel-reviews)  
&copy; Алам, М.Х., Рю, В.-Дж., Ли, С., 2016. Совместное многоплановое отношение к теме: моделирование семантических аспектов для онлайн-обзоров. Информационные науки 339, 206–223.

Задача: Классифицировать отзыв об отеле на TripAdvisor по его содержанию. Бинарная классификация

Используемые признаки:

- Review (text)


Преобразования признаков: tfidf

Модель: logreg

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/AlSavva/Ml_i_B_Course_Project.git
$ cd Ml_i_B_Course_Project
$ docker build -t alsavva/review-sentiment-predict .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную [модель(распаковать архив)](https://github.com/AlSavva/ML_in_Business/blob/Model_Preparate/model.zip) (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models alsavva/review-sentiment-predict
```

### Переходим на [localhost:8181](http://localhost:8181/)
