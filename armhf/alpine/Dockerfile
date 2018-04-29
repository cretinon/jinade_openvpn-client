ARG ARCH=frommakefile
ARG DISTRIB=frommakefile
ARG DOCKERSRC=frommakefile
ARG USERNAME=frommakefile
#
FROM ${USERNAME}/${DOCKERSRC}:${DISTRIB}_${ARCH}
#
RUN apk add --no-cache --purge shadow openvpn iptables curl ca-certificates net-tools procps lsof && rm -rf /var/cache/apk/* 

RUN groupadd vpn
RUN mkdir /vpn

ADD http://www.privateinternetaccess.com/openvpn/ca.crt /vpn/

COPY openvpn.sh /usr/bin/

ENTRYPOINT ["openvpn.sh"]
