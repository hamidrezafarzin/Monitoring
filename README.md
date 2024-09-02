### Table of Contents
1. [Monitoring Setup](#monitoring-setup)
2. [Features](#features)
3. [Project Structure](#project-structure)
4. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Setup](#setup)
5. [Customization](#customization)
6. [License](#license)

# Monitoring Setup

This repository contains a comprehensive monitoring setup using Prometheus and Grafana. It includes production-ready Docker Compose configurations, environment settings, and customizable dashboard templates.

## Features

- **Prometheus Monitoring**: Collect metrics from various services.
- **Grafana Dashboards**: Visualize metrics with pre-configured templates.
- **Docker Compose**: Easily deploy Prometheus and Grafana in a production environment.
- **Environment Configurations**: Sample environment files for quick setup.

## Project Structure

```plaintext
├── docker-compose-prod.yml     # Docker Compose file for production
├── pass_generator.py           # Script for generating passwords
├── config
│   ├── grafana
│   │   └── grafana.ini         # Grafana configuration
│   └── prometheus
│       ├── prometheus.yml      # Prometheus main configuration
│       ├── prometheus-with-db.yml # Prometheus with database configuration
│       └── web.yml             # Prometheus web configuration
├── dashboard
│   └── templates
│       ├── node-exporter-template
│       │   └── dashboard_config.json  # Node exporter dashboard template
│       └── postgres-exporter-template
│           └── 9628_rev7.json # Postgres exporter dashboard template
└── envs
    └── prod
        ├── grafana
        │   └── .env.sample    # Sample environment file for Grafana
        └── prometheus
            └── .env.sample    # Sample environment file for Prometheus
```

## Getting Started

### Prerequisites

- Docker and Docker Compose installed on your machine.

### Setup

1. Clone this repository:
    ```bash
    git clone https://github.com/your-username/monitoring-setup.git
    cd monitoring-setup
    ```

2. Customize the environment variables:
    - Copy the sample environment files from `envs/prod/` to create your own `.env` files.
    - Update the `.env` files with your own configurations.

3. Start the monitoring stack:
    ```bash
    docker-compose -f docker-compose-prod.yml up -d
    ```

4. Access Grafana dashboards:
    - Open your browser and navigate to `http://localhost:3000`.
    - Login with the credentials specified in your `.env` file.

## Customization

- **Grafana**: Modify `grafana.ini` under `config/grafana/` to customize Grafana settings.
- **Prometheus**: Update `prometheus.yml` under `config/prometheus/` for custom Prometheus configurations.
- **Dashboards**: Edit the dashboard templates under `dashboard/templates/` to create custom visualizations.

## License

This project is licensed under the MIT License.
