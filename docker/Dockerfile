FROM centos
FROM python:3.5
LABEL maintainer="tbh“
run mkdir -p /root/python/
add hello.py /root/python/
add doflask.sh /root/python/
workdir /root/python
run pip install flask
env FLASK_APP=hello.py
env FLASK_ENV=development
env FLASK_DEBUG=0
run pwd
ENTRYPOINT  ["sh","/root/python/doflask.sh"]

