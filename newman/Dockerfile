FROM node:lts-slim

# Пользователь node 1000:1000 уже создан
ARG APP=postman
# ARG UID=1000
# ARG GID=1000
ARG ROOT=/opt/${APP}


RUN npm install -g newman newman-reporter-htmlextra newman-reporter-allure
RUN mkdir -p ${ROOT} && chown -R node:node /opt
WORKDIR ${ROOT}
COPY ./environments/reqres_env.json .
USER node

ENTRYPOINT ["newman"]
# ENTRYPOINT ["sh"]
# ENTRYPOINT ["sh", "-c", "touch /srv/postman/test_file.txt && newman"]

# Оставить контейнер запущенным
# docker run -it --rm --name mynode node:lts-slim "bin/sh"
