FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .
# we can remove while in developement and use the bind volume instead of that, but in production do not do that, because we are not point the code from the bind volume.

ARG DEFAULT_PORT=80

ENV PORT $DEFAULT_PORT
# Point to the arg variable which is specified above

EXPOSE $PORT

# VOLUME [ "/app/node_modules" ]

CMD [ "npm", "start" ]

# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback  feedback-node:volumes   
# run the docker container with the specified named volume feedback

# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v "C:/Users/tigin/source/repos/Docker-Course/Section 3/data-volumes-02-added-dockerfile:/app"  feedback-node:volumes
# or
# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v "$(pwd):/app" feedback-node:volumes
# attach the folder in the host machine to the docker container app section

# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v "$(pwd):/app" -v /app/node_modules feedback-node:volumes
# override the node_modules from the app container (-v with longer the path name will survive in the container, it will override from the folder coming outside of the docker)
# or
# specify the folder in the dockerfile

# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v "$(pwd):/app:ro" -v /app/temp -v /app/node_modules feedback-node:volumes
# making the host folder as readonly for the docker

# docker run -d -p 3000:8000 --env PORT=8000 --rm --name feedback-app -v feedback:/app/feedback -v "$(pwd):/app:ro" -v /app/temp -v /app/node_modules feedback-node:env
# setup the env variables

# docker run -d -p 3000:8000 --env-file ./.env  --rm --name feedback-app -v feedback:/app/feedback -v "$(pwd):/app:ro" -v /app/temp -v /app/node_modules feedback-node:env 
# Specify the env varibales in the file

# docker build -t feedback-node:dev --build-arg DEFAULT_PORT=8000 .
# Specify the argument varibales in the building the image time