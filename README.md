# BIOCAD-DevOps-intern

1. Создать веб приложение “hello world” на любом языке программирования, которое должно работать на порту 32777:
- Веб-приложение реализовано на фреймворке FastAPI - [main.py](https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/app/main.py);
- Dockerfile для сборки образа - [Dockerfile](https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/Dockerfile).

2. Установить Docker на рабочий компьютер.

<img src=https://github.com/Anastasiia-Pov/BIOCAD-DevOps-intern/blob/main/screenshots/2.%20%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9%20Docker%20.png width=450 />

3. Образ контейнера собирается командой: ```docker build -t anastasiiapovolotskaia/biocad_intern_devops-web:v1 .```
Публикация контейнера на DockerHub командой: ```docker push anastasiiapovolotskaia/biocad_intern_devops-web:v1 ```
Ссылка на репозиторий на DockerHub: https://hub.docker.com/repository/docker/anastasiiapovolotskaia/biocad_intern_devops-web/general


4. Установить Minikube используя оригинальную инструкцию. После установки необходимо развернуть minikube cluster.


5. Создание deployment с 2 репликами приложения.


6. Создание сервиса, через который будет доступ на "поды". Тип сервиса - NodePort.


7. Запуск в minikube режима проброса портов и подключение к контейнерам через веб браузер.
