FROM java:8

MAINTAINER wuhulala xueaohui_com@163.com
ENV REFRESHED_AT 2018-08-27

ENV broker_id=1
ENV zookeeper_addr=zookeeper:2181
# 自动解压
ADD kafka_2.11-1.1.1.tgz /opt/
#
RUN mv /opt/kafka_2.11-1.1.1 /opt/kafka

VOLUME /opt/kafka/logs

#RUN tar -zxvf /opt/kafka_2.11-1.1.1.tgz -C /opt/kakfa
ENTRYPOINT sed -i "123czookeeper.connect=${zookeeper_addr}" /opt/kafka/config/server.properties && sed -i "21cbroker.id=${broker_id}" /opt/kafka/config/server.properties  && /opt/kafka/bin/kafka-server-start.sh /opt/kafka/config/server.properties

