# Docker-compose files for a simple uptodate
# InfluxDB
# + Grafana stack
# + Telegraf

Customise the .env.example and rename to .env

```
sudo mkdir -p /srv/docker/grafana/data
docker-compose up -d
sudo chown -R 472:472 /srv/docker/grafana/data
```

install telegraph and change telegraf.conf.example to telegraf.conf and change `<INFLUXDB_ADMIN_USER_PASSWORD>` to the one set in the .env.

```bash
$ apt-get -y install telegraf
$ cp telegraf.conf /etc/telegraf/telegraf.conf
$ service telegraf restart
```
