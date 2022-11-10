FROM nhits

# Install system packages
RUN apt-get update  -y --fix-missing && \
    apt-get install -y --no-install-recommends \
    wget \
    openssh-server \
    git && \
    apt-get clean -y

RUN mkdir /etc/sudoers.d/ && echo "%docker  ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers.d/inside_sudoers

COPY entry.sh /entry.sh
RUN chmod +x /entry.sh
ENTRYPOINT ["/entry.sh"]