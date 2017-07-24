FROM jetbrains/teamcity-agent:eap

RUN curl -L https://github.com/docker/compose/releases/download/1.14.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose \
    && chmod +x /usr/local/bin/docker-compose

# update to edge release of docker cli - 17.06.1 fixes docker build --pull issue
RUN sed -i 's/stable/test/' /etc/apt/sources.list.d/docker.list \
    && apt-get update \
    && apt-get upgrade -y docker-ce \
    && systemctl disable docker