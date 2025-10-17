# dockge

Удобный веб интерфейс для управления стаками докер композа.

# Референсы

- https://github.com/louislam/dockge
- https://github.com/louislam/dockge/blob/master/compose.yaml

# Пометки

Настройте файл `.env` с вашими личными секретами и запустите стек:

```env
STACKS_FOLDER_PATH=/your/path/to/homelab-stacks/stacks
```
```bash
# Создайте папку для данных dockge
mkdir /mnt/docker-volumes/dockge/data -p
```

При первом запуске надо будет перейти по `http://<имя_хоста>:5001` для первоначальной настройки. 