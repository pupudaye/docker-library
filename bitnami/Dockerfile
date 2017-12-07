FROM bitnami/php-fpm:5.6
MAINTAINER Waitfish <lipu8829@qq.com>
RUN apt-get update
RUN apt-get -y install gcc
RUN apt-get -y install g++
ADD m4-1.4.18.tar.gz /opt/bitnami
WORKDIR /opt/bitnami/m4-1.4.18
RUN ./configure && make && make install
ADD autoconf-2.69.tar.xz /opt/bitnami
WORKDIR /opt/bitnami/autoconf-2.69
RUN ./configure && make && make install
ADD redis-3.1.4.tgz /opt/bitnami
WORKDIR /opt/bitnami/redis-3.1.4
RUN /opt/bitnami/php/bin/phpize
RUN ./configure –with-php-config=/opt/bitnami/php/bin/php-config
RUN make
RUN make install

WORKDIR /app
ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["/run.sh"]
