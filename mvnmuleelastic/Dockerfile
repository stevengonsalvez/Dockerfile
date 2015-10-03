FROM stevengonsalvez/mulece:3.6.1
MAINTAINER steven gonsalvez <steven.gonsalvez@gmail.com>



RUN rpm --import https://packages.elastic.co/GPG-KEY-elasticsearch


COPY config/elasticsearch.repo /etc/yum.repos.d/

RUN yum install -y elasticsearch

COPY config/logging.yml /usr/share/elasticsearch/config/
COPY config/elasticsearch.yml /usr/share/elasticsearch/config/


#installing maven
RUN wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
RUN yum install -y apache-maven


CMD [ "/opt/mule/bin/mule" && "/usr/share/elasticsearch/bin/elasticsearch" ]

EXPOSE 9200
EXPOSE 8080
