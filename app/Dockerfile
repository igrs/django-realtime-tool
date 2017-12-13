FROM python:latest

ENV PYTHONUNBUFFERED 1
RUN mkdir /app
WORKDIR /app

RUN apt-get update
RUN apt-get install -y postgresql-client

ADD ./requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt
