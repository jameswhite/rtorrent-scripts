FROM scratch
ADD rootfs.tar.xz /
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y procps mosquitto vim net-tools mosquitto-clients
EXPOSE 1883
COPY work /root/work
CMD ["/root/work",">","/var/log/work.log","2>&1"]

# mosquitto_sub -h 127.0.0.1 -p 1883 -t '#' &
# mosquitto_pub -h 127.0.0.1 -p 1883 -t "hello" -m "hello there."
