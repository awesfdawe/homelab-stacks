# caddy

Контейнер реверсивного прокси caddy с caddy-docker-proxy(Управление как у traefik) и cloudflare wildcard сертификатом.

# Референсы

- https://caddyserver.com/docs/
- https://hub.docker.com/_/caddy
- https://github.com/lucaslorentz/caddy-docker-proxy
- https://github.com/caddy-dns/cloudflare
- https://github.com/awesfdawe/builds/blob/main/caddy/Dockerfile

# docker volumes mapping

Создайте папку для данных caddy контейнера.

```bash
mkdir /mnt/docker-volumes/caddy/data -p
sudo chown 1000:1000 /mnt/docker-volumes/caddy/ -R
sudo chmod 775 /mnt/docker-volumes/caddy/ -R
```

# Пометки

Композ подразумевает наличие домена на Cloudflare, API ключа с доступом к DNS:Edit для нужной вам зоны, а так же закрытые порты 443, 80/tcp на роутере для предотвращения утечки данных.

Настройте файл `.env` с вашими личными секретами и запустите стек:

```env
API_KEY=dsadsadsajdajjdajsdajdasjsda
DOMAIN=i.example.com
```