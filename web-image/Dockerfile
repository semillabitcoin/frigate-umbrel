FROM nginx:1.27-alpine

COPY web/index.html /tmp/index.template.html
COPY web/nginx.conf /etc/nginx/conf.d/default.conf
COPY web/umbrel-qr-icon.svg /usr/share/nginx/html/umbrel-qr-icon.svg
