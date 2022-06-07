# ДОМАШНЕЕ ЗАДАНИЕ 2. Анализ поездок посредством Spark DataFrame API

Папулин С.Ю. (papulin.study@yandex.ru)

### Наборы данных:
- Поездки (bikeshare): [данные](https://s3.amazonaws.com/tripdata/201902-citibike-tripdata.csv.zip) | [пояснения](https://www.citibikenyc.com/system-data)
- Кварталы NYC: [данные](https://data.cityofnewyork.us/api/geospatial/d3c5-ddgc?method=export&format=GeoJSON)

### Задача 1

- определите для каждой станции количество начала поездок и количество завершения поездок
- сопоставьте станции с кварталами города (zones) и определите суммы количества начала и завершения для каждого квартала
- выведите по убыванию количества поездок и 
- отобразите в виде картограмм (Choropleth).  

### ~~Задача 2~~
<del> 

- определите "важность" вершин графа поездок с использование PageRank
- выведите по убыванию и 
- отобразите на тепловой карте (HeatMap)

</del>

### Задача 3

- оцените дистанцию поездок (в метрах) на основе координат начальной и конечной станций (без учета поездок, завершившихся там же где и начались)
- выведите максимальное, среднее значение, стандартное отклонение и медиан

### Задача 4

- определите для каждой станции среднее количество начала поездок и количество завершения поездок:
    - в день 
    - утром (06:00-11:59), днем (12:00-17:59), вечером (18:00-23:59), ночью (00:00-05:59)
    - в среду и в воскресенье по временным диапазонам (см. выше)
- отобразите полученные данные для второго случая в виде тепловой временной карты (HeatMapWithTime) 