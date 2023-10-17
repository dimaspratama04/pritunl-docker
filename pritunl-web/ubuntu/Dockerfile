FROM ubuntu:22.04

RUN apt-get -y update && \
    apt-get -y install sudo && \
    apt-get -y install curl && \
    apt-get -y install gnupg && \
    apt-get -y install iputils-ping && \
    apt-get -y install systemctl  
RUN echo "deb http://repo.pritunl.com/stable/apt jammy main" | \
    sudo tee /etc/apt/sources.list.d/pritunl.list
RUN curl -fsSL  https://raw.githubusercontent.com/pritunl/pgp/master/pritunl_repo_pub.asc | \ 
    sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/pritunl.gpg
RUN sudo apt-get -y update && \
    sudo apt-get -y install apt-transport-https && \
    sudo apt-get -y install pritunl

CMD systemctl start pritunl && \
    systemctl enable pritunl
