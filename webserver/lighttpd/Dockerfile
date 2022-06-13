FROM alpine:latest
RUN apk add --update lighttpd \
  && rm -rf /var/cache/apk/* \
  && sed -i.bak "s/server.document-root/#server.document-root/g" /etc/lighttpd/lighttpd.conf
 
COPY ./config/lighttpd.conf /etc/lighttpd/lighttpd.conf
#EXPOSE 8080
COPY ./src/ /var/www/html/
WORKDIR /var/www/localhost
ENTRYPOINT ["lighttpd", "-D", "-f", "/etc/lighttpd/lighttpd.conf"]