FROM morozovsk/php-opencv

RUN apt-get update

RUN apt-get install -y \
    apache2 \
    libapache2-mod-php7.2 \
    mc

COPY .docker/vhost.conf /etc/apache2/sites-available/000-default.conf

RUN a2enmod rewrite
CMD /usr/sbin/apache2ctl -D FOREGROUND

RUN echo "extension=opencv.so" > /etc/php/7.2/apache2/conf.d/opencv.ini