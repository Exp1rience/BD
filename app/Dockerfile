FROM postgres:15-alpine

# Установка локали
RUN apk add --no-cache tzdata
ENV TZ=Europe/Moscow

# Копируем скрипт инициализации
COPY init.sql /docker-entrypoint-initdb.d/

# Настройки PostgreSQL для производительности
RUN echo "shared_buffers = 256MB" >> /usr/share/postgresql/postgresql.conf.sample && \
    echo "max_connections = 100" >> /usr/share/postgresql/postgresql.conf.sample

EXPOSE 5432

CMD ["postgres"]
