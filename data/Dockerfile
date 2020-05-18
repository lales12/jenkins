FROM jenkins/jenkins:lts

USER root

RUN apt-get update &&  apt-get  -y install software-properties-common

RUN wget https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

RUN install apt-transport-https \
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


# RUN dpkg -i docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

# RUN rm docker-ce-cli_19.03.0~3-0~debian-stretch_amd64.deb

# RUN curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

# RUN chmod +x /usr/local/bin/docker-compose

# RUN groupadd -g 999 docker

RUN usermod -aG docker jenkins

USER jenkins
