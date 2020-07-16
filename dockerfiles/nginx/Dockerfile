ARG ALPINE_VERSION
FROM alpine:${ALPINE_VERSION}
LABEL Maintainer="harrett <codeproter@gmail.com>" \
      Description="Lightweight container with Nginx based on Alpine Linux."

ARG CONTAINER_PACKAGE_URL
ARG TZ
RUN if [ "${CONTAINER_PACKAGE_URL}" != "" ]; then \
        sed -i "s/dl-cdn.alpinelinux.org/${CONTAINER_PACKAGE_URL}/g" /etc/apk/repositories; \
    fi && \
    apk update && \
    apk add --no-cache nginx tzdata && \
    cp "/usr/share/zoneinfo/$TZ" /etc/localtime && \
    echo "$TZ" > /etc/timezone

VOLUME ["/var/www"]

EXPOSE 80

ENTRYPOINT ["nginx"]

CMD ["-g", "daemon off;"]
