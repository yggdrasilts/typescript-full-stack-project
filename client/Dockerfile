# The builder from node image
FROM node:12.12.0-alpine as builder

WORKDIR /app
COPY dist/issues-ui /app

# Build a small nginx image with static website
FROM nginx:1.16.0-alpine

RUN rm -rf /usr/share/nginx/html/*

COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY --from=builder /app /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
