FROM almalinux:9

USER root

# Configure Yum 
RUN dnf install -y yum-utils \
    && yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

# install Docker CE from Yum

RUN dnf install -y sudo tar findutils git python3 python3-pip docker-ce \
    && dnf clean all

# add virtualenv
COPY python-requirements.txt /tmp/
RUN pip3 install --requirement /tmp/python-requirements.txt

# create local nonpriv user
ARG USER=luser
RUN useradd -m -s /bin/bash $USER \
    && echo "${USER} ALL=(ALL) NOPASSWD: ALL" >/etc/sudoers.d/${USER} \
    && chmod 0440 /etc/sudoers.d/${USER}

# drop privilege by default
USER ${USER}