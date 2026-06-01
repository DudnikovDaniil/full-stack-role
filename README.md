# full-stack-role

Роль для интеграционного тестирования всего стека:
- ClickHouse
- Vector
- Lighthouse

---

##  Связанные репозитории

| Репозиторий | Ссылка |
|-------------|--------|
| **vector-role** | https://github.com/DudnikovDaniil/vector-role |
| **lighthouse-role** | https://github.com/DudnikovDaniil/lighthouse-role |
| **full-stack-role** | https://github.com/DudnikovDaniil/full-stack-role (текущий) |

---

##  Описание

Данная роль предназначена для **интеграционного тестирования** всего стека:
- Установка ClickHouse
- Установка Vector
- Установка Lighthouse (nginx)

Все три сервиса поднимаются в одном контейнере Docker, после чего проверяется их работоспособность.

---

##  Запуск тестов

### Подготовка окружения

```bash
cd ~/ansible-hw/roles/full-stack-role
python3 -m venv venv
source venv/bin/activate
pip install ansible molecule molecule-docker
```

### Запуск molecule теста

```bash
export ALLOW_BROKEN_CONDITIONALS=true
molecule test
```

---

##  Результаты тестирования

| Компонент | Проверка | Статус |
|-----------|----------|--------|
| ClickHouse | HTTP порт 8123 |  Успешно |
| Vector | Наличие бинарного файла |  Успешно |
| Lighthouse | HTTP порт 8080 |  Успешно |

---

##  Структура роли

```bash
full-stack-role/
├── molecule/
│   └── default/
│       ├── molecule.yml
│       ├── converge.yml
│       └── verify.yml
├── README.md
└── .gitignore
```

