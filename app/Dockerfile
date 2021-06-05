# Use a prebuild-image that provides NodeJS 14 LTS
FROM node:14-alpine as builder

# Set NodeJS production environment
ENV NODE_ENV=production

# Create the working directory for the application
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./
RUN npm install

# Copy App sources
COPY . .

# Expose port 3000
EXPOSE 3000

# Start the application
CMD [ "npm", "start" ]