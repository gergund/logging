FROM ubuntu:bionic

RUN  apt-get update \
&& apt-get install -y nginx libnginx-mod-http-geoip apache2-utils wget

COPY ./scripts/run.sh ./run.sh
COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/default.conf /etc/nginx/conf.d/default.conf

RUN mkdir /etc/nginx/geoip \
&& cd /etc/nginx/geoip \
&& wget http://geolite.maxmind.com/download/geoip/database/GeoLiteCountry/GeoIP.dat.gz \
&& gunzip GeoIP.dat.gz \ 
&& wget http://geolite.maxmind.com/download/geoip/database/GeoLiteCity.dat.gz \
&& gunzip GeoLiteCity.dat.gz

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
	&& ln -sf /dev/stderr /var/log/nginx/error.log

EXPOSE 80

STOPSIGNAL SIGTERM

CMD ./run.sh
