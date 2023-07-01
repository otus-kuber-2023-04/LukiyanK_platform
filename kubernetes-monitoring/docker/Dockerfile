FROM centos:7

ENV TZ=Europe/Moscow

RUN yum install -y epel-release && yum install -y nginx
RUN yum clean all
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

ADD ./nginx.conf /etc/nginx/nginx.conf

CMD [ "nginx" ]
