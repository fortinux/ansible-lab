FROM rockylinux:8
ENV ANSIBLE_HOST_KEY_CHECKING False
RUN dnf install epel-release -y && \
    dnf update -y && \
    dnf install -y openssh-server openssh-clients net-tools vim && \
    dnf install -y ansible
CMD /bin/bash
