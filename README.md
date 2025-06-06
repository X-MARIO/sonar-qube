# SonarQube в Docker

Этот репозиторий содержит конфигурацию для запуска SonarQube с PostgreSQL в Docker.

## Требования

- Docker
- Docker Compose

## Структура файлов

- `docker-compose.yml` - конфигурация Docker Compose
- `.env` - переменные окружения для разработки
- `.env.prod` - переменные окружения для продакшена

## Запуск

### Разработка

```bash
docker-compose up -d
```

### Продакшен

```bash
docker-compose --env-file .env.prod up -d
```

## Доступ

После запуска SonarQube будет доступен по адресу: http://localhost:9000

### Учетные данные по умолчанию
- Логин: admin
- Пароль: admin (необходимо изменить при первом входе)

## Остановка

```bash
docker-compose down
```

## Безопасность

- Не коммитьте файлы `.env` и `.env.prod` в репозиторий
- Добавьте их в `.gitignore`
- Используйте сложные пароли в продакшен среде
- Ограничьте права доступа к файлам с переменными окружения:
  ```bash
  chmod 600 .env .env.prod
  ```

## Тома

Данные сохраняются в следующих томах:
- `sonarqube_data` - данные SonarQube
- `sonarqube_extensions` - расширения SonarQube
- `sonarqube_logs` - логи SonarQube
- `postgresql_data` - данные PostgreSQL #   s o n a r - q u b e  
 