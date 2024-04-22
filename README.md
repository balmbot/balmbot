Кратко о проекте BalmBot:
Разработка чат-бота в Telegram, который будет регулярно отправлять пользователям приятные послания или милые картинки для поднятия настроения.

Описание приложения и его работы:
- Аудитория приложения: Люди, которым требуется поддержка и позитивные эмоции в повседневной жизни.
- Логика работы:
  1. Пользователь подписывается на бота и разрешает ему отправлять сообщения.
  2. Бот регулярно (например, раз в несколько часов) отправляет пользователю случайное приятное сообщение или милую картинку c помощью API

Сущности(таблицы) в базе данных:
1. Users (Пользователи):
   - id (идентификатор пользователя)
   - username (имя пользователя в Telegram)
   - chat_id (идентификатор чата в Telegram)
   - created_at (дата регистрации)

2. Messages (Сообщения):
   - id (идентификатор сообщения)
   - user_id (идентификатор пользователя, кому отправлено сообщение)
   - message_text (текст сообщения)
   - image_url (URL изображения, если есть)
   - sent_at (дата и время отправки сообщения)

3. Subscriptions (Подписки):
   - id (идентификатор подписки)
   - user_id (идентификатор пользователя)
   - active (флаг активности подписки)
