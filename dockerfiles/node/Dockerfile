FROM ubuntu

# install our dependencies and nodejs

RUN apt-get update && DEBIAN_FRONTEND="noninteractive" apt-get -y install tzdata python-software-properties git build-essential nodejs npm

# use changes to package.json to force Docker not to use the cache
# when we change our application's nodejs dependencies:
ADD package*.json /tmp
RUN cd /tmp && npm install && mkdir -p /opt/app && cp -a /tmp/node_modules /opt/app/

# From here we load our application's code in, therefore the previous docker
# "layer" thats been cached will be used if possible
WORKDIR /opt/app
ADD . /opt/app

EXPOSE 51005

CMD ["node", "index.js"]
