FROM nginx:latest

RUN mkdir /etc/nginx/ssl/

RUN apt-get update && apt-get install openssl

RUN openssl dhparam \
      -out /etc/nginx/dhparam.pem 4096

RUN openssl req \
      -new \
      -x509 \
      -sha256 \
      -newkey rsa:2048 \
      -days 365 \
      -nodes \
      -out /etc/nginx/ssl/nginx.pem \
      -keyout /etc/nginx/ssl/nginx.key \
      -subj "/C=JP/ST=Aichi/L=Nagoya/O=Team315/OU=IT/CN=localhost"

RUN rm /etc/nginx/nginx.conf
RUN rm /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]
