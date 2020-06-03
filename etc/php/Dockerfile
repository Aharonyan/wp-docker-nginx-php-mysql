ARG PHP_VERSION
FROM nanoninja/php-fpm:$PHP_VERSION
# Install wp-cli
RUN curl -o /bin/wp-cli.phar https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x /bin/wp-cli.phar && cd /bin && mv wp-cli.phar wp && mkdir -p /var/www/.wp-cli/cache && chown www-data:www-data /var/www/.wp-cli/cache

# Cron and nano text editor
RUN apt-get update -q -q && cd / && apt-get -y install nano && apt-get install -y cron 
RUN cd / && touch /etc/cron.d/crontab
RUN chmod 0644 /etc/cron.d/crontab && touch /var/log/cron.log
CMD cron && docker-php-entrypoint php-fpm

# Note: Use docker-compose up -d --force-recreate --build when Dockerfile has changed.
# This comand for use it better alias dc-wp="docker-compose run --rm php wp --allow-root"
# docker exec -it php_wp-cli bash
