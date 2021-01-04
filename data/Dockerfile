FROM jenkins/jenkins:lts
ARG HOST_UID=1002
ARG HOST_GID=119

USER root

RUN apt-get update

# RUN wget https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

RUN apt-get -y install apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     software-properties-common

RUN curl -fsSL https://download.docker.com/linux/$(. /etc/os-release; echo "$ID")/gpg > /tmp/dkey; apt-key add /tmp/dkey

RUN add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/$(. /etc/os-release; echo "$ID") \
   stretch \
   stable"

RUN apt-get update

RUN apt-get -y install docker-ce

RUN curl -L “https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)” -o /usr/local/bin/docker-compose && \
   chmod +x /usr/local/bin/docker-compose && \
   ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

# RUN dpkg -i docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

# RUN rm docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

# RUN curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

# RUN chmod +x /usr/local/bin/docker-compose

# RUN groupadd -g 999 docker


RUN usermod -u $HOST_UID jenkins

RUN groupmod -g $HOST_GID docker
RUN usermod -aG docker jenkins

USER jenkins
