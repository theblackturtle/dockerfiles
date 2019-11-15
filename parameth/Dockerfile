FROM python:3.8.0-alpine3.10

RUN apk add --no-cache git g++
RUN git clone https://github.com/maK-/parameth.git
WORKDIR /parameth

RUN pip3 install -r requirements.txt

CMD ["python3","parameth.py"]