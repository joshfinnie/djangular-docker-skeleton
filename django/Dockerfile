FROM library/ubuntu:14.04
MAINTAINER Josh Finnie "josh@jfin.us"

RUN apt-get -y update
RUN apt-get install -y python python-pip python-dev libxml2-dev libxslt-dev libpq-dev python-psycopg2 git

ADD django/requirements.txt /code/requirements.txt
RUN pip install -r /code/requirements.txt

RUN apt-get -y update && apt-get -y autoremove

WORKDIR /code/
EXPOSE 8000

CMD python app/manage.py runserver 0.0.0.0:8000
