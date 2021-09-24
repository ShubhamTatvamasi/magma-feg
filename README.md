# magma-feg

### Install FeG

download and unzip magma repo:
```bash
wget https://github.com/magma/magma/archive/refs/tags/v1.5.1.zip
unzip v1.5.1.zip
```

move to FeG install folder:
```bash
cd magma-1.5.1/orc8r/tools/docker
```

copy following file to above directory:
```
rootCA.pem
control_proxy.yml
.env
```

install FeG:
```bash
sudo ./install_gateway.sh feg
```
> Delete code blocks: `script hasn't changed` and `docker login`
---

Register:
```bash
cd /var/opt/magma/docker
docker-compose exec magmad /usr/local/bin/show_gateway_info.py
```

verify connection:
```bash
cd /var/opt/magma/docker
docker-compose exec magmad /usr/local/bin/checkin_cli.py
```

stop FeG:
```bash
cd /var/opt/magma/docker
docker-compose down
```

Restart services:
```bash
cd /var/opt/magma/docker
./recreate_services.sh
```


---



### Enabling Relay To FeG

https://docs.magmacore.org/docs/next/feg/deploy_configure#enabling-relay-to-feg

check logs:
```bash
docker logs -f session_proxy
```

