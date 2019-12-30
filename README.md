# Web-сервис, предоставляющий счёт текущих матчей
## Суть сервиса
Данный сервис предоставляет текущий счёт футбольных матчей.

## API
API веб-сервиса будет предоставляться посредством HTTP, а также реализовывать принципы REST.

### Запросы

#### Получить список матчей
Тип HTTP запроса: `GET`
Адрес: `/matches`
Возвращает коллекцию всех матчей.

#### Получить матч по id
Тип HTTP запроса: `GET`
Адрес: `/matches/:id`

#### Добавить матч
Тип HTTP запроса: `POST`
Адрес: `/add_match`

#### Изменение матча по id
Тип HTTP запроса: `PUT`
Адрес: `/matches/:id`

### Представления

#### Матч
Содержит `id` матча, имена команд - `name1` и `name2`, а также число забитых мячей для каждой из них - `score1` и `score2`.
    
    {
        "id":str;
        "name1":str;
        "name2":str;
        "score1":number;
        "score2":number;
    }
    
## Выполняемые требования REST

### Модель клиент-сервер
С помощью модели клиент-сервер будет произведено разграничение обязоностей клиента и сервера.

### Отсутствие состояния
Сервер не хранит состояние клиента и каждый пришедший на сервер запрос обрабатывается вне контекста пришедших с того же клиента запросов.

### Кэширование
Ответы на запросы на получение информации от матчах можно хранить в кэше до изменения запрашиваемых матчей.

### Единообразие интерфейса

#### Индентификация ресурсов

### Слои
