FROM ubuntu

ENV VERSION 4.0.6

RUN apt-get update -y && apt-get install -y python2.7 python-setuptools python-imaging python-mysqldb sqlite3

ADD https://bitbucket.org/haiwen/seafile/downloads/seafile-server_${VERSION}_x86-64.tar.gz /seafile.tar.gz

RUN tar -xvzf /seafile.tar.gz -C /opt && mv /opt/seafile* /opt/seafile && rm /seafile.tar.gz

# Update the tar to foreground the seafile process
RUN sed -i 's/${seaf_controller} -c/${seaf_controller} -f -c/' /opt/seafile/seafile.sh
