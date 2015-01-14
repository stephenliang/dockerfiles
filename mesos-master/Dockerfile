FROM ubuntu:trusty

RUN sudo apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF && \
	echo "deb http://repos.mesosphere.io/ubuntu trusty main" |  sudo tee /etc/apt/sources.list.d/mesosphere.list && \
	sudo apt-get -y update && \
	sudo apt-get -y install mesos

CMD mesos-master
EXPOSE 8080
