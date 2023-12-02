FROM mcr.microsoft.com/openjdk/jdk:17-ubuntu
# ENV LANG en_US.UTF-8
# ENV JAVA_HOME /usr/lib/jvm/msopenjdk-17-amd64
# ENV PATH "${JAVA_HOME}/bin:${PATH}"

ARG APP=allure
ARG UID=1000
ARG GID=1000
ARG ROOT=/opt/${APP}

RUN apt-get update && \
apt-get install wget tar -y && \
wget "https://github.com/allure-framework/allure2/releases/download/2.24.1/allure-2.24.1.tgz" && \
tar -zxvf allure-2.24.1.tgz -C /opt/ && \
ln -s /opt/allure-2.24.1/bin/allure /usr/bin/allure && \
rm allure-2.24.1.tgz

RUN mkdir ${ROOT}

RUN groupadd --gid ${GID} ${APP} \
    && useradd --uid ${UID} --gid ${APP} --shell /bin/bash --create-home ${APP}

WORKDIR ${ROOT}

RUN chown -R ${APP}:${APP} /opt
USER ${APP}
