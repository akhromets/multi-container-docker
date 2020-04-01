# create temp container to build a project
FROM node:alpine as builder
WORKDIR '/app'
# Install dependencies
COPY package*.json ./
RUN npm install
COPY ./ ./

RUN npm run build

# copy build folder to nginx container and execute default nginx image run command
FROM nginx

EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
