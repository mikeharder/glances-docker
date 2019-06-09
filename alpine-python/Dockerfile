FROM python:alpine

RUN apk add \
  gcc \
  linux-headers \
  musl-dev

# Skip "export" module since "cassandra-driver" fails to compile on Raspberry Pi 3B+
RUN pip install 'glances[action,browser,cloud,cpuinfo,docker,folders,gpu,graph,ip,raid,snmp,web,wifi]'
