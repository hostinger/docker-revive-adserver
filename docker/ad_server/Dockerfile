FROM php:5.6-fpm
RUN docker-php-ext-install pdo pdo_mysql mbstring mysql
COPY conf/php.ini /usr/local/etc/php/
RUN curl -L https://github.com/revive-adserver/revive-adserver/archive/v3.2.2.tar.gz | tar -zx -C /var/www/html/ --strip-components=1

RUN find /var/www/html/var -type d -exec chmod 700 {} +
RUN find /var/www/html/var -type f -exec chmod 600 {} +
RUN chmod 700 /var/www/html/var

RUN chown -R www-data:www-data /var/www/html/plugins
RUN chmod 700 /var/www/html/plugins
RUN chown -R www-data:www-data /var/www/html/www/admin/plugins
RUN chmod 700 /var/www/html/www/admin/plugins
RUN chown -R www-data:www-data /var/www/html/

VOLUME /var/www/html
EXPOSE 9000