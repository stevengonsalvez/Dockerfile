FROM centos:centos6

MAINTAINER steven gonsalvez <steven.gonsalvez@gmail.com>
LABEL Vendor="CentOS"
LABEL License=GPLv2

RUN yum -y update; yum clean all
RUN yum -y install epel-release; yum clean all
RUN yum -y install open; yum clean all
RUN yum -y install java-1.7.0-openjdk.x86_64
RUN yum -y install telnet
RUN yum -y install wget
RUN yum -y install tar
RUN yum -y install which
RUN yum -y update


RUN cd ~ && wget https://repository-master.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.6.1/mule-standalone-3.6.1.tar.gz 
RUN cd /opt && tar xvzf ~/mule-standalone-3.6.1.tar.gz && rm ~/mule-standalone-3.6.1.tar.gz && ln -s /opt/mule-standalone-3.6.1 /opt/mule 



#alternate to downloading and installing everytime
#RUN cd ~
#ADD ./mule-standalone-3.6.1.tar.gz /opt
#RUN cd /opt && ln -s /opt/mule-standalone-3.6.1 /opt/mule 

# Define environment variables.d
ENV MULE_HOME /opt/mule

# Define mount points.
#VOLUME ["/opt/mule/logs", "/opt/mule/conf", "/opt/mule/apps", "/opt/mule/domains"]

# Define working directory.
WORKDIR /opt/mule

#ENV JAVA_HOME="/usr/bin"

CMD [ "/opt/mule/bin/mule" ]

# Default http port
EXPOSE 8081


