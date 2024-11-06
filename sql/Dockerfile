# MySQL Dockerfile (if needed)
FROM mysql:latest

ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=my_database

COPY ./db_user.sql ./docker-entrypoint-initdb.d/
