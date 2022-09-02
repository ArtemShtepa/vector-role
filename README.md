Vector-role
=========

Предназначена для установки на операционные системы под управлением **SystemD** сервиса **Vector** и базовое конфигурирование отслеживания изменения LOG файлов с отправкой изменений в **Clickhouse**

Переменные
----------

- **vector_version** - Версия используемого ПО Vector. По умолчанию **0.23.0**

- **vector_test_dir** - Директория отслеживания LOG файлов.

- **clickhouse_host**: - Хост Clickhouse для выгрузки метрики.

- **clickhosue_port**: - Порт Clickhouse для выгрузки метрики.

- **clickhosue_user**: - Пользователь Clickhouse с правами на запись.

- **clickhosue_password**: - Пароль авторизуемого пользователя Clickhouse.


Пример использования
--------------------

```yaml
- name: Install and configure Vector
  hosts: vector
  become: true
  vars:
    vector_test_dir: "/var/log/test"
    clickhouse_host: hostvars['clickhouse']['ansible_host']
  roles:
    - vector_role
```
