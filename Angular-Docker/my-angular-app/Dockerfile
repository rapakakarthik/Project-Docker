   # Dockerfile
   # Use the official PHP Apache image as a base
   FROM php:8.0-apache

   # Install necessary packages for Apache
   RUN apt-get update && apt-get install -y \
       apache2 \
       && a2enmod rewrite

   # Copy the Angular build output to the Apache document root
   COPY dist/my-angular-app/ /var/www/html/

   # Set permissions for the Apache user
   RUN chown -R www-data:www-data /var/www/html && \
       chmod -R 755 /var/www/html

   # Configure Apache to allow .htaccess overrides
   RUN echo '<Directory /var/www/html/>\n\
       Options Indexes FollowSymLinks\n\
       AllowOverride All\n\
       Require all granted\n\
   </Directory>' > /etc/apache2/conf-available/my-angular-app.conf && \
       a2enconf my-angular-app

   # Expose port 80
   EXPOSE 80