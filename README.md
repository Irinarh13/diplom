# Дипломный проект по курсу "Тестировщик ПО"

## Установленное ПО

1. IntelliJ IDEA 2023.3.6 (Community Edition);
2. Docker Desktop;
3. Браузер, например: Google Chrome.

## Описание запуска автотестов

1. Склонируйте репозиторий по ссылке: https://github.com/netology-code/qa-diploma/tree/master;
2. Откройте проект в IntelliJ IDEA;
3. Запустить Docker;
4. Для запуска контейнеров нужно ввести команду в терминале - docker compose up;
5. Для запуска приложения в новой вкладке терминала нужно ввести команду:
* Для MySQL: java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar artifacts/aqa-shop.jar;   
* Для PostgreSQL: java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar artifacts/aqa-shop.jar;
6. Для запуска автотестов в новой вкладке терминала нужно ввести команду - ./gradlew clean test --info (по умолчанию запускается MySQL)
* ./gradlew test -Ddb.url=jdbc:postgresql://localhost:5432/app - для запуска PostgreSQL;
7. После автотестов, в новой вкладке терминала ввести команду - ./gradlew allureserve (для генерации отчетов на Allure);
8. После проделанной работы, а также просмотра отчета по автотестам необходимо ввести команду для остановки aqa-shop.jar - Ctrl+C;
9. Для удаления контейнеров ввести в терминале команду - docker compose down.
