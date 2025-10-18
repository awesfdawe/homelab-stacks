# ddclient

Контейнер DDNS.

# Референсы

- https://docs.linuxserver.io/images/docker-ddclient/
- https://github.com/ddclient/ddclient
- https://ddclient.net/

# docker volumes mapping

Создайте папку для конфига ddclient контейнера.

```bash
mkdir /mnt/docker-volumes/ddclient/config -p
sudo chown 1000:1000 /mnt/docker-volumes/ddclient/ -R
sudo chmod 775 /mnt/docker-volumes/ddclient/ -R
```

# Пометки

Шаблон подразумевает наличие домена на Cloudflare, API ключа с доступом к DNS:Edit для нужной вам зоны.

1. Настройте файл `.env` с вашими личными секретами:

```env
API_KEY=kaewkekwKEWOEo2eokekWEKo2eke
ZONE=example.com
DOMAIN=ddns.example.com
```

2. Отрендерите шаблон:

```bash
set -o allexport
. .env
set +o allexport
envsubst < ./ddclient.template.conf > /mnt/docker-volumes/ddclient/config/ddclient.conf
```

3. Запустите стек.