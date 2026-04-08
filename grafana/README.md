# Домашнее задание к занятию 14 «Средство визуализации Grafana»

## Задание 1. Подключение Prometheus как источника данных

- Скриншот настроек источника данных:  
  `Screenshot_2026-04-07_16_02_17.png`
- Скриншот списка источников данных:  
  `Screenshot_2026-04-07_16_02_24.png`

## Задание 2. Создание дашборда с панелями

- Скриншот дашборда с метриками:  
  `Screenshot_2026-04-07_16_17_04.png`

**Использованные PromQL-запросы:**
- Загрузка CPU: `100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)`
- Load Average: `node_load1`, `node_load5`, `node_load15`
- Свободная RAM: `node_memory_MemFree_bytes`
- Свободное место на диске: `node_filesystem_avail_bytes{mountpoint="/", fstype!~"rootfs|tmpfs"}`

## Задание 3. Правила оповещения

- Порог на панели **Загрузка CPU**:  
  `Screenshot_2026-04-08_12_06_24.png`
- Порог на панели **Load Average**:  
  `Screenshot_2026-04-08_12_06_45.png`
- Порог на панели **Свободная RAM**:  
  `Screenshot_2026-04-08_12_07_04.png`
- Порог на панели **Свободное место на диске**:  
  `Screenshot_2026-04-08_12_07_21.png`
- Общий вид дашборда с активными алертами (красные зоны):  
  `Screenshot_2026-04-08_12_07_49.png`

## Задание 4. Экспорт дашборда в JSON

Файл с JSON-моделью дашборда:  
[`dashboard_listing.json`](dashboard_listing.json)
