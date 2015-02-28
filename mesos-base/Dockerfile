FROM ubuntu:14.10
MAINTAINER Stephen Liang <docker-maint@stephenliang.pw>

RUN apt-get update && apt-get install -y openjdk-8-jre-headless curl && apt-get clean /tmp/* /var/tmp/*

ENV VERSION 0.21.0
ENV LIBRARY_BUILD_DEPS zlib1g-dev libcurl4-nss-dev libapr1-dev libsvn-dev libsasl2-dev python-dev
ENV RUNTIME_BUILD_DEPS openjdk-8-jdk maven build-essential
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/

RUN apt-get update && apt-get install -y ${RUNTIME_BUILD_DEPS} && \ 
	curl https://archive.apache.org/dist/mesos/${VERSION}/mesos-${VERSION}.tar.gz | tar -xvz -C /opt/  && \
	apt-get install -y ${LIBRARY_BUILD_DEPS} && \
	cd /opt/mesos* && \
	./configure && \
	make && \
	make install && \
	rm -rf /opt/mesos* && \
	apt-get purge -y --auto-remove ${RUNTIME_BUILD_DEPS}
