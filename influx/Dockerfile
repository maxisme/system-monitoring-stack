FROM influxdb:latest

# initialise ssl
RUN /usr/bin/openssl req -x509 -nodes -newkey rsa:2048 -keyout /etc/ssl/influxdb.key -out /etc/ssl/influxdb.crt -days 30 -subj "/C=GB/ST=London/L=London/O=maxisme/OU=maxisme/CN=max.me.uk"

# add cron to add ssl
RUN apt-get update && apt-get -y install cron
COPY CRON.txt /etc/cron.d/ssl
RUN chmod 0644 /etc/cron.d/ssl
RUN crontab /etc/cron.d/ssl

COPY influxdb.conf /etc/influxdb/influxdb.conf

CMD cron && influxd