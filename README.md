# ContinentalGuy_infra
ContinentalGuy Infra repository

# Подключение к 'someinternalhost' в одну команду.
Создаем 'config' файл в директории /.ssh:
```
Host someinternalhost
IdentityFile ~/.ssh/appuser
ProxyCommand ssh appuser@35.206.128.169 -W %h:%p

Host bastion
IdentityFile ~/.ssh/appuser
```

Для установки соединения:
```bash
ssh appuser@someinternalhost
```

# Установка alias'а на 'appuser@someinternalhost'.
```
Host someinternalhost
HostName 10.132.0.8
User appuser
IdentityFile ~/.ssh/appuser
ProxyCommand ssh appuser@35.206.128.169 -W %h:%p

Host bastion
IdentityFile ~/.ssh/appuser
```

Для установки соединения:
```bash
ssh someinternalhost
```