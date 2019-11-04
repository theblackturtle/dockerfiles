FROM python:3.5.8-slim-buster

RUN wget https://raw.githubusercontent.com/laconicwolf/Nmap-Scan-to-CSV/master/nmap_xml_parser.py
RUN chmod +x nmap_xml_parser.py

ENTRYPOINT ["nmap_xml_parser.py"]
