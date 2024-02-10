# taski-docker

Это проект "таск-менеджер". Этот проект был размещен на одном веб-сервере с другим проектом https://github.com/Dmitry8815585/kittygram_final , используя различные порты.
Мои задачи включали в себя настройку WSGI-сервера (Gunicorn) для эффективной работы с бэкенд-приложением проекта, а также настройку веб-сервера Nginx .
Я обеспечил шифрование запросов по протоколу HTTPS, написал Dockerfile для создания образов и реализовал запуск таск-менеджера в контейнерах.
Дополнительно, процессы тестирования и деплоя проекта были автоматизированы с использованием GitHub Actions.

## Стек проекта "таск-менеджер"
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white) ![Gunicorn](https://img.shields.io/badge/Gunicorn-369639?style=for-the-badge&logo=gunicorn&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white) ![CI/CD](https://img.shields.io/badge/CI/CD-4B32C3?style=for-the-badge&logo=github-actions&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)


### Установка

Нужно скопировать содержимое .env.example в локальный файл .env и проставить нужные значения вместо CHANGE_ME

1. Клонировать репозиторий:

   cd taski-docker
   
   git clone https://github.com/good8815585/taski-docker.git
    

3. Установить зависимости бэкенда:

    docker-compose -f docker-compose.production.yml run backend python manage.py migrate

4. Установить зависимости фронтенда:

    docker-compose -f docker-compose.production.yml run frontend npm install

5. Собрать статические файлы и собрать Docker-образы:

    docker-compose -f docker-compose.production.yml build
