# Дамп базы 
create table comments
(
    id   int unsigned auto_increment
        primary key,
    name varchar(319) not null,
    text text         not null,
    date datetime     not null on update CURRENT_TIMESTAMP
);



# Тестовое задание на основе Docker и CodeIgniter для Fullstack разработчика

## Первоначальная настройка

-   Устанавливаем Docker c [официального сайта](https://www.docker.com/products/docker-desktop) и [Docker Compose](https://docs.docker.com/compose/install/);
-   Для пользователей Windows дополнительно необходимо установить виртуальное ядро Linux:
    -   Скачиваем с официального сайта необходимый [пакет](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi);
    -   Устанавливаем пакет;
    -   Запускаем Powershell и выполняем команду `wsl --set-default-version 2`;
    -   Устанавливаем из Microsoft Store [Ubuntu](https://www.microsoft.com/store/apps/9n6svws3rx71);
    -   Запускаем настройку Ubuntu из пуска, задаем имя пользователя и пароль;
    -   Настраиваем Docker:
        -   Запускаем Docker Desktop и переходим в настройки ![General](readme-files/general-page.jpg);
        -   Во вкладке General включаем 'Use the WSL 2 based engine';
        -   Сохраняем настройки;
        -   Переходим во вкладку Resources ![Resources](readme-files/resources-page.jpg);
        -   Выбираем раздел WSL Integration;
        -   Включаем свеже установленный образ Ubuntu;
        -   Сохраняем настройки;
-   Собираем контейнер командой в папке проекта `docker-compose up -d`;
-   Инициализируем сервер:
    -   при запущенном контейнере в папке проекта запускаем команду `docker-compose exec web bash`;
    -   запускаем сборку `composer install`.

## Описание записи

-   name -  почта создателя;
-   text - Текст комментария;
-   date - Дата создания комментария в строковом формате(выбирается создателем).

## Стек

- PHP 7.4;
- MYSQL 8;
- CodeIgniter 4;
- jQuery 3;
- Bootstrap 4.

## Задание

Создать сайт со списком комментариев.
Форма с добавлением комментариевдолжна располагаться под уже добавленными комментариями.

Требования к разработке:

-   добавление и удаление комментариев (желательно, без перезагрузки страницы);
-   постраничный просмотр комментариев (3 комментария на страницу c возможностью выбора конкретной);
-   сортировка по:
    -   id;
    -   дате добавления;
-   направления сортировки:
    -   по возрастанию;
    -   по убыванию;
-   использование валидации почты при вводе для пользователя (с отображением ошибки), а также на сервере;
-   использование адаптивной верстки;
-   использование jQuery.
