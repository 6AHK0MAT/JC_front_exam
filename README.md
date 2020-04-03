# JustControl.it
## Тестовое задание для фронтенд разработчика


## Дано
API предоставляет маркетинговые данные по клиенту (пример в файле [assets/data.json](assets/data.json)).

#### Описание формата данных
```js
//
// Данные представлены в виде таблицы значений и описания столбцов + суммы по столбцам
//
{
  // Строки данных
  "data": [ ... ],
  // Мета-информация
  "meta": {
    //
    // Описание колонок с полями:
    //   - Тип
    //       "type": "metric" | "entity", - метрика или сущность
    //   - Ключ столбца
    //       "key": string,
    //   - Заголовок столбца
    //       "title": string,
    //   - (для колонок "metric") Тип метрики (деньги, абсолютное значение или относительное):
    //       "metricType"?: "money" | "absolute" | "relative",
    //   - (для колонок "metric" с типом метрики "money') Валюта:
    //       "currency"?: string
    "columns": [ ... ],
    //
    // Суммы по столбцам
    "total": { ... }
  }
}
```

## Задача

Создать SPA на Angular, которое отображает на дашборде в удобном виде полученные через API данные.

#### Условия и приоритеты

Со стороны клиента:

- Клиенты хотят понимать, сколько они тратят на рекламу (колонка Spend), и каким получается доход (колонка Revenue): в срезе сущностей и в целом
- Клиенты хотят видеть, как другие метрики влияют на spend и revenue

С технической стороны:

- Нужна расширяемая архитектура приложения с заделом на будущее. Инструменты отображения будут развиваться и часто подстраиваться под нужды клиентов
- Задачу отображения/визуализации можно решать любыми средствами используя открытые библиотеки
