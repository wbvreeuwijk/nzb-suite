# CouchPotato
#
# Version 0.2
FROM wbvreeuwijk/nzb-base:latest
MAINTAINER Bas van Reeuwijk <bas@reeuwijk.net>

LABEL Description="This image will install a CouchPotato server" Version="1.0"

# Install Dependencies
RUN apk add --no-cache libxml2-dev libxslt-dev \
    && pip install lxml

# Get CouchPotato from Github
USER $SABNZBD_UID

RUN cd /opt && git clone https://github.com/RuudBurger/CouchPotatoServer.git couchpotato 

USER 0

# Define environement variables
ENV HOME /config

# Exposing CouchPotato web ui
EXPOSE 5050

# Create volume mount points
RUN mkdir -p /downloads/complete \
    && chown -R $SABNZBD_UID /downloads

# Define container volume
VOLUME ["/config","/video","/downloads/complete"]

# Setting start CMD
CMD ["/usr/bin/python", "/opt/couchpotato/CouchPotato.py", "--data_dir","/config","--console_log"]
