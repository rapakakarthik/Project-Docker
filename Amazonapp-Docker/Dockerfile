FROM ubuntu:22.04
ENV DEBAIN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y apache2 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
COPY index.html /var/www/html/
COPY styles.css /var/www/html/
# COPY banner.jpg /var/www/html/
# COPY product.jpg /var/www/html/
COPY images /var/www/html/
EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]