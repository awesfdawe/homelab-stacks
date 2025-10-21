# wireguard

Контейнер wireguard vpn для удалённого доступа к сервисам.
# Референсы

- https://docs.linuxserver.io/images/docker-wireguard/

# docker volumes mapping

Создайте папку для конфигурации wireguard контейнера.

```bash
mkdir /mnt/docker-volumes/wireguard/config -p
sudo chown 1000:1000 /mnt/docker-volumes/wireguard -R
sudo chmod 775 /mnt/docker-volumes/wireguard -R
```

# Пометки

Настройте файл `.env` с вашими личными секретами и запустите стек:

```env
DDNS=ddns.example.com
```