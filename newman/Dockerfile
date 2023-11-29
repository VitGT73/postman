FROM node:lts-slim
# RUN npm install -g newman newman-reporter-htmlextra newman-reporter-allure

ARG PROJECT_NAME=postman
ARG GROUP_ID=5000
ARG USER_ID=5000

RUN groupadd --gid ${GROUP_ID} ${PROJECT_NAME} && \
    useradd --home-dir /home/${PROJECT_NAME} --create-home --uid ${USER_ID} \
        --gid ${GROUP_ID} --shell /bin/sh --skel /dev/null ${PROJECT_NAME} && \
    mkdir /etc/${PROJECT_NAME} && \
    chown -R ${PROJECT_NAME}:${PROJECT_NAME} /etc/${PROJECT_NAME}

RUN npm install -g newman
WORKDIR /etc/${PROJECT_NAME}

COPY ./enviroments/reqres_env.json /etc/${PROJECT_NAME}
USER ${REMOTE_USER}
# Set newman as the default container command
ENTRYPOINT ["newman"]
