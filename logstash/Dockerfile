FROM docker.elastic.co/logstash/logstash-oss:6.2.4

ADD ./config/ /usr/share/logstash/config/
ADD ./pipeline/ /usr/share/logstash/pipeline/

EXPOSE 5000
EXPOSE 9600


