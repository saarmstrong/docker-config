FROM nginx:latest
RUN apt-get update && apt-get install -y vim
ADD ./ssl /etc/nginx/ssl
ADD ./nginx.conf /etc/nginx
