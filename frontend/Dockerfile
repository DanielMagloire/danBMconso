# syntax=docker/dockerfile:1
# pull official base image
FROM node

RUN npm install -g http-server

#directory to store app source code
RUN mkdir /code

COPY . ./code
#directory to store app source code
WORKDIR /code

# set environment variables
# The enviroment variables ensure that the python output is set straight
# to the terminal with out buffering it first
#ENV PYTHONDONTWRITEBYTECODE=1
#ENV PYTHONUNBUFFERED=1

# install dependencies
#RUN pip install --upgrade pip

RUN npm install -g node-gyp

#RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - 
#RUN apt-get install -y nodejs

RUN npm install --force
RUN npm run build
# copy project
#COPY . /code/
EXPOSE 8080
CMD [ "http-server", "dist" ]
#CMD ["npm", "run", "dev", "0.0.0.0:8080"]