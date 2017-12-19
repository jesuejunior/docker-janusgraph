FROM jesuejunior/janusgraph

WORKDIR /home/janusgraph/janusgraph

ARG ZK_HOST=zk1,zk2,zk3
ARG ES_HOST=es1,es2,es3

ENV ZK_HOST $ZK_HOST
ENV ES_HOST $ES_HOST

COPY gremlin-server.yaml conf/gremlin-server/gremlin-server.yaml

RUN cp -f conf/janusgraph-hbase-es.properties conf/gremlin-server/janusgraph-hbase-es.properties \
  && set -x \
  && sed -E -i.bak 's/storage\.hostname=.*$/storage\.hostname='"$ZK_HOST"'/' conf/gremlin-server/janusgraph-hbase-es.properties \
  && sed -E -i.bak 's/storage\.backend=.*$/storage\.backend=hbase/' conf/gremlin-server/janusgraph-hbase-es.properties \
  && sed -E -i.bak 's/index\.search\.hostname=.*$/index\.search\.hostname='"$ES_HOST"'/' conf/gremlin-server/janusgraph-hbase-es.properties \
  &&  bin/gremlin-server.sh -i org.apache.tinkerpop gremlin-python 3.2.6
  
EXPOSE 8182

VOLUME /home/janusgraph/janusgraph/conf/gremlin-server
VOLUME /home/janusgraph/janusgraph/scripts

CMD [ "/home/janusgraph/janusgraph/bin/gremlin-server.sh" ]