FROM python:3.8.0-alpine3.10

RUN apk add --no-cache git bash && rm -rf /var/lib/apt/lists/*
RUN git clone https://github.com/ProjectAnte/dnsgen.git\
    && cd dnsgen\
    && python3 setup.py install

# ENTRYPOINT ["dnsgen"]
