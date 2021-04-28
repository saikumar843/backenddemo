FROM ubuntu

RUN apt-get update && apt-get upgrade \
&& apt install -y wget tar gzip apt-transport-https ca-certificates curl libcurl4 software-properties-common

WORKDIR /tmp

RUN set -x && wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-ubuntu2004-4.4.5.tgz \
&& tar -xvzf mongodb-linux-x86_64-ubuntu2004-4.4.5.tgz -C /tmp \
&& cp /tmp/mongodb-linux-x86_64-ubuntu2004-4.4.5/bin/* /usr/bin

RUN mkdir -p /var/lib/mongo \
	&& mkdir -p /var/log/mongodb \
	&& mkdir -p /data

WORKDIR /data

CMD [ "mongo" ]