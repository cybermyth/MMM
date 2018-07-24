FROM debian:latest
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get -y upgrade
RUN apt-get -y --no-install-recommends install python-pip mysql-client python-dev default-libmysqlclient-dev python-mysqldb
RUN pip install --upgrade setuptools wheel
RUN pip install flask flask-Mysql
RUN mkdir -p /opt/master
ADD app.py /opt/master/app.py
ADD prepare_db.py /opt/master/prepare_db.py
ADD templates /opt/master/templates
ENTRYPOINT python /opt/master/app.py 
