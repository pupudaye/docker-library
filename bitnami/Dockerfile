FROM bitnami/php-fpm:5.6
MAINTAINER Waitfish <lipu8829@qq.com>
ADD redis.so /opt/bitnami/php/lib/php/extensions
WORKDIR /app
ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["/run.sh"]
