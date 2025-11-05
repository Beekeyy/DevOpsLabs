# FastAPI + SQLite (async) — Чаты

Готовый проект на FastAPI с SQLite (aiosqlite), SQLAlchemy 2.0 (async) и Jinja2.

## Запуск

```bash
cd website
pip install -r requirements.txt
uvicorn app.main:app --reload
```

Откройте: http://127.0.0.1:8000

- Зарегистрируйтесь, войдите.
- Перейдите в «Чаты», создайте чат, приглашайте участников по email зарегистрированных пользователей.
- Сообщения и состав участников сохраняются в `app.db` (SQLite) рядом с приложением.

## Структура

```
website/
├─ app/
│  ├─ __init__.py
│  ├─ main.py
│  ├─ database.py
│  ├─ models.py
│  ├─ routes.py
│  └─ auth.py
├─ templates/
│  ├─ base.html
│  ├─ home.html
│  ├─ signin.html
│  ├─ signup.html
│  ├─ chats.html
│  ├─ chat_detail.html
│  └─ static/
│     └─ style.css
└─ requirements.txt
```

## Заметки

- Конфиг базы в `app/database.py`: `sqlite+aiosqlite:///app.db`.
- Таблицы создаются автоматически при старте (см. `lifespan` в `app/main.py`).
- Секреты (`SECRET_KEY` и JWT) находятся в явном виде для простоты и демонстрации — перенесите их в переменные окружения для продакшена.
