FROM centos:8

MAINTAINER "Märt Maiste" <mart.maiste@gmail.com>

ENV BACULA_COMPONENTS "bacula-libs bacula-common bacula-storage"

RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
    yum -q -y update && \
    yum -y install sudo bacula-libs bacula-common bacula-storage && \
    sed -i -e "s/Defaults    requiretty.*/ #Defaults    requiretty/g" /etc/sudoers && \
    yum clean all

VOLUME ["/var/spool/bacula"]

CMD [ "/usr/sbin/bacula-sd", "-c", "/etc/bacula/bacula-sd.conf", "-d", "50", "-f"]

EXPOSE 9103
