FROM ghcr.io/danielbrendel/hortusfox-web:v6.3

RUN cp /usr/local/bin/docker-entrypoint.sh /usr/local/bin/hortusfox-upstream-entrypoint
COPY entrypoint.sh /usr/local/bin/hortusfox-railway-entrypoint
COPY apache-start.sh /usr/local/bin/hortusfox-apache-start
RUN chmod +x /usr/local/bin/hortusfox-railway-entrypoint /usr/local/bin/hortusfox-apache-start

EXPOSE 80
ENTRYPOINT ["/usr/local/bin/hortusfox-railway-entrypoint"]
