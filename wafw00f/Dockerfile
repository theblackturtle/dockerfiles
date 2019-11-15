FROM python:3.8.0-alpine3.10

RUN apk add --no-cache git
RUN git clone https://github.com/EnableSecurity/wafw00f.git
WORKDIR /wafw00f

RUN python3 setup.py install

CMD ["wafw00f"]