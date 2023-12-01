FROM node:lts-slim


RUN npm install -g newman newman-reporter-htmlextra newman-reporter-allure
WORKDIR /srv/postman
COPY ./environments/reqres_env.json .

ENTRYPOINT ["newman"]
