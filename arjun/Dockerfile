FROM python:3.8.0-alpine3.10

RUN apk add --no-cache git
RUN git clone https://github.com/s0md3v/Arjun.git
WORKDIR /Arjun

RUN pip3 install requests
CMD ["python3","arjun.py"]