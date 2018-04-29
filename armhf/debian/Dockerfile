ARG ARCH=frommakefile
ARG DISTRIB=frommakefile
ARG DOCKERSRC=frommakefile
ARG USERNAME=frommakefile
#
FROM ${USERNAME}/${DOCKERSRC}:${DISTRIB}_${ARCH}
#
RUN apt-get update && apt-get -y -q install --no-install-recommends openvpn iptables curl ca-certificates net-tools procps lsof && apt-get clean && rm -rf /var/cache/apt/* /var/lib/apt/lists/*

RUN groupadd vpn
RUN mkdir /vpn

ADD http://www.privateinternetaccess.com/openvpn/ca.crt /vpn/

COPY openvpn.sh /usr/bin/

ENTRYPOINT ["openvpn.sh"]
