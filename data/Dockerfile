FROM jenkins/jenkins:lts

USER root

RUN apt-get update

RUN apt-get install docker.io

RUN curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

RUN chmod +x /usr/local/bin/docker-compose

USER jenkins
