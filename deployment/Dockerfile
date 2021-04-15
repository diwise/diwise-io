FROM registry.access.redhat.com/ubi8/nginx-118

COPY ./deployment/conf/nginx.conf /etc/nginx/nginx.conf

ADD ./public_html .

# Run script uses standard ways to run the application
CMD nginx -g "daemon off;"
