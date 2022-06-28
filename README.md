# DummyAPI
Здесь представленно описание тестирования проекта DummyAPI/

## Оглавление
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
[![Майнд-Карта](https://drive.google.com/file/d/1dA2Dw37BO-E62zNfyxuSkRFX5b0n4_nn/view?usp=sharing)

