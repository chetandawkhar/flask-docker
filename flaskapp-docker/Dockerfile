FROM ubuntu:18.04
MAINTAINER chetandawkhar@gmail.com

RUN apt-get update -y
RUN apt-get install python3-pip -y
RUN apt-get install gunicorn3 -y

COPY requirements.txt requirements.txt
COPY flaskapp /opt/

RUN pip3 install -r requirements.txt
WORKDIR /opt/

CMD ["/usr/local/bin/gunicorn","-b","0:0:0:0:8000","app:app","--workers"]
#CMD /usr/local/bin/gunicorn --access-logfile - --error-logfile - -b :8000 app:app
