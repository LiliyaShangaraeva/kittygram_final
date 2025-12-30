[![Main Kittygram workflow](https://github.com/LiliyaShangaraeva/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/LiliyaShangaraeva/kittygram_final/actions/workflows/main.yml)
# 🐱 KittyGram — Альбом, в котором можно хранить фотографии котиков.

## 🌟 Описание проекта

KittyGram — это **сеть для владельцев котов**, где можно:

- агружать фото своих котиков.
- Записывать их достижения.

---

## 🛠️ Технологический стек

| Компонент       | Технология               |
|------------------|--------------------------|
| Backend          | Python + Django + DRF    |
| Frontend         | React + Vite             |
| База данных      | PostgreSQL               |
| Сервер           | Nginx + Gunicorn         |
| Контейнеризация  | Docker + Docker Compose  |
| CI/CD            | GitHub Actions           |
| Хостинг          | Yandex Cloud             |

---


## Как развернуть проект

### 1. Клонируйте репозиторий

```bash
git clone https://github.com/LiliyaShangaraeva/kittygram_final.git
cd kittygram_final
```

### 2. Создайте файл .env

Скопируйте шаблон:

```bash
cp .env.example .env
```

Пример файла .env — замените значения на свои!

```bash
POSTGRES_DB=your_db_name
POSTGRES_USER=your_db_user
POSTGRES_PASSWORD=your_db_password
DB_HOST=db
DB_PORT=5432

SECRET_KEY=django-insecure-your-secret-key-here
DEBUG=true
ALLOWED_HOSTS=your-domain.com,localhost,127.0.0.1,gateway
```

> Не забудьте сгенерировать свой `SECRET_KEY` — можно через [Django Secret Key Generator](https://djecrety.ir/).

### 3. Запустите проект

```bash
sudo docker compose -f docker-compose.production.yml up -d --build
```

### 4. Выполните миграции и соберите статику

```bash
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
```

### Для запуска автоматического деплоя:

Запустите проект локально → проверьте, что всё работает → сделайте коммит → залейте в main

```bash
git add .
git commit -m "Исправил баг"
git push origin main
```

Это запустит автоматический деплой — и проект обновится на сервере.

### 5. Создайте суперпользователя (если нужно)

```bash
sudo docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser
```

### Автор:
[Лилия Шангараева](https://github.com/LiliyaShangaraeva)
