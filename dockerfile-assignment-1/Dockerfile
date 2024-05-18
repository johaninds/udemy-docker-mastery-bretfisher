
# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
FROM node:6-alpine

EXPOSE 3000

# Install tini
RUN apk add --no-cache tini

# Create app directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package.json ./

# Install app dependencies
RUN npm install && npm cache clean --force

# Bundle app source
COPY . .

# Start the container
CMD ["/sbin/tini", "--", "node", "./bin/www"]
