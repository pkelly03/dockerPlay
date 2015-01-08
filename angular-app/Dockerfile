FROM ubuntu:14.04
MAINTAINER James Turnbull "james@example.com"
ENV REFRESHED_AT 2014-06-01

RUN apt-get update
RUN apt-get -y -q install nginx

RUN mkdir -p /var/www/html/website
RUN mkdir -p /var/www/html/website/images
RUN mkdir -p /var/www/html/website/scripts
RUN mkdir -p /var/www/html/website/styles
RUN mkdir -p /var/www/html/website/views

ADD nginx/global.conf /etc/nginx/conf.d/
ADD nginx/nginx.conf /etc/nginx/

COPY webapp/*.html /var/www/html/website/
COPY webapp/favicon.ico /var/www/html/website/
COPY webapp/robots.txt /var/www/html/website/

COPY webapp/images/*.png /var/www/html/website/images/
COPY webapp/scripts/*.js /var/www/html/website/scripts/
COPY webapp/styles/*.css /var/www/html/website/styles/
COPY webapp/views/*.html /var/www/html/website/views/

EXPOSE 80

CMD ["/bin/bash"]
