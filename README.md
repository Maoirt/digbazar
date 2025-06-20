# Дигрикс
Дигрикс - платформа электронной коммерции, предназначенная для авторов, которые с помощью этой платформы могут продавать свои цифровые продукты.

Составляющие:
1. Сервис регистрации/авторизации - Пользователь регистрируется с помощью пароля и почты или с помощью входа через аккаунт яндекс, госуслуги. Отдельная регистрация для авторов продукта, при регистрации создается страница автора, на которую могут попасть обычные пользователи
2. Сервис уведомлений - отправка подтверждения аккаунта пользователя ему на почту, новостная рассылка, подписка на новые товары, уведомение о платеже, отправка самого товара на почту (ссылка на диск с товаром)
3. Основной сервис - создание страницы креаторов, загрузка продуктов, отображение авторов, поиск и т.д

Стэк технологий:
Java, Spring Data, Spring AMQP, Spring Rest, Spring Boot, Spring Eureka, PostgreSQL, Grafana, Loki, Docker, SwaggerUI, RabbitMQ, Hibernate (Liquibase), Jackson, JUnit
JavaScript, React + ...

Roadmap.
<br>v1:
- реализация регистрации и входа
  - Авторизация
  - Отправка подтверждение почты (создание сервиса уведомлений)
  - Реализация таблиц в БД
  - Создание UI в React
- связь frontend, backend, bd
- Создание тестов с помощью JUnit

v1.1:
- создание страницы авторов
  - Реализация таблиц в БД
  - Создание UI
  - Построение основного сервиса (CRUD)
- загрузка продуктов, создание страницы продуктов
- покупка продуктов, подключение платежный систем
  - Реализовтаь баланс у пользователей и авторов: пополнение и снятие
  - Подключение платежной системы
- закончить сервис уведомлений
  - Отправка писем при покупке, выставлении продукта и т.д
- Создание тестов с помощью JUnit

v1.2:
- реализация поиска авторов
  - UI страница поиска
  - Реализовать быстрый поиск на бэке
- создание админки с ролями
  - UI админки
  - Описание ролей и связь с бэком и бд
- docker
- SwaggerUI (полное описание всех микросервисов)
- Создание тестов с помощью JUnit

v1.3:
- готовый MVP: пользователь может зарегистрироваться, как пользовать или как продавец. При регистрации, как продавец, создается страница автора, на которой он может загрузить свой цифровой продукт и указать различные параметры(цена, описание). Обычный пользователь может найти страницу автора и купить его цифровой продукт.
- подключение ELK или grafana stack
- Создание тестов с помощью JUnit

фичи:
- Яндекс, Гослуги авторизация
- Создание кастомных страниц продуктов, креаторов
- Главная станица, красиво оформленная.
- Создание категорий продуктов, тэги 
- Вишлист
- Рейтинг продуктов
- Страница поиска с фильтрами продуктов, а не только авторов.

| Что будет реализовано до | 16 января|
| ------------- | ------------- |
| Главная страница | |
| Базовая регистрация для пользователя с авторами с UI связанный с бэком и бд | |
| Подтверждение почты | |
| CRUD пользователей | |
| Автоматическое создание страницы автора при регистрации | |
| Junit тесты | |


title Диаграмма последовательности проекта Дигрикс
Пользователь->Сервис аутентификации:Создание аккаунта
Сервис уведомлений<--Сервис аутентификации:отправка данных пользователя для отправки сообщения подтверждения почты
Почта пользователя<--Сервис уведомлений: сообщение подтверждения 
Пользователь-->Почта пользователя:нажатие ссылки подтверждения 
Пользователь<--Сервис уведомлений: почта подтреждена

