# arr-stack

Стак содержит следующие сервисы:
  - Prowlarr
    - Используется для запросов к торрент индексерам.
  - FlareSolverr
    - Используется для обхода капчи Cloudflare в Prowlarr.
  - Qbittorrent
    - Используется как торрент клиент. 
  - Sonarr
    - Используется для теле сериалов.
  - Radarr
    - Используется для фильмов.
  - Recyclarr
    - Используется для синхронизаций настроек Sonarr и Radarr с trash guides.

# Референсы

- https://github.com/Prowlarr/Prowlarr
- https://github.com/FlareSolverr/FlareSolverr
- https://docs.linuxserver.io/images/docker-qbittorrent/
- https://github.com/Sonarr/Sonarr
- https://github.com/Radarr/Radarr
- https://github.com/recyclarr/recyclarr
- https://trash-guides.info/

# docker volumes mapping

Создайте папки для конфигураций и данных этого стака.

```bash
sudo mkdir /mnt/docker-volumes/arr-stack/media/{movies,tv-shows,downloads} -p
sudo mkdir /mnt/docker-volumes/arr-stack/{prowlarr,qbittorrent,sonarr,radarr,recyclarr}/config -p
sudo chown 1000:1000 /mnt/docker-volumes/arr-stack/ -R
sudo chmod 775 /mnt/docker-volumes/arr-stack/ -R
```

# Пометки

Данный стак расчитан на английский язык.

Настройте файл `.env` с вашими личными секретами и запустите стек:

```env
# Основной домен должен быть таким же как у caddy
PROWLARR_DOMAIN=prowlarr.internal.example.com
QBITTORRENT_DOMAIN=qbittorrent.internal.example.com
SONARR_DOMAIN=sonarr.internal.example.com
RADARR_DOMAIN=radarr.internal.example.com
```

# Первичная настройка

1. Зайти на qbittorrent, создать аккаунт(Чтобы получить временные логин и пароль, смотреть ниже) и настроить по [гайду](https://trash-guides.info/Downloaders/qBittorrent/Basic-Setup/)

```bash
sudo docker compose logs qbittorrent
```

2. Зайти на prowlarr, sonarr, radarr для создания аккаунтов.

3. В prowlarr, sonarr, radarr зайти в Settings -> General -> Proxy. Включить его, выбрать socks5: Hostname = mihomo, port = 1080 и сохранить настройки

4. В prowlarr добавить flaresolverr, настроить индексеры, добавить sonarr и radarr.

5. В sonarr и radarr добавить qbittorrent. 

6. Добавьте апи ключи sonarr'а и radarr'а в `.env`:

```env
SONARR_API_KEY=1j292891e8u21eu821u89e128u0e
RADARR_API_KEY=weqiowuequieuqw2891em912j21e
```

7. Остановите этот композ.

8. Отрендерите шаблон:

```bash
set -o allexport
. .env
set +o allexport
envsubst < ./recyclarr.template.yml > /mnt/docker-volumes/arr-stack/recyclarr/config/recyclarr.yml
```

9. Запустите этот композ.

10. Синхронизировать настройки с trash guides:

```bash
sudo docker compose exec -it recyclarr recyclarr sync
```

11. Настроить схему имён в sonarr и prowlarr по этим гайдам:

- https://trash-guides.info/Sonarr/Sonarr-recommended-naming-scheme/
- https://trash-guides.info/Radarr/Radarr-recommended-naming-scheme/

Unmonitor Deleted Episodes = true