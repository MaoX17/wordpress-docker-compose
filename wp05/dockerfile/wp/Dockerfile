FROM wordpress
# printf statement mocks answering the prompts from the pecl install
RUN printf "\n \n" | pecl install redis && docker-php-ext-enable redis
## PHP
COPY ./php-wp.ini /usr/local/etc/php/conf.d
## 
## APACHE
COPY ./mpm_prefork_low_trafic.conf /etc/apache2/mods-available/mpm_prefork.conf
#COPY ./mpm_prefork_low_trafic.conf /etc/apache2/mods-available/mpm_prefork.conf
RUN /etc/init.d/apache2 restart
