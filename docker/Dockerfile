# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Install git and other dependencies
RUN apt-get update && \
    apt-get install -y git && \
    rm -rf /var/lib/apt/lists/*

# Set the working directory in the container
WORKDIR /opt/nornir-network-backup

RUN mkdir -p /opt/nornir-network-backup/inventory/ && \
    mkdir -p /opt/nornir-network-backup/output/ && \
    mkdir -p /opt/nornir-network-backup/output/logs/ && \
    mkdir -p /opt/nornir-network-backup/output/backups/ && \
    mkdir -p /opt/nornir-network-backup/output/reports/ && \
    mkdir -p /opt/nornir-network-backup/output/facts/

# clone the networktocode/ntc-templates repository
RUN git clone https://github.com/networktocode/ntc-templates.git /opt/ntc-templates

# Install the nornir-network-backup package
RUN pip install nornir-network-backup==0.1.2a1 && \
    pip install nornir-salt==0.18.0 && \
    pip install requests==2.25.1

# Copy the current directory contents into the container at /opt/nornir-network-backup
COPY config-nnb.yaml .

COPY inventory/*.yaml ./inventory/

# Command to run when starting the container
ENTRYPOINT ["nnb"]

CMD ["backup"]