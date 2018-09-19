# NGINX stable image uses Debian "stretch" release (LTS is jessie)
FROM nginx:stable
RUN rm /etc/nginx/conf.d/*
COPY nginx.conf /etc/nginx/
COPY www.conf /etc/nginx/conf.d/
