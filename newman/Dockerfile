# Stage 1: Build stage
FROM node:lts-slim as builder

ARG APP=postman
ARG ROOT=/etc/${APP}

RUN npm install -g newman newman-reporter-htmlextra newman-reporter-allure \
    && mkdir -p ${ROOT} \
    && chown -R node:node ${ROOT}

WORKDIR ${ROOT}
USER node

ENTRYPOINT ["newman"]
