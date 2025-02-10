# Тема 12. Домашня робота

## Опис

У цьому домашньому завданні потрібно доопрацювати REST API-застосунок із попереднього домашнього завдання.

## Технічний опис завдання
  - Створення документації за допомогою **Sphinx**. За допомогою **Sphinx** створіть документацію для вашого застосунку. Для цього додайте в основних модулях до необхідних функцій і методів класів рядки **docstrings**.
  - Модульне тестування. Покрийте модульними тестами модулі репозиторію вашого застосунку.
  - Інтеграційне тестування. Покрийте інтеграційними тестами маршрути вашого застосунку, використовуючи фреймворк **pytest**.
  - Покриття тестами понад 75%. Покрийте ваш застосунок тестами на понад 75%. Для контролю використовуйте пакет **pytest-cov**.
  - Реалізація кешування з **Redis**. Реалізуйте механізм кешування за допомогою бази даних **Redis**. Виконайте кешування поточного користувача під час авторизації, щоб функція **get_current_user** брала користувача з кешу і не зверталася щоразу до бази даних.
  - Механізм скидання пароля. Реалізуйте механізм скидання пароля для застосунку **REST API**.
  - Ролі користувачів і доступ. Реалізуйте для користувачів застосунку доступ за ролями: **«user»** та **«admin»**. Забезпечте, щоб тільки адміністратори могли самостійно змінювати свій аватар за замовчуванням.

### Основні команди
```
    pip install poetry
    poetry install
    poetry shell
    poetry add sphinx -G dev
    make html
    docker compose up --build
    pytest --cov=src tests/ --cov-report=html
```
### FastAPI
#### auth
```bash
    POST /api/auth/register (User registration)
```
```bash
    POST /api/auth/login (User login)
```
```bash
    GET /api/auth/confirmed_email/{token} (Email confirmation)
```
```bash
    POST /api/auth/request_email (Request email)
```
```bash
    POST /api/auth/update_password (Update password)
```
```bash
    GET /api/auth/confirm_update_password/{token} (Password confirmation)
```

#### contacts
```bash
    GET /api/contacts/birthdays (Get upcoming birthdays)
```
```bash
    GET /api/contacts/ (Get all contacts)
```
```bash
    POST /api/contacts/ (Create new contact)
```
```bash
    GET /api/contacts/{contact_id} (Get exact contact)
```
```bash
    PUT /api/contacts/{contact_id} (Update exist contact)
```
```bash
    DELETE /api/contacts/{contact_id} (Delete exist contact)
```

#### users
```bash
    GET /api/users/me (requires authentication)
```
```bash
    PATCH /api/users/avatar (Update User avatar)
```

#### healthchecker
```bash
    GET /api/healthchecker (Checking App Health)
```
