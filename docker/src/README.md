# Тестовое задание для DevOps Engineer

## Цель
Развернуть простое Python приложение с использованием Docker и Ansible, а также настроить Nginx как обратный прокси-сервер.

## Задачи
1. Создать `Dockerfile` для Python приложения.
2. Настроить `docker-compose.yml` для запуска приложения и Nginx.
3. Разработать Ansible роль для автоматического развертывания.

## Требования

### 1. Подготовка Dockerfile

Необходимо подготовить [Dockerfile](https://docs.docker.com/engine/reference/builder/) для сборки python приложения,
хранящегося в директории `python/`

В репозитории присутствует файл `requirements.txt`, содержащий в себе зависимости python для запуска приложения, в Dockerfile необходимо добавить шаг для установки данных зависимостей.

### 2. Подготовка docker-compose

Необходимо подготовить [docker-compose.yml](https://docs.docker.com/compose/compose-file/compose-file-v3/) файл для запуска собранного приложения и Nginx.

docker-compose.yml должен содержать следующие директивы:
- [build](https://docs.docker.com/compose/compose-file/compose-file-v3/#build)
- [ports](https://docs.docker.com/compose/compose-file/compose-file-v3/#ports) (python-приложение слушает по порту 8080)
- [environment](https://docs.docker.com/compose/compose-file/compose-file-v3/#environment). По-умолчанию приложение имеет переменную `HelloMessage='Hello world!'`, необходимо при запуске приложения указать значение данной переменной равным `Hello iac!`

### 3. Ansible
Необходимо настроить сервер с помощью ansible для запуска приложения и Nginx с помощью ранее написанного docker-compose.

[ansible-playbook](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_intro.html) должен иметь следующие функции:
- Установка docker, docker-compose
- Передача Dockerfile, docker-compose.yml, исходных кодов и конфигураций
- Запуск приложения с помощью утилиты docker-compose

Для выполнения данного пункта можно использовать сторонние роли.
Все используемые роли следует указать в файле [requirements.yml](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html#installing-multiple-roles-from-a-file).

### 4. Проверка задания
- Запустить Ansible роль для развертывания.
- Перейти по адресу `http://localhost` для проверки работы приложения через Nginx( приложение должно отдавать указанную в переменной окружения `HelloMessage` строку)

## Оформление результата

- Весь код должен быть организован в виде репозитория на GitHub.
- Необходимо включить `README.md` с инструкциями по развертыванию и тестированию.
- Репозиторий должен содержать все конфигурационные файлы и шаблоны.
