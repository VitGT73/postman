# docker build -t vitgt/newman-htmlextra-allure .
FROM node:lts-slim as builder

ARG APP=postman
ARG ROOT=/etc/${APP}

RUN npm install -g newman newman-reporter-htmlextra newman-reporter-allure \
    && mkdir -p ${ROOT} \
    && chown -R node:node ${ROOT}

WORKDIR ${ROOT}
USER node

CMD ["newman" "-v"]
# ENTRYPOINT ["newman"]
# COPY entrypoint.sh /entrypoint.sh

# ENTRYPOINT ["/entrypoint.sh"]
