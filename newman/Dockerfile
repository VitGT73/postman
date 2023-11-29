FROM node:lts-slim
# RUN npm install -g newman newman-reporter-htmlextra newman-reporter-allure
RUN npm install -g newman
WORKDIR /etc/newman

# Set newman as the default container command
ENTRYPOINT ["newman"]
