FROM almalinux:9

MAINTAINER "Märt Maiste" <mart.maiste@gmail.com>

RUN yum -q -y update && \
    yum -q -y install postgresql sudo telnet bacula-director bacula-console which pigz && \
    yum clean all

CMD [ "/usr/sbin/bacula-dir", "-u", "bacula", "-c", "/etc/bacula/bacula-dir.conf", "-d", "50", "-f"]

EXPOSE 9101
