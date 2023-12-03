FROM mcr.microsoft.com/openjdk/jdk:17-ubuntu
# Используем минимальный базовый образ для JDK 17

ARG APP=allure
ARG UID=1000
ARG GID=1000
ARG ROOT=/etc/${APP}

# Устанавливаем необходимые пакеты и скачиваем Allure
RUN apt-get update && apt-get install -y wget tar \
    && wget "https://github.com/allure-framework/allure2/releases/download/2.24.1/allure-2.24.1.tgz" \
    && tar -zxvf allure-2.24.1.tgz -C /opt/ \
    && ln -s /opt/allure-2.24.1/bin/allure /usr/bin/allure \
    && rm allure-2.24.1.tgz \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Создаем необходимую директорию и настраиваем права доступа
RUN mkdir ${ROOT} \
    && groupadd --gid ${GID} ${APP} \
    && useradd --uid ${UID} --gid ${APP} --shell /bin/bash --create-home ${APP} \
    && chown -R ${APP}:${APP} ${ROOT}

WORKDIR ${ROOT}

# Указываем пользователя, от имени которого будет выполняться приложение
USER ${APP}

ENTRYPOINT [ "allure" ]
