FROM jenkins/jenkins:lts

USER root

RUN wget https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

RUN dpkg -i docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

RUN rm docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb


RUN curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

RUN chmod +x /usr/local/bin/docker-compose

USER jenkins
