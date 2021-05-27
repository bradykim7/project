# pull official base image
FROM python:3-alpine

# set work directory
WORKDIR /usr/src/app

# set environment variables
# PYTHONDONTWRITEBYTECODE: Prevents Python from writing pyc files to disc (equivalent to python -B option)
# PYTHONUNBUFFERED: Prevents Python from buffering stdout and stderr (equivalent to python -u option)

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install psycopg2 dependecies(postgresql)
RUN apk update
RUN apk add libffi-dev postgresql-dev gcc openssl-dev python3-dev musl-dev rust py-cryptography cargo

# install dependencies
RUN pip install -U pip
COPY ./requirements.txt .
COPY . .
RUN pip install -r requirements.txt

# copy project

# run entrypoint.sh
# entrypoint roles : define shellscript language when start container
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]