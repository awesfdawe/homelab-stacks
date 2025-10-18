# drasl

Контейнер альтернативного сервера авторизации для Minecraft.

# Референсы

- https://github.com/Unmojang/Drasl
- https://github.com/unmojang/drasl/blob/master/doc/configuration.md
- https://github.com/unmojang/FjordLauncher

# Пометки

```bash
# Создайте папку для конфигурации и данных drasl
mkdir /mnt/docker-volumes/drasl/config -p
mkdir /mnt/docker-volumes/drasl/data -p
```

Шаблон подразумевает что данные будут идти по https.

1. Настройте файл `.env` с вашими личными секретами:

```env
DOMAIN=drasl.example.com
FIRST_ADMIN_USERNAME=playername
```

2. Отрендерите шаблон:

```bash
set -o allexport
. .env
set +o allexport
envsubst < ./config.template.toml > /mnt/docker-volumes/drasl/config/config.toml
```

3. Запустите стек.