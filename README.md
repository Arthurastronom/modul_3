Задание
Обработать данные об оценках ресторанов ( по данным 'www.tripadvisor.com')
Задача
Создать новые признаки для качественного предсказания данных

Данные:

    City: Город
    Cuisine Style: Кухня
    Ranking: Ранг ресторана относительно других ресторанов в этом городе
    Price Range: Цены в ресторане в 3 категориях
    Number of Reviews: Количество отзывов
    Reviews: 2 последних отзыва и даты этих отзывов
    URL_TA: страница ресторана на 'www.tripadvisor.com'
    ID_TA: ID ресторана в TripAdvisor
    Rating: Рейтинг ресторана

В ходе анализа были созданы следующие параметры
1. one hot для городов и кухонь
2. параметр для NaN 'Number_of_Reviews_isNAN', 'Cuisine_Style_NAN','Price_Range_NAN'
3. параметр популярности города popular_City как one lable encoding
4. количество представленных в ресторане кухонь number_Cuisine
5. параметр наличия популярного блюда/кухни в ресторане popular_Cuisine
6. one label encoding для расброса цены Price
7. параметр, показывающий отклонение между двумя последними оставленными отзывами diff. Вот здесь есть вариант для улучшения модули - пронормировать, чтобы все данные были одного порядка
8. chain_restor -  параметр показывающий входит ли данный ресторан в сеть ресторанов (1 и 0) - one label encoding
9. Ranking_NORM - параметр, который позвоялет выровнять данные между городом и их количеством ресторанов, так как в большом городе много ресторанов , соответственно и будет большая оценка

В итоге эволюция оценки MAE на случайном лесу 0,42 - 0,32 - 0,21

Как улучшить оценку:
1. Найти и убрать коррелированные признаки
2. Оставить наиболее значимые из оставшихся признаков
3. Осуществить процедуру стандартизации
