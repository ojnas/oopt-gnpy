FROM python:3.6-slim

ARG BRANCH="develop"

ADD https://github.com/Telecominfraproject/oopt-gnpy/archive/${BRANCH}.zip /

RUN apt-get update && apt-get install -y unzip

RUN unzip ${BRANCH}.zip && rm ${BRANCH}.zip

RUN pip install -r /oopt-gnpy-develop/requirements.txt

ENV PYTHONPATH=/oopt-gnpy-develop

WORKDIR /oopt-gnpy-develop/shared/examples

ENTRYPOINT cp -nr /oopt-gnpy-develop/examples /oopt-gnpy-develop/shared && /bin/bash