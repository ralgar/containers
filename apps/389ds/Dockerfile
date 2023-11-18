FROM opensuse/tumbleweed:latest
LABEL maintainer="Ryan Algar <me@ralgar.dev>"

RUN zypper install -y 389-ds timezone openssl nss_synth python3-cryptography

COPY nsswitch.conf /etc/nsswitch.conf

RUN mkdir -p /data/config && \
    mkdir -p /data/ssca && \
    mkdir -p /data/run && \
    mkdir -p /var/run/dirsrv && \
    ln -s /data/config /etc/dirsrv/slapd-localhost && \
    ln -s /data/ssca /etc/dirsrv/ssca && \
    ln -s /data/run /var/run/dirsrv && \
    chmod -R 777 /data /etc/dirsrv

COPY ./dscontainer.py /usr/bin/dscontainer
RUN chmod +x /usr/bin/dscontainer
RUN chmod +x /usr/sbin/ns-slapd

VOLUME /data

EXPOSE 3389 3636

CMD [ "/usr/bin/dscontainer", "-r" ]
