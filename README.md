**Техническое задание (ТЗ) для бота Telegram на Python:**

1. **Общее описание:**
    Разработать Telegram бота, который предоставляет пользователю доступ к информации с сайта Habr.com. Бот должен реагировать на определенные команды и предоставлять запрошенную информацию.

2. **Функциональные требования:**

    2.1. **Команда /posts:**
    
        2.1.1. Пользователь отправляет команду /posts в чат бота.
        
        2.1.2. Бот отправляет пользователю 5 лучших постов за сегодня с сайта Habr.com в виде гиперссылки с заголовком поста и его рейтинг.
    
    2.2. **Команда /hubs:**
    
        2.2.1. Пользователь отправляет команду /hubs в чат бота.
        
        2.2.2. Бот отправляет пользователю список из 10 самых популярных Хабов на сайте Habr.com
    
    2.3. **Команды /subscribe и /unsubscribe:**
    
        2.3.1. Пользователь отправляет команду /subscribe <название_хаба> для подписки на определенный хаб.
        
        2.3.2. Бот добавляет пользователя в базу данных SQLite в таблицу "subs" с указанием хаба.
        
        2.3.3. Пользователь отправляет команду /unsubscribe для отмены подписки на определенный хаб.
        
        2.3.4. Бот удаляет пользователя из таблицы "subs" по указанному хабу.
    
    2.4. **Команда /subs:**
    
        2.4.1. Пользователь отправляет команду /subs в чат бота.
        
        2.4.2. Бот проверяет подписки пользователя в таблице "subs" базы данных SQLite.
        
        2.4.3. Для каждого хаба, на который подписан пользователь, бот отправляет самую популярную статью за сегодня.
    
3. **Требования к реализации:**

    3.1. Для парсинга данных использовать библиотеки requests и BeautifulSoup.
    
    3.2. Для взаимодействия с Telegram API можно использовать голые HTTPS запросы или библиотеку, такую как python-telegram-bot / aiogram.
    
    3.3. Для хранения подписок пользователя использовать базу данных SQLite.
    
    3.4. Реализовать обработку ошибок, например, при неправильном вводе пользователя или ошибки при парсинге данных.
    
4. **Примерный алгоритм работы бота:**
    
    4.1. Получение сообщения от пользователя.
    
    4.2. Проверка полученной команды.
    
    4.3. В зависимости от команды выполнение соответствующего действия:
    
        - /posts: Парсинг данных с сайта и отправка результатов пользователю.
        
        - /hubs: Получение списка популярных хабов и отправка результатов пользователю.
        
        - /subscribe: Добавление подписки пользователя в базу данных.
        
        - /unsubscribe: Удаление подписки пользователя из базы данных.
        
        - /subs: Получение списка подписок пользователя и отправка результатов пользователю.
