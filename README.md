# homelab-stacks

### Подготовление

1. Создать папку для docker volumes и выдать себе права на non root юзера:

```bash
sudo mkdir /mnt/docker-volumes
sudo chown <user>:<user> /mnt/docker-volumes -R
```

2. Создать нужные сети в докере:

```bash
sudo docker network create vpn
sudo docker network create proxy
sudo docker network create tunnel
```