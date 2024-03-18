FROM nvidia/dcgm-exporter:3.3.5-3.4.0-ubuntu22.04

RUN apt-get install -y ca-certificates \
    && apt-get update \
    && apt-get install wget -y \
    && wget -qO- https://get.docker.com | sh \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY nvidia-smi-ps /usr/local/bin
COPY nvidia-smi-exporter /usr/local/bin

RUN chmod +x /usr/local/bin/nvidia-smi-*

ENTRYPOINT [ "nvidia-smi-exporter" ]
