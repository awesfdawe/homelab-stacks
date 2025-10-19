# drasl

Стак содержит следующие сервисы:
  - Drasl
    - Альтернативный сервер авторизации для Minecraft.
  - Anubis
    - Защита от ботов.

# Референсы

- https://github.com/Unmojang/Drasl
- https://github.com/unmojang/drasl/blob/master/doc/configuration.md
- https://github.com/TecharoHQ/anubis
- https://anubis.techaro.lol/docs/category/configuration/
- https://github.com/unmojang/FjordLauncher

# docker volumes mapping

Создайте папку для конфига и данных drasl контейнера.

```bash
mkdir /mnt/docker-volumes/drasl/{config,data} -p
sudo chown 1000:1000 /mnt/docker-volumes/drasl/ -R
sudo chmod 775 /mnt/docker-volumes/drasl/ -R
```

# Пометки

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