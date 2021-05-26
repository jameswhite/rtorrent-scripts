FROM scratch
ADD rootfs.tar.xz /
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y procps net-tools vim screen rtorrent mktorrent mosquitto-clients transmission-cli
RUN mkdir -p /opt/rtorrent/log
RUN mkdir -p /opt/rtorrent/watch
RUN mkdir -p /opt/rtorrent/download
RUN mkdir -p /opt/rtorrent/download/hit-and-run
RUN mkdir -p /opt/rtorrent/download/seed
RUN mkdir -p /opt/rtorrent/download/start
COPY .rtorrent.rc /root/.rtorrent.rc.tpl
COPY .screenrc /root/.screenrc
COPY work /root/work
EXPOSE 6890-6899
CMD ["/root/work"]
# mosquitto_sub -h mqtt -t "torrent" -C 1 | base64 -d > /opt/rtorrent/watch/start/torrentfile.torrent
