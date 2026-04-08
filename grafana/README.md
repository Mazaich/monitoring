# Домашнее задание к занятию 14 «Средство визуализации Grafana»

## Задание 1. Подключение Prometheus в качестве источника данных

- Настройки источника данных:  
  ![Datasource config](Screenshot_2026-04-07_16_02_17.png)
- Список источников данных:  
  ![Data Sources list](Screenshot_2026-04-07_16_02_24.png)

## Задание 2. Создание дашборда с панелями

- Дашборд с метриками:  
  ![Dashboard metrics](Screenshot_2026-04-07_16_17_04.png)

**Использованные запросы PromQL:**

- Загрузка ЦП: `100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)`
- Средняя загрузка: `node_load1`, `node_load5`, `node_load15`
- Свободная оперативная память: `node_memory_MemFree_bytes`
- Свободное место на диске: `node_filesystem_avail_bytes{mountpoint="/", fstype!~"rootfs|tmpfs"}`

## Задание 3. Правила оповещения

- Порог на панели Загрузка ЦП:  
  ![CPU alert](Screenshot_2026-04-08_12_06_24.png)
- Порог на панели Средняя нагрузка:  
  ![Load alert](Screenshot_2026-04-08_12_06_45.png)
- Порог на панели Свободная оперативная память:  
  ![RAM alert](Screenshot_2026-04-08_12_07_04.png)
- Порог на панели Свободное место на диске:  
  ![Disk alert](Screenshot_2026-04-08_12_07_21.png)
- Общий вид дашборда с активными оповещениями (красные зоны):  
  ![Dashboard alerts](Screenshot_2026-04-08_12_07_49.png)

## Задание 4. Экспорт дашборда в JSON

- Файл с JSON-моделью дашборда:  
  [`dashboard_listing.json`](dashboard_listing.json)
