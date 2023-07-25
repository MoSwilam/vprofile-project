FROM nginx

LABEL project="V-Profile"
LABEL maintainer="Mo Swilam"

# REMOVE default nginx config
RUN rm /etc/nginx/conf.d/default.conf

# COPY our nginx config
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf