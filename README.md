# docker-nzb-suite

Ever wanted to setup a complete environment that does the following
* Downloads NZB files
* Searches for new episodes of your favourite show and downloads them when they appear
* Search for new movies and downloads them when they appear
* Add subtitles to your Movies and TV shows
* Combine multiple newzbin search providers into one simple interface
* Use Spotweb as an alternative newzbin provider

All you need is
1. A running docker environment
2. A usenet provider
3. A MySQL database (add this to the compose file and change parameters)

Get the *docker-compose.yml* file and modify the parameters to your liking

Usage:
`docker-compose up -d`

The following services will be started:
* SABNzbd       (https://sabnzbd.org/):                   8080
* SickBeard     (http://sickbeard.com/):                  8081
* CouchPotato   (https://couchpota.to/):                  5050
* NZBmegaSearch (http://pillone.github.io/usntssearch/):  5005
* Spotweb       (https://github.com/spotweb/spotweb):     18888
