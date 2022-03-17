# Создание приватного Docker Registry


## Как установить Docker Registry на сервер

- сгенерим htpasswd файл  
`docker run --rm registry:2.6.2 htpasswd -Bbn ExampleRegistryLogin ExampleRegistryPassword > htpasswd`
- запустим команду для установки со всеми необходимыми параметрами  
`HOST=140.238.212.163 PORT=22  HTPASSWD_FILE=htpasswd make deploy`
- Переходим по ссылкам
  - http://registry.demo-auction.phpqa.ru:3000/v2/
  - http://cache-registry.demo-auction.phpqa.ru:3000/v2/
- Логин пароль см. из п.1 

## Локально
- docker compose up
- http://localhost:5000/v2/


### **authorized_key**
- Добавляет или удаляет авторизованные SSH-ключи для определенных учетных записей пользователей.