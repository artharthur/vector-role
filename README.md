# Vector Role

Ansible роль для установки и настройки Vector — агента для сбора и отправки логов.

## Требования

- Ubuntu 20.04/22.04
- Ansible 2.10+

## Переменные

### defaults/main.yml (можно переопределить)

| Переменная | Описание | По умолчанию |
|------------|----------|--------------|
| `vector_version` | Версия Vector | `0.41.1` |
| `vector_install_dir` | Директория установки | `/opt/vector` |
| `vector_config_dir` | Директория конфигов | `/etc/vector` |

### vars/main.yml (внутренние)

| Переменная | Описание |
|------------|----------|
| `vector_config` | Конфигурация sources и sinks |

### Внешние переменные

| Переменная | Описание | По умолчанию |
|------------|----------|--------------|
| `clickhouse_host` | IP адрес ClickHouse сервера | `127.0.0.1` |

## Пример использования
```yaml
- hosts: vector
  roles:
    - vector
  vars:
    clickhouse_host: "192.168.1.68"
```

## Лицензия

MIT

## Автор

Arthur Ishmakov
