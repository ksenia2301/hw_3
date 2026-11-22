Домашнее задание №3

Сборка Docker-образа:

```powershell
docker build -t hw3-app .
```

Запуск контейнера:

```powershell
docker run -d --name hw3-container -p 8080:8000 -e GREETING="Привет! Docker работает!" -e STORAGE=sqlite hw3-app
```

Приложение доступно по адресу: http://localhost:8080/

Проверка работы:

- `GET /` — просмотр счётчика.
- `POST /increment` — увеличение счётчика на 1.
- `GET /healthz` — проверка работы сервера.
- `GET /readyz` — проверка хранилища.

Просмотр логов

```powershell
docker logs hw3-container
```

Запуск через Docker Compose (6 баллов)

Создала файл `docker-compose.yml` для запуска приложения через Docker Compose.

Настройки хранятся в `.env`, пример настроек — в `.env.example`:
```env
APP_PORT=8080
GREETING=Привет! Docker работает!
```

Запуск приложения:
docker compose up -d --build
```

Для хранения данных использую `my_data`, поэтому счётчик сохраняется после пересоздания контейнера.

Остановка приложения:
docker compose down
```

Проверила сохранение данных: после повторного запуска значение счётчика осталось равным `1`.