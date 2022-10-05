FROM centos:8

MAINTAINER "Märt Maiste" <mart.maiste@gmail.com>

RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
    yum -q -y update && \
    yum -q -y install postgresql sudo telnet bacula-libs bacula-common bacula-director bacula-console && \
    sed -i -e "s/Defaults    requiretty.*/ #Defaults    requiretty/g" /etc/sudoers && \
    yum clean all

CMD [ "/usr/sbin/bacula-dir", "-u", "bacula", "-c", "/etc/bacula/bacula-dir.conf", "-d", "50", "-f"]

EXPOSE 9101
