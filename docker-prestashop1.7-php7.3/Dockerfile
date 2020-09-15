FROM "prestashop/prestashop:1.7-7.3-apache"

RUN apt-get -y update && apt-get -y install vim
RUN a2enmod ssl
RUN mkdir /etc/apache2/ssl/
COPY prestashop.localhost+3.pem /etc/apache2/ssl/
COPY prestashop.localhost+3-key.pem /etc/apache2/ssl
RUN rm -rf /etc/apache2/sites-available/000-default.conf
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf
RUN service apache2 start
