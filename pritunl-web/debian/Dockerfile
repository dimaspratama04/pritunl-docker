FROM debian:buster

RUN sudo tee /etc/apt/sources.list.d/pritunl.list << EOF
    deb https://repo.pritunl.com/stable/apt buster main
    EOF
RUN apt-get -y update && \
    apt-get install -y pritunl
CMD systemctl start pritunl && \
    systemctl enable pritunl
