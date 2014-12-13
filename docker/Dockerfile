# pocketmine 
#
# VERSION 0.1
#
# SVN: $Id$
# Created: 2014.12.11
# Copyright: Steven E. Pav, 2014
# Author: Steven E. Pav
# Comments: Steven E. Pav

FROM ubuntu

MAINTAINER Steven E. Pav <shabbychef@gmail.com>

RUN (apt-get update; \
	apt-get install -y make autoconf automake libtool m4 wget curl python3-yaml; \
	mkdir -p /opt/pocketmine; \
	cd /opt/pocketmine && curl -sL http://get.pocketmine.net/ | bash -s - -r -v development)

VOLUME /var/pocketmine
WORKDIR /var/pocketmine

EXPOSE 19132

ENTRYPOINT ["/opt/pocketmine/bin/php5/bin/php"]
CMD ["/opt/pocketmine/PocketMine-MP.phar", "--no-wizard", "--enable-rcon=on","--allow-flight=true","--motd-dockermine","--view-distance=60","--memory-limit=1024M"]

#for vim modeline: (do not edit)
# vim:nu:fdm=marker:fmr=FOLDUP,UNFOLD:cms=#%s:syn=Dockerfile:ft=Dockerfile:fo=croql
