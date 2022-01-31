FROM centos:centos7
ARG salt_repo_url
RUN yum update -y && \
    curl ${salt_repo_url} | tee /etc/yum.repos.d/salt.repo && \
    yum clean expire-cache && \
    yum install salt-minion -y && \
    yum clean all && \
    rm -rf /var/cache/yum

RUN sed -i "s/#master: salt/master: saltmaster/g" /etc/salt/minion

ENTRYPOINT ["salt-minion", "-l", "debug"]

