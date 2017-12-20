FROM resin/rpi-raspbian:stretch


#RUN echo "deb-src http://archive.raspbian.org/raspbian/ stretch main contrib non-free rpi" >> /etc/apt/sources.list && apt-get update && mkdir ~/unrar-nonfree && cd ~/unrar-nonfree && apt-get build-dep unrar-nonfree && apt-get source -b unrar-nonfree && dpkg -i unrar*.deb && cd && rm -r ~/unrar-nonfree  && rm -rf /var/lib/apt/lists/*

#RUN apt-get update && apt-get install sabnzbdplus python-openssl p7zip-full unzip par2 python-yenc && rm -rf /var/lib/apt/lists/*
RUN apt-get update && apt-get install python-cheetah wget && rm -rf /var/lib/apt/lists/* 

RUN wget --no-check-certificate https://github.com/midgetspy/Sick-Beard/tarball/master -O sickbeard.tar.gz && tar -xzvf sickbeard.tar.gz && mv midgetspy-Sick-Beard-* SickBeard
 
VOLUME /data
VOLUME /config

EXPOSE 8081

CMD python /SickBeard/SickBeard.py --datadir /config/data --config /config/config.ini -p 8081 --nolaunch
#CMD /usr/bin/sabnzbdplus -f /config/sabnzbd.ini -s 0.0.0.0:8080 -b 0 
