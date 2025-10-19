# jellyfin

Контейнер jellyfin.

# Референсы

- https://docs.linuxserver.io/images/docker-jellyfin/
- https://jellyfin.org/docs/

# docker volumes mapping

Создайте папку для данных jellyfin контейнера.

```bash
sudo mkdir /mnt/docker-volumes/jellyfin/config -p
sudo chown 1000:1000 /mnt/docker-volumes/jellyfin/ -R
sudo chmod 775 /mnt/docker-volumes/jellyfin/ -R

sudo mkdir /mnt/docker-volumes/arr-stack/media/{movies,tv-shows} -p
sudo chown 1000:1000 /mnt/docker-volumes/arr-stack/ -R
sudo chmod 775 /mnt/docker-volumes/arr-stack/ -R
```

# Пометки

Композ использует VPN для получения метаданных и подразумевает использование caddy.
Рекомендуется настроить Hardware acceleration.

Настройте файл `.env` с вашими личными секретами и запустите стек:

```env
# Основной домен должен быть таким же как у caddy
DOMAIN=jellyfin.internal.example.com
```