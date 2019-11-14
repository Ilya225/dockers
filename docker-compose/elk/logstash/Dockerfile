FROM docker.elastic.co/logstash/logstash:6.8.3
RUN rm -f /usr/share/logstash/pipeline/logstash.conf
ADD config/ /usr/share/logstash/pipeline/
ADD config/ /usr/share/logstash/config/
ADD config/ /etc/logstash/conf.d