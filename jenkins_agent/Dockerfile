ARG DEBIAN_FRONTEND=noninteractive
FROM jenkins/ssh-agent:4.2.1-jdk11
USER root 
RUN apt-get update && apt-get install -y curl git python3 python3-pip unzip ansible
# Group ID is taken from the group ID set on host.
RUN groupadd -g 997 docker && usermod -aG docker jenkins
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && unzip awscliv2.zip && ./aws/install
RUN curl -fsSL https://get.docker.com/ | sh
RUN curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose