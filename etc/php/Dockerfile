ARG PHP_VERSION
FROM nanoninja/php-fpm:$PHP_VERSION
# Install wp-cli
RUN curl -o /bin/wp-cli.phar https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x /bin/wp-cli.phar && cd /bin && mv wp-cli.phar wp && mkdir -p /var/www/.wp-cli/cache && chown www-data:www-data /var/www/.wp-cli/cache

# Note: Use docker-compose up -d --force-recreate --build when Dockerfile has changed.
# This comand for use it better alias dc-wp="docker-compose run --rm php wp --allow-root"
# docker exec -it php_wp-cli bash
