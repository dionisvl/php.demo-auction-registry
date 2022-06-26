# Создание приватного Docker Registry

## Common installation preparations
- сгенерим htpasswd файл  
  `docker run --rm registry:2.6.2 htpasswd -Bbn ExampleRegistryLogin ExampleRegistryPassword > htpasswd`

## How to install to local dev
- `make init` or `docker compose up`
- now you can open local docker registry: http://localhost:5000/v2/
- default login = registry, password = password

## How to install to production
- go to provision directory and prepare target server
  - cd pro*
  - make server
  - make authorize
- запустим команду для установки со всеми необходимыми параметрами  
`HOST=164.215.102.35 PORT=222  HTPASSWD_FILE=htpasswd make deploy`
- Переходим по ссылкам
  - http://registry.demo-auction.phpqa.ru/v2/
  - http://cache-registry.demo-auction.phpqa.ru/v2/
- Логин пароль см. из п.1 


### **authorized_key**
- Добавляет или удаляет авторизованные SSH-ключи для определенных учетных записей пользователей.


### Провека cache-registry
- `sudo nano /etc/docker/daemon.json`
- or on Windows: `C:\Users\User\.docker\daemon.json`
```
{
  "registry-mirrors": ["http://cache-registry.demo-auction.phpqa.ru"]
}
```
- go to url: http://cache-registry.demo-auction.phpqa.ru/v2/_catalog