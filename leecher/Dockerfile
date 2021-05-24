FROM scratch
ADD rootfs.tar.xz /
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y procps net-tools vim screen rtorrent mktorrent
RUN mkdir -p /opt/rtorrent/log
RUN mkdir -p /opt/rtorrent/watch
RUN mkdir -p /opt/rtorrent/download
RUN mkdir -p /opt/rtorrent/download/hit-and-run
RUN mkdir -p /opt/rtorrent/download/seed
RUN mkdir -p /opt/rtorrent/download/start
COPY .rtorrent.rc /root/.rtorrent.rc
COPY .screenrc /root/.screenrc
EXPOSE 6890-6899
CMD ["/bin/bash"]
