```
version: '3.8'

services:
  snmp_exporter:
    image: prom/snmp-exporter:latest
    container_name: snmp_exporter
    ports:
      - "9116:9116"
    command:
      - "--config.file=/etc/snmp_exporter/snmp.yml"
    volumes:
      - snmp_config:/etc/snmp_exporter
    networks:
      - snmp_network
    restart: always

networks:
  snmp_network:
    driver: bridge

volumes:
  snmp_config:
```
