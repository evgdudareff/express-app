## Тестовый проект node express для проверки github actions при помощи docker hub и watchtower

Сервер доступен для проверки по адресу http://localhost:8080

Что делает:
- вокфлоу мониторит пуш в master-ветку, пересобирает образ и пушит в docker hub
- watchtower мониторит с указанным интервалом именованный контейнер приложения и подтягивает изменения, если они есть


Как запустить из cli:
- docker run -d -p 80:8080 --name express-app evgdudareff/express-app:latest
- docker run -d --name watchtower -e REPO_USER=YOUR_LOGIN -e REPO_PASS=YOUR_TOKEN -v /var/run/docker.sock:/var/run/docker.sock


Как запустить при помощи docker-compose:
- echo -n "YOUR_LOGIN:YOUR_TOKEN" | base64
- кодированный токен добавить в поле auth в config.json
- запуск docker-compose up
- остановка docker-compose down