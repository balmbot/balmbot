Проект BalmBot:
Чат-бот в Telegram, который каждое утро в 10:00 (GMT+3) отправляет пользователям приятные послания и милые картинки для поднятия настроения.
Ссылка на бот: https://t.me/BalmmBot

Описание приложения и его работы:
- Аудитория приложения: Люди, которым требуется поддержка и позитивные эмоции в повседневной жизни.
- Логика работы:
  1. Пользователь подписывается на бота и разрешает ему отправлять сообщения.
  2. Бот c помощью API отправляет пользователю приятное сообщение и картинку раз в сутки в 10:00 (GMT+3). 
  3. Сообщения хранятся в БД (supabase), картинки генерируются в момент отправки (Hugging Face)

 Схема работы
 
![balmbot drawio](https://github.com/balmbot/balmbot/assets/166996616/9db095a0-4886-4bbb-b748-2e8df1ed5b9a)



Сущности(таблицы) в базе данных:
1. users (Пользователи):
  - id (идентификатор пользователя)
  - chat_id (идентификатор чата в Telegram)
   - created_at (дата регистрации)

2. messages (Сообщения):
  - id (идентификатор сообщения)
  - message_text (текст сообщения)
  
3. send_messages (Отправленные сообщения):
  - id (идентификатор сообщения)
  - created_at (дата отправки)
  - chat_id (идентификатор чата в Telegram)
  -  text (текст сообщения)

4. send_images (Отправленные изображения):
  - id (идентификатор изображения)
  - created_at (дата отправки)
  - chat_id (идентификатор чата в Telegram)
  - file_id (уникальный идентификатор изображения)

5. error_messages (Не отправленные сообщения):
  - id (идентификатор изображения)
  - created_at (дата планируемой отправки)
  - chat_id (идентификатор чата в Telegram)
  - error (формат ошибки)

6. error_images(Не отправленные изображения):
  - id (идентификатор изображения)
  - created_at (дата планируемой отправки)
  - chat_id (идентификатор чата в Telegram)
  - error (формат ошибки)
