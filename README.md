### Collection - link:

wget https://github.com/allure-framework/allure2/releases/download/2.24.1/allure-2.24.1.tgz
sudo tar -zxvf allure-2.24.1.tgz -C /opt/

sudo ln -s /opt/allure-2.24.1/bin/allure /usr/bin/allure

docker run -v ./newman:/etc/postman --rm vitgt/newman-htmlextra-allure newman run "https://www.postman.com/collections/29800373-595b2c38-79f7-4fd2-bc40-f89df17be89e" -k -e "reqres_env.json" -r cli,allure



allure serve
allure generate

### Даем всем права на зашаренную папку
sudo chmod -R 777 ./docker_shared
mkdir -p docker_shared/allure-results
mkdir -p docker_shared/default-reports
mkdir -p docker_shared/report
