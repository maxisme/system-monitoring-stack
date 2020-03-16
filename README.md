# Docker-compose files for a simple uptodate
# InfluxDB
# + Grafana stack
# + Telegraf

Customise the .env.example and rename to .env
as well as changing telegraf.conf.example to telegraf.conf and changing `<INFLUXDB_ADMIN_USER_PASSWORD>` to the above.

```
sudo mkdir -p /srv/docker/grafana/data
docker-compose up -d
sudo chown -R 472:472 /srv/docker/grafana/data

```

install telegraph with:

```bash
$ apt-get -y install telegraf
$ cp telegraf.conf /etc/telegraf/telegraf.conf
$ service telegraf restart
```
