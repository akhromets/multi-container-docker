# docker build -f Dockerfile.dev .
# docker run -it -p 5000:5000 <ContainerID> --> http://localhost:5000

# Specify a base image
FROM node:alpine

WORKDIR '/app'

# Install dependencies
COPY package*.json ./
RUN npm install

# reminder to use COPY in production
COPY ./ ./

# Default command
CMD ["npm", "run", "start"]
