# Лабораторная работа: Запуск сайта в контейнере

## Цель работы
 Подготовка образа контейнера для запуска веб-сайта на базе Apache HTTP Server + PHP (mod_php) + MariaDB.

## Задание
1. Создать образ контейнера с веб-сервером Apache, PHP и MariaDB.
2. Запустить контейнер с созданным образом.
3. Настроить и установить WordPress на веб-сервере.
4. Проверить работоспособность сайта WordPress.

## Описание выполнения работы с ответами на вопросы
1. Создание Dockerfile: Мы создали Dockerfile для сборки образа контейнера с именем apache2-php-mariadb.
![1](./1s.PNG) 
2. Установка необходимых компонентов: В Dockerfile мы устанавливали необходимые компоненты, такие как Apache, PHP и MariaDB.

3. Настройка Apache и PHP: Мы изменяли конфигурационные файлы Apache и PHP для настройки веб-сервера и PHP-интерпретатора.

4. Загрузка файлов WordPress: Мы загружали файлы WordPress в контейнер, чтобы развернуть сайт WordPress.
![2](./2s.PNG)

5. Настройка базы данных: Мы создавали базу данных WordPress и пользователя для доступа к ней.
![3](./3s.PNG)

6. Создание файла конфигурации WordPress: Мы создавали файл конфигурации WordPress (wp-config.php) и копировали его в контейнер.

7. Запуск контейнера: Мы запускали контейнер из созданного образа с помощью команды docker run.

8. Проверка доступности сайта: Мы проверяли доступность сайта WordPress в браузере по адресу http://localhost/.

## Выводы
В результате выполнения лабораторной работы был успешно создан и настроен веб-сервер с WordPress. Были изучены основные принципы работы с Docker и контейнеризации веб-приложений.

## Ответы на вопросы
1. Какие файлы конфигурации были изменены? Были изменены файлы конфигурации 000-default.conf (для Apache), php.ini (для PHP), '50-server.cnf' (для mariadb) и wp-config.php (для WordPress) и Dockerfile.
2. За что отвечает инструкция DirectoryIndex в файле конфигурации apache2? Инструкция DirectoryIndex определяет порядок приоритета индексных файлов, которые веб-сервер будет искать в директории при запросе к корневому URL.
3. Зачем нужен файл wp-config.php? Файл `wp-config.php` содержит настройки WordPress, такие как параметры подключения к базе данных, ключи аутентификации и другие конфигурационные параметры.
4. За что отвечает параметр post_max_size в файле конфигурации php? Параметр `post_max_size` в файле конфигурации php определяет максимальный размер данных, отправляемых через метод POST.
5. Укажите, на ваш взгляд, какие недостатки есть в созданном образе контейнера? На мой взгляд, недостатками созданного образа контейнера могут быть:
- Отсутствие настроек безопасности, таких как отключение ненужных модулей Apache или настройка доступа к базе данных.
- Неоптимальное использование слоев в Dockerfile, что может привести к увеличению размера образа.
