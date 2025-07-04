#set the base image to create the image for react app
FROM node:20-alpine

#create a user to run the app
# this is a good practice to run the app as a non-root user
RUN  addgroup app && adduser -S -G app app

# set the user to run the app
USER app

# set the working directory
WORKDIR /app

# copy the package.json and package-lock.json files
COPY package*.json ./

# sometimes the ownership of the files in the working directory is changed to root, thus the app can't acceess the files and throws an error access-> permission denied
# to avoid this, change the ownership of the files to the root user

USER root

#change the ownership of the files to the app user
RUN chown -R app:app .

#change the use back to app user
USER app

# install the dependencies
RUN npm install

# copy the rest of the files
COPY . .

# expose port 5173 to tell Docker that the container listens on this port at runtime
EXPOSE 5173

# command to run the app
CMD ["npm", "run", "dev"]

