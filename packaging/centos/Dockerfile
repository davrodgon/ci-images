FROM indigodatacloud/ci-images:base-c7
MAINTAINER Pablo Orviz <orviz@ifca.unican.es>

RUN yum makecache fast \
    && yum install -y findutils \
                      maven \
                      python-setuptools \
		      epel-release \
    && yum -y clean all 

# build-environment
COPY build_env.txt /tmp/ 
RUN xargs yum -y install < /tmp/build_env.txt

EXPOSE 22 

CMD ["/usr/sbin/sshd", "-D"]
