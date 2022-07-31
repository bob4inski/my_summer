
FROM nginx:alpine

COPY webapp /app

# Insert wasm type into Nginx mime.types file so they load correctly.
RUN sed -i '3i\ \ \ \ application/wasm wasm\;' /etc/nginx/mime.types

# Override default nginx config
COPY /nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf
COPY /config.sample.json /app/config.json
RUN rm -rf /usr/share/nginx/html \
  && ln -s /app /usr/share/nginx/html
