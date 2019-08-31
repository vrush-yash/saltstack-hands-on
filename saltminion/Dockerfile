FROM centos:latest
RUN yum update -y && \
    yum install https://repo.saltstack.com/yum/redhat/salt-repo-2019.2.el7.noarch.rpm -y && \
    yum clean expire-cache && \
    yum install salt-minion -y && \
    yum clean all && \
    rm -rf /var/cache/yum

RUN sed -i "s/#master: salt/master: saltmaster/g" /etc/salt/minion

ENTRYPOINT ["salt-minion", "-l", "debug"]

