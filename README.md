# Diana Bot - деплой на Railway

## Шаги

### 1. GitHub
- Создайте аккаунт на github.com если нет
- Создайте новый репозиторий (New repository)
- Загрузите три файла: main.py, requirements.txt, Procfile

### 2. Railway
- Зайдите на railway.app
- New Project -> Deploy from GitHub repo
- Выберите ваш репозиторий
- Railway автоматически задеплоит бота

### 3. Получите URL
- В Railway откройте Settings -> Domains -> Generate Domain
- Скопируйте URL вида: https://diana-bot-xxxx.up.railway.app

### 4. Gupshup webhook
- Зайдите в Gupshup -> ваш номер -> Callback URL
- Вставьте: https://diana-bot-xxxx.up.railway.app/webhook

### 5. Готово
- Отправьте сообщение на ваш WhatsApp номер
- Бот ответит через Diana

## Что делает бот
- Получает сообщение от гостя через Gupshup webhook
- Читает историю переписки из файла history.json
- Отправляет запрос в Groq с промптом Дианы
- Убирает <think> теги если модель их добавляет
- Отправляет ответ гостю через Gupshup
- Сохраняет историю для следующего сообщения

## Смена модели
В main.py строка:
GROQ_MODEL = "llama-3.3-70b-versatile"
Замените на любую другую модель Groq.
