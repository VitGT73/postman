### Collection - link:

wget https://github.com/allure-framework/allure2/releases/download/2.24.1/allure-2.24.1.tgz
sudo tar -zxvf allure-2.24.1.tgz -C /opt/

sudo ln -s /opt/allure-2.24.1/bin/allure /usr/bin/allure

newman run "https://www.postman.com/collections/29800373-595b2c38-79f7-4fd2-bc40-f89df17be89e" -r allure -e "envirmens
allure serve
