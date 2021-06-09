# Use ubuntu as the base image.
# Install apache2 and configure it to work on 3003 port. (do not update any other Apache configuration settings like document root etc).
FROM ubuntu

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y apache2
RUN sed -i 's/80/3003/' /etc/apache2/ports.conf
RUN sed -i 's/:80/:3003/' /etc/apache2/sites-enabled/000-default.conf
#RUN /etc/init.d/apache2 start
#https://stackoverflow.com/questions/44376852/how-to-start-apache2-automatically-in-a-ubuntu-docker-container
CMD apachectl -D FOREGROUND

EXPOSE 3003
