FROM fedora

WORKDIR /

ENV NGINX_DEST /usr/share/nginx/html

RUN yum upgrade -y && yum clean all
RUN yum install -y nginx && yum clean all

ADD nginx.conf /etc/nginx/nginx.conf

ADD https://raw.githubusercontent.com/ailabitmo/food-ontology/master/food.owl $NGINX_DEST/
ADD https://raw.githubusercontent.com/ailabitmo/food-ontology/master/food.html $NGINX_DEST/index.html
ADD https://raw.githubusercontent.com/ailabitmo/food-ontology/master/img/concept.jpg $NGINX_DEST/img/

RUN chmod 777 -R $NGINX_DEST/*

EXPOSE 80

CMD ["/usr/sbin/nginx"]
