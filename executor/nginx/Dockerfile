FROM ubuntu:14.04
MAINTAINER Mathias Held "office@mathias-held.de"

RUN apt-get update -y
RUN apt-get install -y nginx
RUN apt-get install -y python
RUN apt-get install -y ruby1.9.1-dev
RUN apt-get install -y wget
RUN wget https://bootstrap.pypa.io/ez_setup.py -O - | sudo python
RUN easy_install supervisor

ENV RVM_PATH /home/rvm
ENV TARGET_DIR /opt/app
WORKDIR $TARGET_DIR

RUN echo 'Hi man, here is ngix' > /usr/share/nginx/html/index.html
#run when starting container

#ENTRYPOINT [ "/usr/sbin/nginx"]
#CMD ["-h"]
#EXPOSE 80

RUN groupadd nginx
RUN useradd -g nginx nginx
USER nginx

VOLUME ["/opt/project", "/c/Users/Mathias/docker/shares"]
ADD Dockerfile /tmp/
ONBUILD RUN echo `date` > /tmp/builddate

