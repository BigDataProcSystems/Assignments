
# Домашнее задание 1. Создание скриптов и удаленный запуск

С.Ю. Папулин (papulin_bmstu@mail.ru)

### Содержание

- [Задание 1](#Задание-1)
- [Задание 2](#Задание-2)
- [Задание 3](#Задание-3)
- [Задание 4](#Задание-4)

## **Задание 1** 

Напишите программу на `python` для обработки `json` данных

1. Создайте каталог `dev/assignment` со следующей внутренней структурой:

```bash
assignment/
└── pyscripts
    ├── data
    └── output
```

2. Загрузите `json` файл, содержащий 100 отзывов, по ссылке: https://github.com/BigDataProcSystems/Practice/blob/master/hadoop/data/samples_100.json. Поместите его в каталог `pyscripts/data`.

```bash
assignment/
└── pyscripts
    ├── data
    │   └── samples_100.json
    └── output
```

3. Создайте `python` скрипт с именем `preprocessing.py`, который будет обрабатывать `json` файл (см. указания ниже в секции `TODO` кода программы)

    Замечание: 
    - Ниже шаблон содержания файла `preprocessing.py`
    - Первая строка нужна, если вы запускает скрипт вторым вариантом (см. ниже)

```python
#!/usr/bin/env python3

import json  # для работы с json (необходимо использовать функции этого модуля для парсинга)

def main():
    """Основная функция"""
    # TODO: Напишите программу на `python`, которая читает файл
    # построчно, парсит каждую строку, извлекает идентификатор 
    # продукта `asin` и рейтинг `overall` и записывает их в 
    # виде строки с запятой в качестве разделителя в файл `output.csv`.
    # Пример строки выходного файла: id,rating
    pass


if __name__ == "__main__":
    main()

```

Итоговая структура

```bash
assignment/
└── pyscripts
    ├── data
    │   └── samples_100.json
    ├── output
    └── preprocessing.py
```

3. Запустите скрипт и убедитесь, что всё работает правильно

Команда запуска скрипта

```bash
python3 preprocessing.py
```
или

```bash
# Замечание: убедитесь, что для скрипта установлен флаг executable
preprocessing.py
```

Итоговая структура

```bash
assignment/
└── pyscripts
    ├── data
    │   └── samples_100.json
    ├── output
    │   └── output.csv
    └── preprocessing.py   
```

4. Сохраните `preprocessing.py` в облачном хранилище (например, [filebin.net](https://filebin.net/)) и запишите ссылку или код (понадобится далее)

    для [filebin.net](https://filebin.net/) ссылка для загрузки будет: https://filebin.net/archive/YOUR_RANDOM_CODE/tar


## **Задание 2** 
Напишите скрипт на `bash` с именем `run.sh` для запуска `python` программы

1. Внутри файла напишите команды, которые будет выполнять скрипт

```bash
# TODO: 1. Запустите python script

# TODO: 2. Создайте soft link `output.csv` в каталоге `assignment/output` к выходному файлу `assignment/pyscripts/output/output.csv
```

2. Запустите скрипт и убедитесь, что всё работает правильно

Установите флаг `executable` и запустите команду

```
run.sh
```
или так

```bash
bash run.sh
```

В последнем случае можно не устанавливать флаг `executable`

3. Сохраните `run.sh` в облачном хранилище (например, [filebin.net](https://filebin.net/)) и запишите ссылку или код (понадобится далее)

    для [filebin.net](https://filebin.net/) ссылка для загрузки будет: https://filebin.net/archive/YOUR_RANDOM_CODE/tar

    Замечание: можно `preprocessing.py` и `run.sh` объединить в один архив с одной ссылкой

## **Задание 3** 

Напишите скрипт на `bash` с именем `startup.sh` для подготовки среды запуска программы

Внутри файла напишите команды, которые будет выполнять скрипт

```bash
# TODO: 1. Создайте каталоги в домашней директории:
#   - `assignment/output`
#   - `assignment/pyscripts/data`
#   - `assignment/pyscripts/output`
#   - `assignment/scripts`

# TODO: 2. Загрузите samples_100.json по ссылке (см. задание 1) 
# в каталог `assignment/pyscripts/data`

# TODO: 3. Загрузите python скрипт по ссылке (см. задание 2) 
# в каталог `assignment/pyscripts`

# TODO: 4. Загрузите bash скрипт по ссылке (см. задание 3) 
# в каталог `assignment/scripts`

# TODO: 5. Если скрипты упакованы в tar архив, то распакуйте 
# их, переместите в указанные каталоги и после этого удалите 
# архив
```

В итоге должна быть следующая структура каталога 

```bash
├── assignment
│   ├── pyscripts
│   │   ├── data
│   │   │   └── samples_100.json
│   │   ├── output
│   │   │   └── output.csv
│   │   └── preprocessing.py
│   └── scripts
└── startup.sh
```

## **Задание 4** 

Удаленный запуск скриптов

1. Создайте бесплатную виртуальную машину на одном из облачном провайдеров (AWS, Azure, Google Cloud, Heroku, DigitalOcean и пр.) с ОС Ubuntu
2. Создайте ключ доступа по SSH (обычно это в веб-интерфейсе провайдера)
3. Проверьте подключение к виртуальной машине посредством подключения по SSH
4. Загрузите скрипт `startup.sh` в домашнюю директорию удаленной виртуальной машины посредством `scp`
5. Запустите `startup.sh` скрипт на удаленной машине
6. Запустите `run.sh` скрипт на удаленной машине
7. Загрузите `assignment/output/output.csv` на локальную машину посредством `scp` и отобразите первые несколько строк


