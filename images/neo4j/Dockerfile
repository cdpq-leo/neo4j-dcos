FROM neo4j:3.3.3

RUN apk add -U bind-tools && rm -f /var/cache/apk/*

# Add graphaware plugins.
ADD /plugins /var/lib/neo4j/plugins

# Add graphaware configs.
ADD /config/neo4j-ga.conf /var/lib/neo4j/conf/
RUN cat /var/lib/neo4j/conf/neo4j-ga.conf >> /var/lib/neo4j/conf/neo4j.conf && \
    rm /var/lib/neo4j/conf/neo4j-ga.conf

COPY init-dcos-neo4j.sh /init-dcos-neo4j.sh

ENTRYPOINT ["/init-dcos-neo4j.sh"]
