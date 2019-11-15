FROM python:3.8.0-alpine3.10

RUN apk add --no-cache git
RUN git clone https://github.com/maK-/parameth.git
WORKDIR /parameth

CMD ["python3","parameth.py"]