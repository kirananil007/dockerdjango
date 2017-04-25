FROM ubuntu:14.04

MAINTAINER Kiran Anil

ENV DOCKYARD_SRC=helloworld

ENV DOCKYARD_SRVHOME=/srv

ENV DOCKYARD_SRVPROJ=/srv/helloworld

RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y python python-pip

WORKDIR $DOCKYARD_SRVHOME
RUN mkdir media static logs
VOLUME ["$DOCKYARD_SRVHOME/media/", "$DOCKYARD_SRVHOME/logs/"]

COPY $DOCKYARD_SRC $DOCKYARD_SRVPRO

RUN pip install -r $DOCKYARD_SRVPROJ/requirements.txt

EXPOSE 8000

WORKDIR $DOCKYARD_SRVPROJ
COPY ./docker-entryscript.sh /
ENTRYPOINT ["/docker-entryscript.sh"]


