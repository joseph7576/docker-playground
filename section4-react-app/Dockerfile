# base image
FROM node:lts-alpine3.18

# these line should be type in case we might encounter premission error for writing or exec commands
# add user and group
RUN addgroup app && adduser -SG app app
# set the user
USER app

# set workdir
WORKDIR /app

# copy app files to image
COPY package*.json .

# run commands
# this will be cache if we don't change the packages in out application
RUN npm install 

# optimization
COPY . .

# set env vars
ENV API_URL=http://api.myapp.com/

# tell the container which port it should be listening
EXPOSE 3000

# default command to use when starting the container
# CMD [ "npm", "start" ] -> personal preferences :D
ENTRYPOINT [ "npm", "start" ]