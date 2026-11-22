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

