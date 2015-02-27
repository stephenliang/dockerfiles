FROM ubuntu
MAINTAINER Stephen Liang <docker-maint@stephenliang.pw>

RUN apt-get update && apt-get install -y openjdk-7-jre-headless curl && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV VERSION 3.4.6

RUN curl http://www.gtlib.gatech.edu/pub/apache/zookeeper/zookeeper-${VERSION}/zookeeper-3.4.6.tar.gz | tar -xz -C /opt \
	&& mv /opt/zookeeper-${VERSION} /opt/zookeeper \
	&& mv /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg \
	&& mkdir -p /tmp/zookeeper

EXPOSE 2181
VOLUME ["/opt/zookeeper/conf", "/tmp/zookeeper"]
CMD /opt/zookeeper/bin/zkServer.sh start-foreground
