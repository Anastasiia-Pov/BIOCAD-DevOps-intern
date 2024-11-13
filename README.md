# BIOCAD-DevOps-intern

Схема организации контейнеров и сервисов

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/schema.png width=750 />


1. Создать веб приложение “hello world” на любом языке программирования, которое должно работать на порту 32777:
- Веб-приложение реализовано на фреймворке FastAPI - [main.py](https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/app/main.py);
- Dockerfile для сборки образа - [Dockerfile](https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/Dockerfile).

2. Установить Docker на рабочий компьютер.

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/2.%20%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9%20Docker%20.png width=750 />

3. Сборка контейнера и публикация на DockerHub.
- Образ контейнера собирается командой: 
`
docker build -t anastasiiapovolotskaia/biocad_intern_devops-web:v1 .
`
- Публикация контейнера на DockerHub командой: 
`
docker push anastasiiapovolotskaia/biocad_intern_devops-web:v1 
`

- Ссылка на репозиторий на DockerHub: https://hub.docker.com/repository/docker/anastasiiapovolotskaia/biocad_intern_devops-web/general

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/3.%20%D0%9F%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%20%D0%BA%D0%BE%D0%BD%D1%82%D0%B5%D0%B9%D0%BD%D0%B5%D1%80%D0%B0%20%D0%BD%D0%B0%20DockerHub.png width=750 />

4. Установить Minikube используя оригинальную инструкцию. После установки необходимо развернуть minikube cluster.

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/4.%20%D0%A0%D0%B0%D0%B7%D0%B2%D0%BE%D1%80%D0%B0%D1%87%D0%B8%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20minikube%20claster.png width=750 />

5. Создание deployment с 2 репликами приложения.

- cоздание деплоймента и проверка запуска первой реплики. 
    
<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/5.1%20%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%B4%D0%B5%D0%BF%D0%BB%D0%BE%D0%B9%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%20%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0%20%D0%B5%D0%B3%D0%BE%20%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0.%20%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%201%20%D1%80%D0%B5%D0%BF%D0%BB%D0%B8%D0%BA%D0%B8.png width=750 />

- изменение количества подов в деплойменте, добавление второй реплики.

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/5.2%20%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%B2%D1%82%D0%BE%D1%80%D0%BE%D0%B9%20%D1%80%D0%B5%D0%BF%D0%BB%D0%B8%D0%BA%D0%B8.png width=750 />
    
6. Создание сервиса, через который будет доступ на "поды". Тип сервиса - NodePort.

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/6.%20%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%B5%D0%BC%20%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%2C%20%D1%87%D0%B5%D1%80%D0%B5%D0%B7%20%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D0%B9%20%D0%BE%D1%81%D1%83%D1%89%D0%B5%D1%81%D1%82%D0%B2%D0%BB%D1%8F%D0%B5%D1%82%D1%81%D1%8F%20%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%20%D0%BA%20%D0%BF%D0%BE%D0%B4%D0%B0%D0%BC.png width=750 />

7. Запуск в minikube режима проброса портов и подключение к контейнерам через веб-браузер.

- создание тунеля для работа через Docker container по адресу http://127.0.0.1:53803:

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/7.1%20%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%82%D1%83%D0%BD%D0%B5%D0%BB%D1%8F%20%D0%B4%D0%BB%D1%8F%20Docker.png width=750 />

- подключение к контейнерам через веб-браузер:

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/7.2%20%D0%9F%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%BA%20%D0%BA%D0%BE%D0%BD%D1%82%D0%B5%D0%B9%D0%BD%D0%B5%D1%80%D0%B0%D0%BC%20%D1%87%D0%B5%D1%80%D0%B5%D0%B7%20%D1%82%D1%83%D0%BD%D0%B5%D0%BB%D1%8C.png width=750 />
