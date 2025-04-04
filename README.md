# Итоговый проект по теме `"Система продажей билетов на мероприятия"`
##### Выполняли студенты `ИКБО-62-23`
##### `Кузин Дмитрий`
##### `Саргсян Тигран`
##### `Скляр Матвей`

## Описание проекта
Проект направлен на реализацию системы, состоящей из бота и приложения для платформы IOS. Бот предоставляет функционал просмотра списка мероприятий и приобретения билетов на них. Приложение служит компаньоном администратора мероприятия, позволяя быстрее принимать участников на входе путем сканирования их билетов, а не ручной проверки регистрации. Основная цель – упростить процесс покупки билетов для пользователя и упросить контроль за посетителями мероприятия. Взаимодействие с пользователем на моменте покупки им билета обеспечивает удобный бот, созданный при помощи библиотеки aiogram для Python, хранение данных о пользователях и билетах происходит на бесплатном PostgreSQL хостинге Supabase. Приложение разработано при помощи XCode на языке Swift, использован классический скрипт для сканирования и расшифровки QR-кодов.


## Общая структура проекта

Система включает два основных компонента:

  • **Telegram-бот** — обеспечивает удобный интерфейс для пользователей и администраторов: позволяет просматривать мероприятия, покупать билеты, подтверждать регистрацию и управлять событиями.
 
  • **iOS-приложение** — используется администраторами мероприятий для сканирования QR-кодов билетов при входе.

Оба компонента используют единое хранилище данных, основанное на облачном сервисе **Supabase** (PostgreSQL).

---

## Telegram-бот

Бот реализован на языке **Python** с использованием фреймворка **aiogram**, предоставляющего асинхронный интерфейс для работы с Telegram API.

### Функциональность:

#### Для пользователей:
- Просмотр списка доступных мероприятий;
- Покупка и бронирование билетов;
- Получение QR-кода билета после покупки.

#### Для администраторов:
- Создание новых мероприятий;
- Просмотр списка купленных билетов;
- Подтверждение оплаты/бронирования билетов;

### Используемые библиотеки:

- **aiogram** — фреймворк для Telegram-ботов;
- **asyncpg** — асинхронный драйвер PostgreSQL;
- **supabase** — клиент для взаимодействия с Supabase API;
- **qrcode** — генерация QR-кодов для билетов;
- **python-dotenv** — загрузка конфигурации из `.env`;
- **pytz** — корректная работа с часовыми поясами.

### requirements.txt

```txt
aiogram
asyncpg
supabase
qrcode
python-dotenv
pytz
```

## Запуск проекта

```bash
cd dvijbot/ticketbot
python3 bot.py
```

### Установка зависимостей:

```bash
# Linux
sudo apt update && sudo apt -y python3 python3-pip
pip install -r requirements.txt

# MacOS
brew install python3 && brew install python3-pip
pip install -r requirements.txt
```

