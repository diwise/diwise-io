FROM node:10-alpine as builder

WORKDIR /vue-ui

ADD ./temperature/package*.json ./
RUN npm install

COPY ./temperature .
RUN npm run build


FROM registry.access.redhat.com/ubi8/nginx-118

COPY ./deployment/conf/nginx.conf /etc/nginx/nginx.conf

ADD ./public_html .
COPY --from=builder /vue-ui/dist /opt/app-root/src

# Run script uses standard ways to run the application
CMD nginx -g "daemon off;"
