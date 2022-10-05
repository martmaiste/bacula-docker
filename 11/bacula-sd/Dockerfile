FROM almalinux:9

MAINTAINER "Märt Maiste" <mart.maiste@gmail.com>

ENV BACULA_COMPONENTS "bacula-libs bacula-common bacula-storage"

RUN yum -q -y update && \
    yum -y install sudo bacula-storage && \
    yum clean all

VOLUME ["/var/spool/bacula"]

CMD [ "/usr/sbin/bacula-sd", "-c", "/etc/bacula/bacula-sd.conf", "-d", "50", "-f"]

EXPOSE 9103
