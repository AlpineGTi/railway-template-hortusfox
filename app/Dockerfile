FROM ghcr.io/danielbrendel/hortusfox-web:v6.3

RUN printf 'User-agent: *\nDisallow: /\n' > /var/www/html/public/robots.txt
RUN a2enmod headers \
 && printf 'Header always set X-Robots-Tag "noindex, nofollow"\n' > /etc/apache2/conf-available/noindex.conf \
 && a2enconf noindex

RUN cp /usr/local/bin/docker-entrypoint.sh /usr/local/bin/hortusfox-upstream-entrypoint
COPY entrypoint.sh /usr/local/bin/hortusfox-railway-entrypoint
COPY apache-start.sh /usr/local/bin/hortusfox-apache-start
RUN chmod +x /usr/local/bin/hortusfox-railway-entrypoint /usr/local/bin/hortusfox-apache-start

EXPOSE 80
ENTRYPOINT ["/usr/local/bin/hortusfox-railway-entrypoint"]
