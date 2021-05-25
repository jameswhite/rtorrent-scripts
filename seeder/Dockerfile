FROM scratch
ADD rootfs.tar.xz /
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y procps net-tools vim screen rtorrent mktorrent dnsutils mosquitto-clients
RUN mkdir -p /opt/rtorrent/log
RUN mkdir -p /opt/rtorrent/watch
RUN mkdir -p /opt/rtorrent/download
RUN mkdir -p /opt/rtorrent/download/hit-and-run
RUN mkdir -p /opt/rtorrent/download/start
RUN mkdir -p /opt/rtorrent/watch/seed
# RUN /bin/dd if=/dev/urandom of=/opt/rtorrent/download/hit-and-run/torrentfile bs=512 count=10240
# RUN /usr/bin/mktorrent -v -p -a http://$(dig +short tracker):6969/announce -o /opt/rtorrent/watch/start/torrentfile.torrent /opt/rtorrent/download/hit-and-run/torrentfile
COPY .rtorrent.rc /root/.rtorrent.rc
COPY .screenrc /root/.screenrc
EXPOSE 6890-6899
CMD ["/bin/bash"]
#

# docker cp rtorrent-scripts_seeder_1:/opt/rtorrent/watch/start/torrentfile.torrent .
# docker cp torrentfile.torrent rtorrent-scripts_leecher_1:/opt/rtorrent/watch/start/torrentfile.torrent
