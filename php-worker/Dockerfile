#
#--------------------------------------------------------------------------
# Image Setup
#--------------------------------------------------------------------------
#
# To take a look at the'php-worker' base Image, visit its DockerHub page
#    https://hub.docker.com/r/nielsvdoorn/laravel-supervisor/
#

FROM nielsvdoorn/laravel-supervisor

MAINTAINER Mahmoud Zalt <mahmoud@zalt.me>

#
#--------------------------------------------------------------------------
# Optional Supervisord Configuration
#--------------------------------------------------------------------------
#
# Modify the ./supervisor.conf file to match your App's requirements.
# Make sure you rebuild your container with every change.
#
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

#
#--------------------------------------------------------------------------
# Optional Software's Installation
#--------------------------------------------------------------------------
#
# If you need to modify this image, feel free to do it right here.
#
	# -- Your awesome modifications go here -- #


#
#--------------------------------------------------------------------------
# Final Touch
#--------------------------------------------------------------------------
#
ENV PHANTOMJS_VERSION 2.1.1
COPY ./phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2  /tmp/
RUN tar xjf /tmp/phantomjs-$PHANTOMJS_VERSION-linux-x86_64.tar.bz2 -C /usr/local/ && \
    mv /usr/local/phantomjs-$PHANTOMJS_VERSION-linux-x86_64 /usr/local/phantomjs && \
    ln -s /usr/local/phantomjs/bin/phantomjs /bin/phantomjs && \
    chmod +x /bin/phantomjs





RUN rm -r /var/lib/apt/lists/* /tmp/*
WORKDIR /etc/supervisor/conf.d/
