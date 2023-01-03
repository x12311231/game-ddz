FROM hyperf/hyperf:7.4-alpine-v3.15-swoole-v4.8

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories

RUN set -ex && apk update && apk add --no-cache libstdc++ openssl git bash     && apk add --no-cache --virtual .build-deps $PHPIZE_DEPS libaio-dev openssl-dev curl-dev

RUN pecl install msgpack && echo 'extension=msgpack.so' > /etc/php7/conf.d/50_msgpack.ini

#RUN apk del .build-deps
