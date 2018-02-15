FROM python:3.6.1

LABEL NAME ansible-role-supervisor-test
LABEL VERSION 0.0.0

COPY ./requirements/ /usr/src/requirements/
COPY ./requirements.txt /usr/src/requirements.txt

# set working directory to /usr/src/
WORKDIR /usr/src/

RUN pip install -r /usr/src/requirements/test.txt
