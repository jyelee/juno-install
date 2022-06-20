FROM centos:7.2.1511
RUN yum -y install wget openssh-clients git vim net-tools gcc automake autoconf libtool make gcc-c++

WORKDIR /root/juno-install/shell

ADD docker/src/.bashrc /root/

COPY shell/ /root/juno-install/shell

RUN mkdir -p /root/juno-install/shell/config

COPY config/juno/ /root/juno-install/shell/config/juno

COPY config/grafana/ /root/juno-install/shell/config/grafana

COPY config/prometheus/ /root/juno-install/shell/config/prometheus

COPY soft/ /root/juno-install/shell/soft

RUN sh /root/juno-install/shell/install.sh -y

CMD ["/sbin/my_init"]
