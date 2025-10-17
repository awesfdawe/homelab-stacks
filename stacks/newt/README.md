# newt

Контейнер для подключения к туннелю [Pangolin](https://docs.digpangolin.com/).
Контейнер обёрнут в прокси-контейнер из-за блокировки туннелей WireGuard в России, поэтому контейнер mihomo должен быть запущен перед запуском этого композа.

# Референсы

- https://docs.digpangolin.com/manage/sites/install-site#docker-installation
- https://github.com/fosrl/newt
- https://docs.digpangolin.com/

# Пометки

Настройте файл `.env` с вашими личными секретами и запустите стек:

```env
PANGOLIN_ENDPOINT=https://example.com
NEWT_ID=qwjiwuqreiwqeeqw
NEWT_SECRET=742394732h7nhewd87ye1239e9he9812e
```