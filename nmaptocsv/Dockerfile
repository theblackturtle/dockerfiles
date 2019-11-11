FROM python:3.8.0-alpine3.10

WORKDIR /root

RUN apk add --no-cache wget && rm -rf /var/lib/apt/lists/*
RUN wget https://raw.githubusercontent.com/laconicwolf/Nmap-Scan-to-CSV/master/nmap_xml_parser.py -O /root/nmap_xml_parser.py

CMD ["python3"]
