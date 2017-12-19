FROM openjdk:8-jdk

ENV JG_VERSION 0.2.0

ENV HOME /home/janusgraph

RUN groupadd --gid 1000 janusgraph \
  && useradd --uid 1000 --gid janusgraph --shell /bin/bash --create-home janusgraph \
  && wget https://github.com/JanusGraph/janusgraph/releases/download/v${JG_VERSION}/janusgraph-${JG_VERSION}-hadoop2.zip \
  && unzip janusgraph-*-hadoop2.zip \
  && mv janusgraph-*-hadoop2 ${HOME}/janusgraph \
  && chown janusgraph:janusgraph -R ${HOME}/janusgraph 

WORKDIR ${HOME}/janusgraph

CMD [ "/bin/bash" ]
