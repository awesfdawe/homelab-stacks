# minecraft

Контейнер сервера Minecraft.

# Референсы

- https://docker-minecraft-server.readthedocs.io/en/latest/
- https://github.com/itzg/docker-minecraft-server
- https://github.com/Mukul1127/Minecraft-Java-Flags

# docker volumes mapping

Создайте папку для данных minecraft контейнера.

```bash
mkdir /mnt/docker-volumes/minecraft/data -p
sudo chown 1000:1000 /mnt/docker-volumes/minecraft/ -R
sudo chmod 775 /mnt/docker-volumes/minecraft/ -R
```

# Пометки

Настройте файл `.env` с вашими личными секретами и запустите стек:

```env
ADMIN_UUID=sadadsda6-7ads-4ef6-a675-123123123
PACKWIZ_URL=https://raw.githubusercontent.com/awesfdawe/minecraft-modpack/refs/heads/main/pack.toml
JVM_XX_OPTS='-XX:+UnlockExperimentalVMOptions -XX:+UnlockDiagnosticVMOptions .......'
```