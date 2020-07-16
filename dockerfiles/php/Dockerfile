ARG ALPINE_VERSION
FROM alpine:${ALPINE_VERSION}
LABEL Maintainer="harrett <codeproter@gmail.com>" \
      Description="Lightweight container with PHP based on Alpine Linux."

COPY --from=composer /usr/bin/composer /usr/bin/composer
ARG CONTAINER_PACKAGE_URL
ARG TZ
RUN if [ "${CONTAINER_PACKAGE_URL}" != "" ]; then \
        sed -i "s/dl-cdn.alpinelinux.org/${CONTAINER_PACKAGE_URL}/g" /etc/apk/repositories; \
    fi && \
    apk update && \
    apk add --no-cache php7 php7-fpm php7-opcache php7-pdo_mysql php7-mysqli php7-redis php7-json php7-openssl \
        php7-phar php7-ctype php7-mcrypt php7-mbstring php7-curl php7-xml php7-gd php7-imagick php7-xdebug tzdata && \
    cp "/usr/share/zoneinfo/$TZ" /etc/localtime && \
    echo "$TZ" > /etc/timezone

VOLUME ["/var/www"]

EXPOSE 9000

ENTRYPOINT ["/usr/sbin/php-fpm7"]

CMD ["-F"]
