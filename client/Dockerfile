# This is multi set docker file
# The first set is named as builder, we could name it anything
FROM node:alpine as builder
# we are going to set up the working dirctory of this container to '/app'
WORKDIR '/app'
# copying package.json from our computer to the current work directory "." of container
COPY package.json .
# Run npm install command to install node modules
RUN npm install
# Copy all the files from this directory to container
COPY . .
# finally build the application
RUN npm run build


# this is the second set of this docker file
FROM nginx
# This is telling that i want to run on port 3000
EXPOSE 3000
# copy default.conf file from our computer and place it in the container
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# copy certain build directory from builder container above and put it inside this container
COPY --from=builder /app/build /usr/share/nginx/html