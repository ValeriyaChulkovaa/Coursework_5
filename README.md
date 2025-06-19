# 🚀 Трекер полезных привычек — Habit Tracker API

![Python](https://img.shields.io/badge/Python-3.12%2B-3776AB?logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-5.1%2B-092E20?logo=django&logoColor=white)
![DRF](https://img.shields.io/badge/DRF-3.15%2B-a30000?logo=django&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15%2B-4169E1?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-7.2%2B-DC382D?logo=redis&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-5.4%2B-37814A?logo=celery&logoColor=white)

API-сервис для создания и управления полезными привычками с напоминаниями в Telegram-боте.

## 🌟 Основные функции

- 🔐 JWT-аутентификация (регистрация/авторизация)
- 🛡️ Ролевая модель доступа:
  - Владелец и админ — полный доступ
  - Авторизованные пользователи — просмотр своих привычек
  - Публичные привычки доступны всем
- ⏰ Автоматические напоминания в Telegram
- 📊 Кастомные команды для загрузки тестовых данных
- 📚 Полная документация (Swagger/ReDoc)

## ⚙️ Установка

### Требования
- **Python 3.12+**
- **Redis Server 7.2+**
- **PostgreSQL 15+**
- **Poetry** для управления зависимостями

1. **Клонировать репозиторий**
```bash
git clone https://github.com/ValeriyaChulkovaa/Coursework_5.git
cd Project_5_Habit_Tracker
```

2. **Настройка окружения**
- Создать `.env` файл по примеру `.env.example`

3. **Установка зависимостей**
```bash
poetry install --no-root
poetry shell  # активация виртуального окружения
```

## 🚀 Запуск проекта

1. **Миграции базы данных**
```bash
python manage.py migrate
```

2. **Загрузка тестовых данных (опционально)**
```bash
python manage.py load_users
python manage.py load_habits
```

3. **Запуск Django-сервера**
```bash
python manage.py runserver
```

4. **Запуск Redis (в отдельном терминале)**
```bash
redis-server
```

5. **Запуск Celery (в отдельном терминале)**
```bash
celery -A config worker --beat --scheduler django --loglevel=info
```

## 📚 Документация
Доступна после запуска сервера:
- Swagger UI: [http://localhost:8000/swagger/](http://localhost:8000/swagger/)
- ReDoc: [http://localhost:8000/redoc/](http://localhost:8000/redoc/)

## 🧪 Тестирование
```bash
python manage.py test habits users --verbosity=2
coverage run --source='.' manage.py test
coverage report  # просмотр отчета
```
**Покрытие кода:** 90%

## 🛠 Технологии
- **Backend**: Django 5.1.5 + DRF 3.15.2
- **База данных**: PostgreSQL 15+
- **Брокер задач**: Redis 7.2+
- **Асинхронные задачи**: Celery 5.4.0
- **Аутентификация**: JWT (djangorestframework-simplejwt 5.4.0)
- **Документация**: drf-yasg 1.21.8
- **Линтеры**: flake8 + isort + black

## 👨💻 Автор
[Дмитрий] – [GitHub](https://github.com/Sweerx)