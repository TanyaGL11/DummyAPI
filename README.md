# DummyAPI
Здесь представленно описание тестирования проекта DummyAPI/

## Оглавление
0. [Описание проекта](#Описание-проекта)
1. [POST](#POST)
    1. GET /post (Get List)
    2. POST /post/create
2. [Майнд-карта](#Майнд-карта)
3. [Коллекции POSTMAN](#Коллекции-POSTMAN)

## Описание проекта
https://dummyapi.io/ представляет собой сервис для тестирования API. Для выполнения запросов неоходимо app-id, который генерируется автоматически после регистрации на сайте. В качестве тестирования был взят объект **POST**

### POST

#### GET /post (Get List)
Возвращает список публикаций отсортированных по дате создания:
- доступны созданные query params
- доступны query params разбиения на страницы

**Response Body**

**List**
Структура данных для всех ответов, которые возвращают массив данных.
```js
{
data: Array(Model)
total: number(total items in DB)
page: number(current page)
limit: number(number of items on page)
}
```
**Post Preview**
```js
{
id: string(autogenerated)
text: string(length: 6-50, preview only)
image: string(url)
likes: number(init value: 0)
tags: array(string)
publishDate: string(autogenerated)
owner: object(User Preview)
}
```
#### POST /post/create (Create Post)
Создаtn новый пост пользователя. Возвращает информацию о публикации.
(обязательны для заполнения поля owner и post )

**Request Body**
```js
{
text: string(length: 6-50, preview only)
image: string(url)
likes: number(init value: 0)
tags: array(string)
owner: string(User id)
}
```
## Майнд-Карта
Данная МК представляет собой наборн тестов для тестирования POST. Подробная проверка расписана для **Get List** и **Create Post**.
![Майнд-Карта](https://github.com/TanyaGL11/DummyAPI/blob/main/DummyAPI.png "МК")
Также майнд-карту можно [скачать](https://github.com/TanyaGL11/DummyAPI/blob/main/DummyAPI.xmind)

## Коллекция POSTMAN
В данной коллекции представлялен основной набор автотестов для регрессионного тестирования POST.

Коллекцию можно [скачать](https://github.com/TanyaGL11/DummyAPI/blob/main/POST.postman_collection.json)

Environment можно [скачать](https://github.com/TanyaGL11/DummyAPI/blob/main/Local.postman_environment.json)
