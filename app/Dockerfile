# we define the python version we used
FROM python:3.8.0-alpine

# set a directory when we work
WORKDIR /usr/src/app

# this code avoid the python writing pyc files to disc 
ENV PYTHONDONTWRITEBYTECODE 1

# this code prevents that python buffering stdout and stderr in a console
ENV PYTHONUNBUFFERED 1

# we add dependencies
RUN apk update \
        && apk add postgresql-dev gcc python3-dev musl-dev
# first upgrade pip tool 
RUN pip install --upgrade pip

# copied requirements fiel to root folder app 
COPY ./requirements.txt /usr/src/app/requirements.txt

# install all requiriments from file requitements.txt
RUN pip install -r requirements.txt

# copied project
COPY . /usr/src/app/
