FROM python:alpine

# Skip "export" module since "cassandra-driver" fails to compile on Raspberry Pi 3B+
RUN apk add --no-cache --virtual .build_deps \
	gcc \
	linux-headers \
	musl-dev \
	&& pip install 'glances[action,browser,cloud,cpuinfo,docker,folders,gpu,graph,ip,raid,snmp,web,wifi]' \
	&& apk del .build_deps

# Define working directory.
WORKDIR /glances

# EXPOSE PORT (For XMLRPC)
EXPOSE 61209

# EXPOSE PORT (For Web UI)
EXPOSE 61208

# Define default command.
CMD python -m glances -C /glances/conf/glances.conf $GLANCES_OPT
