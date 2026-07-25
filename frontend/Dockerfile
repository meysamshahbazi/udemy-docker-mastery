FROM node:lts-alpine AS builder 
# node:16-alpine

WORKDIR '/app'
COPY package.json .
RUN npm install

COPY . . 
RUN npm run build

FROM nginx
EXPOSE 80
# /app/build
COPY --from=builder /app/build /usr/share/nginx/html
