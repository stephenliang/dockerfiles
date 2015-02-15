FROM ubuntu:trusty

RUN sudo apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF && \
	echo "deb http://repos.mesosphere.io/ubuntu trusty main" |  sudo tee /etc/apt/sources.list.d/mesosphere.list && \
	sudo apt-get -y update && \
	sudo apt-get -y install marathon

CMD marathon
EXPOSE 8080
