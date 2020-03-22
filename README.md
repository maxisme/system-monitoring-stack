# Docker-compose files for a simple uptodate
# InfluxDB
# + Grafana stack
# + Telegraf

 - Customise the `env.influxdb.example` and rename to `env.influxdb` with a custom `INFLUXDB_ADMIN_PASSWORD`
 - Customise the `config/grafana.ini.example` to `config/grafana.ini`
 - Customise the `config/kapacitor.conf.example` to `config/kapacitor.conf` and setting the `[[influxdb]]` password to `INFLUXDB_ADMIN_PASSWORD`
 
```
sudo mkdir -p /srv/docker/grafana/data
docker-compose up -d
sudo chown -R 472:472 /srv/docker/grafana/data
```

install telegraph and change telegraf.conf.example to telegraf.conf and change `<INFLUXDB_ADMIN_USER_PASSWORD>` to the one set in the .env.

```bash
$ apt-get -y install telegraf
$ cp config/telegraf.conf.example /etc/telegraf/telegraf.conf
$ service telegraf restart
```
