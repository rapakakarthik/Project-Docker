   FROM php:8.0-apache
   RUN apt-get update && apt-get install -y \
       apache2 \
       && a2enmod rewrite
   COPY dist/my-angular-app/ /var/www/html/
   RUN chown -R www-data:www-data /var/www/html && \
       chmod -R 755 /var/www/html
   RUN echo '<Directory /var/www/html/>\n\
       Options Indexes FollowSymLinks\n\
       AllowOverride All\n\
       Require all granted\n\
   </Directory>' > /etc/apache2/conf-available/my-angular-app.conf && \
       a2enconf my-angular-app
   EXPOSE 80