# mihomo
https://wiki.metacubex.one/ru/config/

1. Заполнить .env по шаблону .env.example
2. Отрендерить шаблон
```bash
set -o allexport
. .env
set +o allexport
envsubst < ./config.template.yaml > ./data/config.yaml
```