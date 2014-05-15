FROM docker.local:5000/ubuntu:12.04-base

RUN apt-get update; \
    apt-get install -y git-core build-essential python-dev \
    libevent1-dev python-openssl liblzma-dev wget python-setuptools python-pip; \
    rm /var/lib/apt/lists/*_*

RUN curl -L -s https://github.com/dotcloud/docker-registry/archive/0.6.7.tar.gz | tar -v -C / -xz  
RUN mv /docker-registry-0.6.7 /docker-registry

RUN cd /docker-registry && pip install -r requirements.txt
RUN cp /docker-registry/config/boto.cfg /etc/boto.cfg

ADD config/config.yml /docker-registry/config/config.yml
VOLUME /data/docker-registry-data

EXPOSE 5000

CMD cd /docker-registry && ./setup-configs.sh && exec ./run.sh

