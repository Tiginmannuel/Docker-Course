FROM node
# use the base line image of node
WORKDIR /app
# tell the docker all the subsequent command need to run on the above specified folder
COPY package.json /app
# package.json is used while npm install so first it copy to /app
RUN npm install
# then install dependencies with that package.json
COPY . ./ 
#copy the all files in this folder to docker app folder (./ means /app because we set the workdir to /app already)
EXPOSE 80
# optional instruction 
# RUN node server.js don't do this image is just image. it's used to run on the container
CMD ["node", "server.js"]


# docker cp sad_hofstadter:/test/text.txt dummy
# Used to copy the file from the docker to local system

# docker run -p 3000:80 -d --rm --name testNodeWithName c77123d7488d
# docker run against a image with specified port in the local machine:docker and in detach mode and with remove automatically and with name

# docker build -t bmi-app:1 .
# used to build images with tag

# docker push IMAGE NAME
# docker pull IMAGE NAME