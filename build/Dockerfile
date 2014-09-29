# version 1.4-1
# docker-version 0.9.1
FROM        phusion/passenger-full
MAINTAINER  guruvan "guruvan@shastafareye.net"

# We use a bootstrap script to avoid having temporary cache files and build
# dependencies being committed and included into the docker image.
ADD         bootstrap.sh /tmp/
RUN         chmod +x /tmp/bootstrap.sh
RUN         /tmp/bootstrap.sh

# Add mazacoin config & startup files
ADD         mazacoin.conf /root/.mazacoin/
ADD	    mazacoind.run /etc/service/mazacoind/run
RUN         chmod 600 /root/.mazacoin/mazacoin.conf ; chmod 700 /etc/service/mazacoind/run

#XPOSE      MZC   MZC   INSIGHT
#XPOSE      RPC   P2P   LIVE TEST
EXPOSE      12832 12835 3000 3001
#ENTRYPOINT  [""]
CMD         ["/sbin/my_init"]
