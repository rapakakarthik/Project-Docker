FROM php:8.0-apache
RUN apt-get update && apt-get install -y \
    apache2 \
    && a2enmod rewrite
COPY . /var/www/html/
RUN chown -R www-data:www-data /var/www/html && \
    chmod -R 755 /var/www/html
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf
EXPOSE 80