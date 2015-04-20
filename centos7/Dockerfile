FROM centos:7
MAINTAINER 164c <morotomi.hiroshi@gmail.com>

RUN yum update && yum install -y \
openssh \
openssh-clients \
openssh-server \
passwd \
sudo

RUN useradd centos
RUN mkdir /home/centos/.ssh
RUN curl https://github.com/164c.keys >> /home/centos/.ssh/authorized_keys
RUN chown -R centos /home/centos/.ssh 
RUN chmod 700 /home/centos/.ssh && chmod 600 /home/centos/.ssh/authorized_keys
RUN echo "centos    ALL=(ALL)    NOPASSWD:ALL" >> /etc/sudoers.d/centos

# to generate keys which are required to ssh login
# https://access.redhat.com/documentation/ja-JP/Red_Hat_Enterprise_Linux/6/html/Deployment_Guide/s1-ssh-configuration.html#table-ssh-configuration-configs-system
RUN /usr/bin/ssh-keygen -t rsa -b 2048 -f /etc/ssh/ssh_host_rsa_key -N ""

EXPOSE 22 80
ENTRYPOINT ["/sbin/init"]

