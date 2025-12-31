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
| `vector_architecture` | Архитектура (auto) | `x86_64` или `aarch64` |

### Внешние переменные

| Переменная | Описание | По умолчанию |
|------------|----------|--------------|
| `clickhouse_host` | IP адрес ClickHouse сервера | `127.0.0.1` |

## Тестирование

### Molecule

Роль содержит два сценария тестирования:

**default** — тестирование в Docker контейнере:
```bash
molecule test
```

**compatibility** — облегчённый сценарий для tox:
```bash
molecule test -s compatibility
```

### Tox

Запуск тестов через tox:
```bash
tox
```

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
