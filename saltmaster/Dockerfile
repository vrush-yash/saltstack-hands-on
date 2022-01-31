FROM centos:centos7
ARG salt_repo_url
RUN yum update -y && \
    curl ${salt_repo_url} | tee /etc/yum.repos.d/salt.repo && \
    yum clean expire-cache && \
    yum install salt-master salt-minion salt-ssh vim git -y && \
    yum clean all && \
    rm -rf /var/cache/yum
RUN sed -i "s/#auto_accept: False/auto_accept: True/g" /etc/salt/master

ENTRYPOINT ["salt-master", "-l", "debug"]

