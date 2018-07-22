FROM alpine:3.8
LABEL maintainer="Miguel A. Pari Rojas"

ENV CVS_USER cvsuser
ENV CVS_PASSWD cvspass

RUN apk update
RUN apk add cvs openssl busybox-extras

COPY files/inetd.conf /etc/inetd.conf
COPY files/run.sh /

RUN chmod +x run.sh

RUN echo "cvspserver 2401/tcp" >> /etc/services

RUN mkdir /var/cvsroot

VOLUME ["/var/cvsroot"]

CMD ["/run.sh"]
