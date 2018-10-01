FROM fluent/fluentd:v1.2

RUN apk add --update --virtual .build-deps \
    sudo autoconf automake libtool build-base ruby-dev geoip geoip-dev libmaxminddb \
 && sudo gem install \
        fluent-plugin-elasticsearch \
        fluent-plugin-rewrite-tag-filter \
	fluent-plugin-geoip 
