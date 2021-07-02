FROM ubuntu:21.04
RUN apt-get update && \
    apt-get install -y c-icap libicapapi-dev clamav libc-icap-mod-virus-scan && \
    usermod -a -G c-icap c-icap && \
    mkdir -p /var/run/c-icap && \
    touch /var/run/c-icap/c-icap.id && \
    chown -R c-icap:c-icap /var/run/c-icap /etc/c-icap/

RUN /usr/bin/freshclam

COPY ./conf/*.conf /etc/c-icap/

EXPOSE 1344

#USER c-icap
CMD ["sh", "-c", "/usr/bin/freshclam -d -c 24 && /usr/bin/c-icap -f /etc/c-icap/c-icap.conf -D -N"]
