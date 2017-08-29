# SickRage
#
# Version 0.2
FROM wbvreeuwijk/nzb-base:latest
MAINTAINER Bas van Reeuwijk <bas@reeuwijk.net>

LABEL Description="This image will install a SickRage server" Version="1.0"

# Install Cheetah
RUN pip install Cheetah

# Get SickBear from GitHub
USER $SABNZBD_UID

RUN cd /opt && git clone git://github.com/SickRage/SickRage.git sickrage

USER 0

# Define environement variables
ENV HOME /config

# Exposing SickBeard web ui
EXPOSE 8081

RUN mkdir -p /downloads/complete \
    && chown -R $SABNZBD_UID /downloads

# Define container volume
VOLUME ["/config","/video","/downloads/complete"]

# Setting start CMD
CMD ["/usr/bin/python", "/opt/sickrage/SickBeard.py", "--datadir=/config", "-p", "8081","--nolaunch"]
