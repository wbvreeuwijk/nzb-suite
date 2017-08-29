# NZB MegaSearch
#
# Version 0.1
FROM wbvreeuwijk/nzb-base:latest
MAINTAINER Bas van Reeuwijk <bas@reeuwijk.net>

LABEL Description="This image will install a NZB MegaSearch server" Version="1.0"

RUN cd /opt && git clone https://github.com/actualmanx/usntssearch.git

RUN ln -s /config/custom_params.ini /opt/usntssearch/NZBmegasearch/custom_params.ini

EXPOSE 5000

VOLUME ["/config"]

CMD ["/usr/bin/python","/opt/usntssearch/NZBmegasearch/mega2.py"]



