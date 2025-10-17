# mihomo

Контейнер с мощным ядром для использования VPN, создаёт локальный смешанный прокси (SOCKS4, SOCKS5, HTTP, HTTPS) на порту 1080, а также TUN‑интерфейс для полного обворачивания контейнера в VPN при отсутствии поддержки прокси.

# Референсы

- https://github.com/MetaCubeX/mihomo
- https://wiki.metacubex.one/ru/config/

# Пометки

Шаблон подразумевает наличия ссылки [подписки](https://wiki.metacubex.one/ru/config/proxy-providers/content/#__tabbed_1_3)

1. Настройте файл `.env` с вашими личными секретами:

```env
BASE64_PROXY_SUBSCRIPTION_URL=https://example.com/base64_subscription_path/etc/etc
```

2. Отрендерите шаблон:

```bash
# Создайте папку для конфигурации mihomo
mkdir /mnt/docker-volumes/mihomo/config -p
# Отрендерите шаблон
set -o allexport
. .env
set +o allexport
envsubst < ./config.template.yaml > /mnt/docker-volumes/mihomo/config/config.yaml
```

3. Запустите стек.