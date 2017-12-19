# docker-janusgraph
Dockerfiles for JanusGraph


### Build with hosts params

```shell
    docker build --build-arg ES_HOST=10.54.0.4,10.54.0.5,10.54.0.3 ZK_HOST=10.55.0.7,10.55.0.5,10.55.0.6 jesuejunior/janusgraph-server
```