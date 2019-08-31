FROM centos:latest
RUN yum update -y && \
    yum install https://repo.saltstack.com/yum/redhat/salt-repo-2019.2.el7.noarch.rpm -y && \
    yum clean expire-cache && \
    yum install salt-master salt-minion salt-ssh -y && \
    yum clean all && \
    rm -rf /var/cache/yum
RUN sed -i "s/#auto_accept: False/auto_accept: True/g" /etc/salt/master

ENTRYPOINT ["salt-master", "-l", "debug"]

