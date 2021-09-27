# magma-feg

### Install FeG

download and unzip magma repo:
```bash
wget https://github.com/magma/magma/archive/refs/tags/v1.6.0.zip
unzip v1.6.0.zip
```

move to FeG install folder:
```bash
cd magma-1.6.0/orc8r/tools/docker
```

copy following file to above directory:
```
rootCA.pem
control_proxy.yml
.env
```

Delete code blocks: `script hasn't changed` and `docker login`:
```bash
cp install_gateway.sh install_gateway.sh.bak
sed -i '80,84d;181,184d' install_gateway.sh
```

install FeG:
```bash
sudo ./install_gateway.sh feg
```
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

