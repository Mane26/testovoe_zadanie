# Testovoe_zadanie Bewise.ai- простой веб сервис с помощью FastAPI.


## Стек технологий

- Python 3.10
- Pip
- FastApi
- Docker
- Docker Compose
- SQLAlchemy
- Pydantic
- PostgreSQL



## Установка проекта локально

* Склонировать репозиторий на локальную машину:
```bash
git clone https://github.com/Mane26/testovoe_zadanie
cd testovoe_zadanie
```

* Cоздать и активировать виртуальное окружение:

```bash
python3 -m venv venv
```

```bash
. venv/bin/activate
```

* Cоздайте файл `.env` в директории `/infra/` с содержанием:

```
ALLOWED_HOSTS='ip localhost'
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

* Перейти в директирию и установить зависимости из файла requirements.txt:

```bash
pip install -r requirements.txt
```


## Запуск проекта в Docker контейнере
* Установите Docker.

Параметры запуска описаны в файлах `docker-compose.yml` которые находятся в директории `infra/`.  

* Запустите docker compose:
```bash
docker-compose up -d --build  
```  
  
## Сайт
После запуска проект будут доступен по адресу:
[http://localhost/]

### Подготовка и запуск проекта на сервере

- Клонировать проект с помощью git clone или скачать ZIP-архив.
- Перейти в папку \testovoe_zadanie и выполнить команды:
```bash
sudo docker build -t <логин на DockerHub>/<название образа для бэкенда, какое хотите> .
sudo docker login
sudo docker push <логин на DockerHub>/<название образа для бэкенда, которое написали> 
```

- Установить docker на сервер:
```bash
sudo apt install docker.io 
```
- Установить docker-compose на сервер:
```bash
sudo apt-get update
sudo apt install docker-compose
```
- Скопировать файл docker-compose.yml из директории infra на сервер:
```bash
scp docker-compose.yml <username>@<host>:/home/<username>/
```

- Проект будет доступен по вашему IP-адресу.

## Документация к API
API документация доступна по ссылке (создана с помощью redoc):
http://localhost/api/docs/


## Пример POST-запроса:
URL: https://localhost/questions/bulk
Request body: {question_num: 100}
Response: "Question Example"


## Авторы
[Саркисян М.М.](https://github.com/Mane26) - Python разработчик. Разработала бэкенд и деплой для сервиса Foodgram.  
