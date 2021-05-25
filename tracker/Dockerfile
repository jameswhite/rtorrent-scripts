FROM scratch
ADD rootfs.tar.xz /
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y libowfat-dev make git build-essential zlib1g-dev libowfat-dev make git vim net-tools mktorrent mosquitto-clients
RUN /bin/bash -c "[ ! -d /var/cache/git ] && mkdir -p /var/cache/git; (cd /var/cache/git;  git clone git://erdgeist.org/opentracker)"
RUN /bin/bash -c "(cd /var/cache/git/opentracker; sed -i '' -e 's/^#FEATURES+=-DWANT_V6/FEATURES+=-DWANT_V6/' -e 's/#FEATURES+=-DWANT_COMPRESSION_GZIP$/FEATURES+=-DWANT_COMPRESSION_GZIP/' Makefile; make)"
EXPOSE 6969
CMD ["/var/cache/git/opentracker/opentracker"]

# check http://127.0.0.1:6969/stats
