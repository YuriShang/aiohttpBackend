# aiohttpBackend

Запуск приложения:
  1) Устанавливаем зависимости; 
  2) В конфиге прописываем url бд, а также имя пользователя и пароль;
  3) Делаем миграции с помощью Alembic;
  4) Запускаем main.py
  
Взаимодействия с БД:
  1) Залогиниться - host:port/login. 'username' и 'password' передаются через form-data по соответствующим ключам.
  2) Прочитать список пользователей (GET) - host:port/read 
  3) Создать пользователя (POST) - host:port/create. Необходимо передать json со следующими полями:
  
    {
    "login": "user",
    "name": "Ivan",
    "surname": "необязательное поле"
    "password": "password",
    "birthday": "01.01.1970",
    "privileges": "readonly",
    }
    
    возможные значения для поля "privileges" - "readonly", "admin"
    
 4) Обновить данные пользователя (POST) - host:port/update. Необходимо передать json со следующими полями:
   
    {
    "login": "user",
    "name": "Ivan",
    "surname": "необязательное поле"
    "password": "password",
    "birthday": "01.01.1970",
    "privileges": "readonly",
    }
    
    возможные значения для поля "privileges" - "readonly", "admin"
    
 5) Удалить пользователя (POST) - host:port/delete. Необходимо передать json со следующими полями:
  
    {
    "login": "username"
    }
  
 6) Заблокировать пользователя - host:port/block. Необходимо передать json со следующими полями:
  
    {
    "login": "username"
    }
    
 7) Разблокировать пользователя - host:port/unblock. Необходимо передать json со следующими полями:
  
    {
    "login": "username"
    }
    
 8) выйти из системы (POST) - host:port/logout
  