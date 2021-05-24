FROM scratch
ADD rootfs.tar.xz /
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y mosquitto vim net-tools
EXPOSE 1883
CMD ["/usr/sbin/mosquitto"]
# mosquitto_sub -h 127.0.0.1 -p 1883 -t '#' &
# mosquitto_pub -h 127.0.0.1 -p 1883 -t "hello" -m "hello there."
