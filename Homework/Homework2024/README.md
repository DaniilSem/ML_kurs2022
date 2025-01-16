# Домашняя работа на 2024 год

В этом задании вы будете решать задачу прогнозирования количества посетителей ресторанов на основе данных временного ряда. Данные предоставлены двумя разными источниками:

Hot Pepper Gourmet (hpg): аналог Yelp, позволяет пользователям искать рестораны и бронировать столики онлайн.
AirREGI / Restaurant Board (air): система для управления бронированиями и кассой, похожая на Square.
Вы должны использовать данные о бронированиях, посещениях и другую информацию из этих источников, чтобы спрогнозировать количество посетителей ресторанов на конкретные даты. Данные для обучения охватывают период с 2016 года до апреля 2017 года, а тестовый набор включает последнюю неделю апреля и май 2017 года. Дни, когда рестораны были закрыты, не учитываются при оценке, и такие дни также исключены из тренировочного набора.

## Описание файлов:
Это реляционная база данных из двух систем. Каждый файл помечен префиксом (air_ или hpg_), чтобы указать источник. У каждого ресторана есть уникальные идентификаторы air_store_id и hpg_store_id, но не все рестораны представлены в обеих системах. Данные о широте и долготе указаны приблизительно, чтобы избежать идентификации ресторанов.

### `air_reserve.csv` — бронирования, сделанные через систему air.

`air_store_id` — идентификатор ресторана в системе air.

`visit_datetime` — время бронирования (дата посещения).

`reserve_datetime` — время создания бронирования.

`reserve_visitors` — количество посетителей по бронированию.

### `hpg_reserve.csv` — бронирования, сделанные через систему hpg.

`hpg_store_id` — идентификатор ресторана в системе hpg.

`visit_datetime` — время бронирования (дата посещения).

`reserve_datetime` — время создания бронирования.

`reserve_visitors` — количество посетителей по бронированию.

### `air_store_info.csv` — информация о ресторанах в системе air (название, район, координаты).

`air_store_id`

`air_genre_name`

`air_area_name`

`latitude, longitude` — координаты района ресторана.

### `hpg_store_info.csv` — информация о ресторанах в системе hpg (название, район, координаты).

`hpg_store_id`

`hpg_genre_name`

`hpg_area_name`

`latitude, longitude` — координаты района ресторана.

### `store_id_relation.csv` — сопоставление ресторанов, представленных в обеих системах.

`hpg_store_id`

`air_store_id`

### `air_visit_data.csv` — исторические данные о посещениях ресторанов в системе air.

`air_store_id`

`visit_date` — дата посещения.

`visitors` — количество посетителей в ресторане в указанный день. 

### `date_info.csv` — информация о календарных датах.

`calendar_date`

`day_of_week` — день недели.

`holiday_flg` — является ли день праздником в Японии.

## Что должно быть в ноутбуке

1. Чтение данных и разбиение на тестовую и обучающую выборку в соотношении 3:7
2. Анализ данных с графиками 
3. Выбор признаков и их кодирование
4. Анализ признаков
5. Обучение нескольких моделей и подбор гиперпараметров
6. Подсчет метрик
7. Анализ результатов

## Форма сдачи

1. Готовый ноутбук с исследованием
2. Ноутбук нужно показать и ответить на вопросы по нему
3. Сделать форк на гитхабе с данного репозитория и залить ноутбук в эту папку