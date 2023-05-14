FROM node:16 as depend

# Create app directory
WORKDIR /usr/src/build/app

# Install app dependencies
COPY package*.json ./
RUN npm install
# FROM node:16-alpine as prod
# WORKDIR /usr/src/app
# COPY --from=depend /usr/src/build/app/node_modules ./node_modules
COPY . .

EXPOSE 3000
CMD [ "node", "index.js" ]