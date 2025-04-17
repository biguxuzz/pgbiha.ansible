# Ansible BiHA Postgres Pro Enterprise Cluster

Этот Ansible проект автоматизирует установку и настройку кластера BiHA Postgres Pro Enterprise с тремя ролями: LEADER, FOLLOWER и REFEREE.

## Требования

- Ansible 2.9+
- Доступ к серверам по SSH
- Root права на серверах
- Поддерживаемые ОС: Ubuntu, Debian, Astra Linux

## Структура проекта

```
.
├── inventory.yml           # Инвентарь с определением хостов
├── site.yml               # Основной плейбук
├── group_vars/            # Переменные для групп
│   └── biha_cluster.yml   # Переменные кластера
└── roles/
    ├── common/            # Общие задачи
    ├── postgrespro/       # Установка Postgres Pro
    └── biha/              # Настройка BiHA
```

## Использование

1. Настройте переменные в `group_vars/biha_cluster.yml`
2. Запустите плейбук:
   ```bash
   ansible-playbook -i inventory.yml site.yml
   ```

## Важные замечания

- Перед запуском убедитесь, что все серверы доступны
- Измените пароль `biha_replication_password` на безопасный
- Проверьте правильность IP-адресов в `inventory.yml` 