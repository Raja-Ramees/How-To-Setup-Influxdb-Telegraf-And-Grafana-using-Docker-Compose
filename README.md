# 📊 How to Setup InfluxDB, Telegraf, and Grafana using Docker Compose

This repository provides an enterprise-ready Docker Compose setup for deploying a full monitoring stack using **InfluxDB**, **Telegraf**, and **Grafana**. It is designed for DevOps engineers, platform teams, and system administrators looking to gain visibility into infrastructure metrics with minimal setup time.

---

## 🔧 Components

- **InfluxDB**: Time-series database to store metrics.
- **Telegraf**: Agent to collect and send system and application metrics.
- **Grafana**: Visualization layer for creating dashboards from InfluxDB data.

---

## 🗂 Repository Structure

How-To-Setup-Influxdb-Telegraf-And-Grafana-using-Docker-Compose/
├── docker-compose.yml
├── telegraf/
│ └── telegraf.conf
├── grafana/
│ └── provisioning/
│ ├── datasources/
│ │ └── datasource.yml
│ └── dashboards/
│ └── <predefined-dashboard>.json
└── influxdb/
└── init/
└── init.iql


---

## ✅ Prerequisites

- Docker installed: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose installed: [Install Docker Compose](https://docs.docker.com/compose/install/)
- Ports `3000`, `8086`, and `8125` must be available.

---

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/Raja-Ramees/How-To-Setup-Influxdb-Telegraf-And-Grafana-using-Docker-Compose.git
cd How-To-Setup-Influxdb-Telegraf-And-Grafana-using-Docker-Compose

2. Start the Stack
docker-compose up -d
🌐 Access the Services
Component	URL	Default Credentials
Grafana	http://localhost:3000	admin / admin
InfluxDB	http://localhost:8086	No UI – REST API only

📉 Importing Dashboards in Grafana
Open Grafana → Dashboards → Import

Upload any .json file from grafana/provisioning/dashboards/

Choose InfluxDB as the data source

🛠 Customization
Telegraf Configuration
Modify telegraf/telegraf.conf to:

Add or remove input plugins (e.g., cpu, mem, disk, docker, etc.)

Set output to InfluxDB

Grafana Provisioning
grafana/provisioning/datasources/datasource.yml: Define InfluxDB as default data source

grafana/provisioning/dashboards/: Auto-load dashboards at startup
🧹 Stopping the Stack
docker-compose down

📬 Contact
Maintained by Raja Ramees
📧 Connect on GitHub

🏢 Ideal For
Monitoring Linux or containerized environments

Dashboards for real-time server metrics

Training and demo environments for observability tools
