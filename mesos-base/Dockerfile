FROM ubuntu:14.10
MAINTAINER Stephen Liang <docker-maint@stephenliang.pw>

RUN apt-get update && apt-get install -y openjdk-8-jre-headless curl && apt-get clean /tmp/* /var/tmp/*

ENV VERSION 0.21.0
ENV BUILD_DEPS zlib1g-dev libcurl4-nss-dev libapr1-dev libsvn-dev libsasl2-dev openjdk-8-jdk maven python-dev

RUN apt-get update && apt-get install -y build-essential && \ 
	curl https://archive.apache.org/dist/mesos/${VERSION}/mesos-${VERSION}.tar.gz | tar -xvz -C /opt/  && \
	apt-get install -y ${BUILD_DEPS} && \
	cd /opt/mesos* && \
	make && \
	make install && \
	rm -rf /opt/mesos* && \
	apt-get purge -y --auto-remove ${BUILD_DEPS}
