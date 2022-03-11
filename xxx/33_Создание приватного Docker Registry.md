- docker compose up
- http://localhost:5000/v2/

Команда для генерации htpasswd файла:  
`docker run --rm registry:2.6.2 htpasswd -Bbn registry password > htpasswd` 



### **authorized_key**  
- Добавляет или удаляет авторизованные SSH-ключи для определенных учетных записей пользователей.