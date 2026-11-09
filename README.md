```
trueconf-siem-notifier/
│
├── .gitignore               # Исключение виртуального окружения, секретов (.env) и логов
├── README.md                # Документация проекта (этот файл)
├── requirements.txt         # Список внешних зависимостей (requests, python-dotenv, websockets)
├── main.py                  # Главный асинхронный координирующий цикл мониторинга
├── last_incident_time.txt   # Файл хранения временной метки (создается автоматически)
│
├── api_mp_vm/               # Модуль интеграции с MaxPatrol SIEM
│   ├── __init__.py
│   ├── mp_vm_variables.py   # Базовые константы подключения к SIEM и лимиты логов
│   ├── vm_authentication.py # Скрипт авторизации и получения Bearer-токена SIEM
│   └── mp_vm_incidents.py   # Сбор инцидентов, запрос связанных событий и форматирование текста
│
└── api_trueconf/            # Модуль интеграции с TrueConf Server
    ├── __init__.py
    ├── tc_authentication.py # Получение OAuth JWT-токена через REST API по паролю
    └── tc_messages.py       # Инициализация WebSocket и асинхронная отправка сообщений
```
