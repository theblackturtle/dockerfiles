FROM python:3.8.0-slim-buster
WORKDIR /root

RUN apt-get update && apt-get install -y wget && rm -rf /var/lib/apt/lists/*
RUN wget https://raw.githubusercontent.com/laconicwolf/Nmap-Scan-to-CSV/master/nmap_xml_parser.py

ENTRYPOINT ["python3"]
