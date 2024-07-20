# Nornir Network Backup Docker Project

This project provides a Dockerized environment for running the `nornir-network-backup` tool, which is designed to facilitate network configuration backup tasks, based on Nornir.

## Overview

The `nornir-network-backup` Docker container is built to run network backup tasks using the specified version of the `nornir-network-backup` Python package. This setup allows for easy deployment and execution of network backup operations across various environments without the need for complex installation processes.

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Installation

1. Clone this repository to your local machine.
2. Navigate to the project directory.

### Building the Docker Image

Run the following command to build the Docker image:

```bash
docker-compose build
```


### Running the Container

To start the container and execute the `backup --all` command:

```bash
docker-compose up
```

### Custom Commands

You can override the default command (`backup --all`) by modifying the `command` line in the `docker-compose.yaml` file.

### Configuration

The `docker-compose.yaml` file contains several commented-out volume mappings. These can be uncommented and adjusted according to your needs to mount local directories into the container:

- Inventory files
- Configuration files
- Output directories for logs, backups, and reports
- NTC templates directory

### Networks

The service is configured to use a custom bridge network named `nornir_network_backup`. This can be adjusted in the `docker-compose.yaml` file under the `networks` section.

### Environment Variables

The environment section in the docker-compose.yaml file is currently empty but can be used to pass environment variables to the container.

### Contributing

Contributions to this project are welcome. Please ensure to follow the standard Git workflow and submit your pull requests for review.

### License

This project is licensed under the MIT License - see the LICENSE file for details.
