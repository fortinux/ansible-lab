# Rocky Linux 8 image
FROM rockylinux:8

# Install OpenSSh server and vim
RUN dnf -y install openssh-server openssh-clients vim

# Created public key. It's required when starting sshd
RUN ssh-keygen -f /etc/ssh/ssh_host_rsa_key -N '' -t rsa
RUN ssh-keygen -f /etc/ssh/ssh_host_ecdsa_key -N '' -t ecdsa

# Allow login as root
RUN sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config

# Specify root password
RUN echo "root:" | chpasswd

EXPOSE 22

# Start sshd
CMD ["/usr/sbin/sshd", "-D"]
