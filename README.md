## express app

Access with browser http://localhost:8080


Как запустить из cli:
- docker run -d -p 80:8080 --name express-app evgdudareff/express-app:latest
- docker run -d --name watchtower -e REPO_USER=YOUR_LOGIN -e REPO_PASS=YOUR_TOKEN -v /var/run/docker.sock:/var/run/docker.sock


Как запустить при помощи docker-compose:
- echo -n "YOUR_LOGIN:YOUR_TOKEN" | base64
- кодированный токен добавить в поле auth в config.json
- запуск docker-compose up
- остановка docker-compose down