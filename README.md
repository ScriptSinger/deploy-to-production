# Скрипт развертывания

Следующий cкрипт используется для развертывания веб-проекта на удаленном сервере через SSH.

## Конфигурация

Скрипт определяет следующие переменные, которые будут использоваться в процессе развертывания:

- `SERVER`: адрес удаленного сервера.
- `PROJECT_DIRECTORY`: каталог на сервере, где будет расположен проект.
- `REPOSITORY`: URL репозитория, содержащего проект.
- `TOKEN`: токен, используемый для взаимодействия с Telegram Bot API.
- `API_KEY`: ключ, используемый для взаимодействия с Stripe API.

## Процесс развертывания

1. Подключиться к удаленному серверу по SSH
2. Перейдти в каталог проекта на сервере.
3. Проверить, не клонирован ли уже репозиторий:
   - Если нет, клонировать репозиторий, создать файл `.env.local`, содержащий необходимые переменные окружения и сделать символическую ссылку.
   - Если да, обновить репозиторий последними изменениями из ветки `main`.
4. Установить зависимости проекта с помощью Composer.
5. Очистить production cache.
6. Отключиться от сервера.
