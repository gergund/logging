FROM nginx:stable

RUN  apt-get update \
&& apt-get install -y apache2-utils

COPY ./scripts/run.sh ./run.sh
COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/default.conf /etc/nginx/conf.d/default.conf

RUN ./run.sh
