# taski-docker

Это проект "таск-менеджер". Этот проект был размещен на одном веб-сервере с другим проектом https://github.com/Dmitry8815585/kittygram_final , используя различные порты.
Мои задачи включали в себя настройку WSGI-сервера (Gunicorn) для эффективной работы с бэкенд-приложением проекта, а также настройку веб-сервера Nginx .
Я обеспечил шифрование запросов по протоколу HTTPS, написал Dockerfile для создания образов и реализовал запуск таск-менеджера в контейнерах.
Дополнительно, процессы тестирования и деплоя проекта были автоматизированы с использованием GitHub Actions.

### Стек проекта: Docker, Nginx, Gunicorn, workflow, GitHub Actions, CI/CD, Linux

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
