# SDD — System Design Document

## 1. Архітектурний стиль
Система побудована за багатошаровою архітектурою:
1. **Presentation Layer** — вебінтерфейс або REST API-контролери.
2. **Business Layer** — сервіси з бізнес-логікою.
3. **Persistence Layer** — репозиторії для доступу до даних.
4. **Database Layer** — БД для користувачів, подій, категорій, бронювань.

## 2. Основні компоненти
| Компонент | Відповідальність |
|---|---|
| AuthController / AuthService | Реєстрація, логін, видача JWT |
| EventController / EventService | CRUD для подій |
| BookingController / BookingService | Бронювання місць |
| CategoryController / CategoryService | Керування категоріями |
| AdminController / AdminService | Адміністративні операції |

## 3. Модель даних
### User
- id
- fullName
- email
- passwordHash
- role

### Event
- id
- title
- description
- dateTime
- location
- capacity
- availableSeats
- categoryId
- organizerId

### Booking
- id
- userId
- eventId
- bookingDate
- status

### Category
- id
- name
- description

## 4. Основні сценарії взаємодії
### Сценарій 1. Реєстрація та вхід
1. Користувач надсилає форму реєстрації.
2. Сервіс перевіряє унікальність email.
3. Пароль хешується.
4. Дані зберігаються у БД.
5. При логіні користувач отримує JWT.

### Сценарій 2. Бронювання події
1. Користувач відкриває картку події.
2. Система перевіряє доступність місць.
3. Створюється запис бронювання.
4. `availableSeats` зменшується на 1.
5. Користувач отримує підтвердження.

## 5. Архітектурні правила
- Контролери не містять бізнес-логіку.
- Сервіси працюють через репозиторії.
- DTO використовуються для вхідних і вихідних даних API.
- Валідація виконується на межі системи.

## 6. Зв’язок із SSD
Всі компоненти реалізують вимоги з **SSD** через посилання на ідентифікатори FR-xx та NFR-xx.
