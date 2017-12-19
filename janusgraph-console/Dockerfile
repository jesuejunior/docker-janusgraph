FROM jesuejunior/janusgraph-server

WORKDIR /home/janusgraph/janusgraph

RUN set -x && mkdir files

VOLUME /home/janusgraph/janusgraph/files

CMD [ "/home/janusgraph/janusgraph/bin/gremlin.sh" ]
