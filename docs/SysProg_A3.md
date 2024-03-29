# Домашнее задание 3. Контейнеризация приложений посредством Docker

С.Ю. Папулин (papulin_bmstu@mail.ru)

### Содержание

- [Задача 1. Обработка команд сервером](#Задача-1.-Обработка-команд-сервером)
- [Задача 2. Использование контейнера с Redis для хранения данных](#Задача-2.-Использование-контейнера-с-Redis-для-хранения-данных)
- [Задача 3. Контейнеризация сервера](#Задача-3.-Контейнеризация-сервера)
- [Задача 4 [Опционально] Удаленное развертывание сервера](#Задача-4.-[Опционально]-Удаленное-развертывание-сервера)


## **Задача 1.** Обработка команд сервером

1. Напишите программу сервера, выполняющего приведенные далее в таблице команды. За основу возьмите сервер из ДЗ2. Для хранения данных используйте Python объекты.

|Команда|Описание|
|-|-|
|**`check`** `any-word`|Проверка на стоп-слово|
|**`show`** `requests`|Возвращает общее количество запросов к серверу|
|**`show`** `top-words`|Возвращает топ-10 количества проверок по словам. Формат: "слово количество"|
|**`show`** `top-client`|Топ-10 клиентов с наибольшим количеством запросов. Формат: "IP:PORT количество"|

2. Напишите программу клиента для взаимодействия с сервером и вывода результатов обработки команд сервером. За основу возьмите клиента из ДЗ2.

3. Запустите на локальном хосте и проверьте работоспособность сервера и клиента.

## **Задача 2.** Использование контейнера с Redis для хранения данных

Реализуйте программу из задачи 1, но с использованием контейнера с `Redis` для хранения количества запросов в соответствии с ранее обозначенными командами (см. семинар ["Контейнеризация приложений посредством Docker"
](https://github.com/BigDataProcSystems/Practice/blob/master/common/docs/sysprog_docker_basics.md))

⚠️ **Замечание.** Для хранения количества слов и клиентов можно использовать упорядоченное множество - sorted set (см. ["Redis Data types"](https://redis.io/topics/data-types))

## **Задача 3.** Контейнеризация сервера

1. Постройте `Docker` образ на базе `python:3.7-slim-buster` для запуска контейнера с сервером
2. Создайте `bridge` сеть с подсетью `10.0.1.0/16`
3. Запустите контейнер сервера и `Redis` так, чтобы они были в одной созданной ранее сети
4. Посредством клиента проверьте работоспособность сервера

## **Задача 4.** [Опционально] Удаленное развертывание сервера

1. Напишите и запустите скрип для установки `Docker` на удаленном узле
2. Загрузите локальный образ сервера на ваш приватный репозиторий `Docker Hub` (см. ["Docker Hub Quickstart"](https://docs.docker.com/docker-hub/))
3. Напишите скрип для развертывания сервера и `Redis` на удаленном узле с использованием ранее загруженного в `Docker Hub` образа
4. Проверьте работоспособность с использовать локального клиента

