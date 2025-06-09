# TradeOffer Ansible Deployment

## Описание

Проект для автоматического развёртывания приложения TradeOffer с помощью Ansible и Docker Compose. Состоит из четырёх сервисов: frontend, backend, mysql и adminer. 

Готовый compose для запуска приложения берется из: https://github.com/AnnaKlyshnikova/task1-Docker-Ansible-Vagrant.git

## Структура
```
ansible-tradeoffer/
├── ansible.cfg
├── deploy_tradeoffer.yml
├── inventory/
│   └── hosts.yml
├── roles/
│   └── tradeoffer/
│       ├── tasks/main.yml
│       ├── defaults/main.yml
│       ├── handlers/main.yml
│       ├── meta/main.yml
│       ├── vars/main.yml
│       ├── files/
│       ├── templates/
│       └── tests/
│           ├── inventory
│           └── test.yml
└── ssh_keys/
    └── lab
```
## Что делает

- Устанавливает Docker и Docker Compose
- Клонирует репозиторий приложения
- Копирует проект в /opt/tradeoffer
- Запускает docker compose с файлом compose.yml

## Запуск
ansible-playbook deploy_tradeoffer.yml

## Требования
- Коллекция community.docker:
  ansible-galaxy collection install community.docker