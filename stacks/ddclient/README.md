# ddclient
https://docs.linuxserver.io/images/docker-ddclient/

В папке data создать ddclient.conf и заполнить по документации [ddclient.net](https://ddclient.net/), пример с cloudflare лежит в ddclient.example.conf

# ddclient

Контейнер DDNS.

# Референсы

- https://docs.linuxserver.io/images/docker-ddclient/
- https://github.com/ddclient/ddclient
- https://ddclient.net/

# Пометки

Шаблон подразумевает наличия домена на Cloudflare, API ключа с доступом к DNS:EDIT для нужной вам зоны.

1. Настройте файл `.env` с вашими личными секретами:

```env
API_KEY=kaewkekwKEWOEo2eokekWEKo2eke
ZONE=example.com
DOMAIN=ddns.example.com
```

2. Отрендерите шаблон:

```bash
# Создайте папку для конфигурации ddclient
mkdir /mnt/docker-volumes/ddclient/config -p
# Отрендерите шаблон
set -o allexport
. .env
set +o allexport
envsubst < ./ddclient.template.conf > /mnt/docker-volumes/ddclient/config/ddclient.conf
```

3. Запустите стек.