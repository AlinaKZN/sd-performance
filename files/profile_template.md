# Шаблон профилирования запросов

## Топ-10 самых медленных запросов:

| Запрос | Среднее время выполнения (ms) | Количество вызовов | Количество неуспешных вызовов | 
|----------------------------------|-----------------------|--------------------|-------------------------------|
| GET /api/requests | 0.2                   | 1000               | 3                             |


## Метрики:
**Среднее время выполнения успешных запросов (ms)**
sum(http_server_requests_seconds_count{method="POST", uri="/api/requests", status=~"2.*"}))
/
http_requests_total{method="POST", url="/api/requests"}

**Количество запросов**
http_requests_total{method="POST", url="/api/requests"}

**Количество неуспешных вызовов**
http_errors{status="500", url="/api/requests"}


