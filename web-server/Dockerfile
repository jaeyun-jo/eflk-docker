FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y wget
RUN wget https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.2.0-amd64.deb
RUN dpkg -i filebeat-7.2.0-amd64.deb


RUN apt-get install -y apache2 
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

ENTRYPOINT ["/usr/sbin/apache2"]
CMD ["-D", "FOREGROUND"]

CMD ["service", "filebeat", "start"]
