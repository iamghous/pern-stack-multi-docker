FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
# just going to change command from docker.dev rest is similar, scripts can be found in package.json file.
CMD ["npm", "run", "start"]
