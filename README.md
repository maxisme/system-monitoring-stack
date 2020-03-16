# Docker-compose files for a simple uptodate
# InfluxDB
# + Grafana stack
# + Telegraf

Run your stack:

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
