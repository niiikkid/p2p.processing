# P2P Processing Platform

[![PHP](https://img.shields.io/badge/PHP-8.3%2B-777BB4?logo=php&logoColor=white)](https://www.php.net/)
[![Laravel](https://img.shields.io/badge/Laravel-11-FF2D20?logo=laravel&logoColor=white)](https://laravel.com/)
[![Vue.js](https://img.shields.io/badge/Vue.js-3-4FC08D?logo=vuedotjs&logoColor=white)](https://vuejs.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8%2B-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Redis](https://img.shields.io/badge/Redis-6%2B-DC382D?logo=redis&logoColor=white)](https://redis.io/)

Веб-платформа P2P-процессинга для приёма и выплаты фиатных платежей. Она объединяет мерчантов и трейдеров, поддерживает P2P-операции, учёт балансов и вознаграждений в USDT, а также API-интеграции для внешних систем.

> Репозиторий содержит серверную часть и веб-интерфейс платформы. Мобильное приложение для автоматизации работы трейдера находится в отдельном репозитории: [p2p-app](https://github.com/niiikkid/p2p-app).

## Возможности

- Приём платежей и управление выплатами.
- Личный кабинет для мерчанта, трейдера, поддержки, тимлида и администратора.
- P2P-заказы, платёжные реквизиты, статусы операций и споры.
- Кошельки, балансы, пополнения и вывод средств в USDT.
- API для мерчантов, H2H-интеграций, выплат, выписок и вебхуков.
- Управление платёжными шлюзами, валютами, лимитами и антифрод-правилами.
- Уведомления и интеграция с Telegram.
- Статистика, журналы операций и экспорт данных.

## Стек

| Направление | Технологии |
| --- | --- |
| Backend | PHP 8.3+, Laravel 11 |
| Frontend | Vue 3, Inertia.js, Vite |
| Интерфейс | Tailwind CSS, DaisyUI |
| Хранение и очереди | MySQL 8+, Redis 6+, Laravel Horizon |
| Наблюдаемость | Laravel Telescope, Laravel Pulse, Sentry |

## Требования

- PHP 8.3+ с расширениями `bcmath`, `gmp`, `mbstring`
- Composer
- Node.js 18+ и npm
- MySQL 8+
- Redis 6+

## Быстрый старт

1. Клонируйте репозиторий и установите зависимости:

   ```bash
   git clone git@github.com:niiikkid/p2p.processing.git
   cd p2p.processing
   composer install
   npm install
   ```

2. Создайте локальный файл окружения и настройте подключение к MySQL, Redis и внешним сервисам:

   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

3. Выполните миграции и соберите фронтенд:

   ```bash
   php artisan migrate
   npm run build
   ```

4. Запустите приложение, очередь и сборщик фронтенда в отдельных терминалах:

   ```bash
   php artisan serve
   php artisan horizon
   npm run dev
   ```

> Не добавляйте `.env` в Git: он содержит ключи и параметры подключений. Для локальной разработки используйте значения из `.env.example` как шаблон.

## API и интеграции

Платформа предоставляет защищённые API для:

- работы с заказами мерчанта;
- H2H-операций и споров;
- баланса и вывода средств;
- создания и отслеживания выплат;
- выписок по заказам и выплатам;
- приёма вебхуков от внешних сервисов и мобильного приложения.

Документация по интеграции отображается в интерфейсе платформы для авторизованных пользователей с соответствующими правами.

## Связанные проекты

- [Мобильное приложение для автоматизации — p2p-app](https://github.com/niiikkid/p2p-app)
- [Криптопроцессинг — payment.system](https://github.com/niiikkid/payment.system)

## Скриншоты

| | |
| --- | --- |
| ![Интерфейс платформы — экран 1](./1.png) | ![Интерфейс платформы — экран 2](./2.png) |

## Лицензия

Условия использования и распространения проекта пока не опубликованы. Перед использованием кода за пределами проекта согласуйте их с владельцем репозитория.
