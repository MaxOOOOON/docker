# docker

**homework**
1. Создайте свой кастомный образ nginx на базе alpine. После запуска nginx должен 
отдавать кастомную страницу (достаточно изменить дефолтную страницу nginx). Собранный образ необходимо запушить в docker hub и дать ссылку на ваш 
репозиторий.
2. Определите разницу между контейнером и образом

3. Ответьте на вопрос: Можно ли в контейнере собрать ядро?
---


1. Создайте свой кастомный образ nginx  
    Сначала необходимо создать dockerfile  
    Затем собрать докер образ

         docker build -t maxon29/nginx_custom:0.2 .
         
    Запустить контейнер

        docker run -d -p 80:80 maxon29/nginx_custom:0.2

    Добавляем контейнер в docker hub

        docker push maxon29/nginx_custom:0.2

    Проверка доступности:

    ![check](https://github.com/MaxOOOOON/docker/blob/main/Screenshot%202021-09-12%20202257.png)

    Ссылка на docker hub с образом: 

    https://hub.docker.com/repository/docker/maxon29/nginx_custom

2. Образ - "сущность" стека слоев только для чтения.Контейнер - "сущность" стека слоев с верхним слоем для записи.


3. Можно, только контейнер нужно будет запускать с привилигерованными правами


Полезное:  

docker stop $(docker ps -aq)  
docker build -t id/cont-name:ver .  
docker commit nginx-base  
docker exec -it container_id /bin/bash   
docker-compose exec {CONTAINER_NAME} {COMMAND}  
ENV - переменные окружения  
ARG - переменные во время сборки    
COPY - скопировать файл или папку   
ADD - скопировать файл или папку, скачать по ссылке, разархивировать архив  
EXPOSE - документация   
Контейнер- Это приложение и его зависимости упакованные в окружение 
