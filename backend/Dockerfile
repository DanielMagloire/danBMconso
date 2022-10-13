# syntax=docker/dockerfile:1
# pull official base image
FROM python:3

#directory to store app source code
RUN mkdir /code

COPY . ./code
#directory to store app source code
WORKDIR /code

# set environment variables
# The enviroment variables ensure that the python output is set straight
# to the terminal with out buffering it first
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# install dependencies
RUN pip install --upgrade pip
RUN pip install psycopg2-binary
#COPY ../requirements.txt .
RUN pip install -r requirements.txt


#CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]