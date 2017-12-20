FROM resin/rpi-raspbian:stretch

RUN apt-get update && apt-get install python-cheetah python-openssl python-lxml wget && rm -rf /var/lib/apt/lists/* 

RUN wget --no-check-certificate https://github.com/CouchPotato/CouchPotatoServer/tarball/master -O couchpotato.tar.gz && tar -xzvf couchpotato.tar.gz && mv CouchPotato-CouchPotatoServer-* CouchPotato
 
VOLUME /data
VOLUME /config

EXPOSE 5050

CMD python /CouchPotato/CouchPotato.py --data_dir /config --console_log 
