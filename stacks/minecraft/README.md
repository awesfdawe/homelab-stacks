# minecraft

Контейнер сервера Minecraft.

# Референсы

- https://docker-minecraft-server.readthedocs.io/en/latest/
- https://github.com/itzg/docker-minecraft-server
- https://github.com/Mukul1127/Minecraft-Java-Flags

# Пометки

Настройте файл `.env` с вашими личными секретами и запустите стек:
```bash
# Создайте папку для конфигурации и данных minecraft
mkdir /mnt/docker-volumes/minecraft/data -p
```

```env
ADMIN_UUID=sadadsda6-7ads-4ef6-a675-123123123
PACKWIZ_URL=https://raw.githubusercontent.com/awesfdawe/minecraft-modpack/refs/heads/main/pack.toml
JVM_XX_OPTS='-XX:+UnlockExperimentalVMOptions -XX:+UnlockDiagnosticVMOptions .......'
```