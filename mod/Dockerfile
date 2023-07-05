FROM nzzaidi/baota-docker:ln

RUN bash /www/server/panel/install/install_soft.sh 0 install php 8.0 \
    && bash /www/server/panel/install/install_soft.sh 0 install fileinfo 80 \
    && bash /www/server/panel/install/install_soft.sh 0 install gmp 80 \
    && bash /www/server/panel/install/install_soft.sh 0 install redis 80 \
    && bash /www/server/panel/install/install_soft.sh 0 install opcache 80 \
    && chkconfig --level 2345 redis off \
    && rm -f /usr/bin/redis-cli \
    && rm -f /etc/init.d/redis \
    && rm -rf /www/server/redis \
    && rm -rf /www/server/panel/plugin/redis \
    && sed -i -E 's/,(symlink|putenv|proc_open|proc_get_status|exec|pcntl_signal|pcntl_alarm|pcntl_async_signals),/,/g' /www/server/php/80/etc/php.ini \
    && sed -i 's/msonedrive/php-8.0/' /www/server/panel/config/index.json \
    && sed -i 's/score/backup/' /www/server/panel/config/index.json
