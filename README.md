# Создание приватного Docker Registry

## Common installation preparations
- сгенерим htpasswd файл  
  `docker run --rm registry:2.6.2 htpasswd -Bbn ExampleRegistryLogin ExampleRegistryPassword > htpasswd`

## How to install to local dev
- `make init` or `docker compose up`
- now you can open local docker registry: http://localhost:5000/v2/
- default login = registry, password = password

## How to install to production
- запустим команду для установки со всеми необходимыми параметрами  
`HOST=140.238.212.163 PORT=22  HTPASSWD_FILE=htpasswd make deploy`
- Переходим по ссылкам
  - http://registry.demo-auction.phpqa.ru:3000/v2/
  - http://cache-registry.demo-auction.phpqa.ru:3000/v2/
- Логин пароль см. из п.1 


### **authorized_key**
- Добавляет или удаляет авторизованные SSH-ключи для определенных учетных записей пользователей.