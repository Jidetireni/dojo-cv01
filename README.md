# Setting Up a 3-Tier Application with Monitoring on the Cloud

This repository contains the complete setup for deploying a 3-tier application (React frontend, FastAPI backend, PostgreSQL database) with a monitoring stack using Prometheus, Grafana, Loki, Promtail, and cAdvisor. The project was developed as part of the DevOps Dojo CV Challenge, showcasing modern DevOps practices.

---

## Key Features
- **Frontend**: React app served via Nginx.
- **Backend**: FastAPI app with PostgreSQL integration.
- **Database**: PostgreSQL with environment-configured setup.
- **Monitoring**: 
  - Logs: Loki, Promtail, and Grafana.
  - Metrics: Prometheus, cAdvisor, and Grafana.
- **Reverse Proxy & SSL**: Managed with Nginx Proxy Manager.
- **Cloud Deployment**: Configured for cloud platforms with domain setup (DuckDNS).

---

## Getting Started

### Local Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/The-DevOps-Dojo/cv-challenge01.git
   ```
2. Refer to the detailed README files in the `frontend` and `backend` directories for local setup instructions.

### Dockerized Setup
1. **Build Frontend and Backend Images**:
   - Frontend:
     ```bash
     docker build -t frontend ./frontend
     ```
   - Backend:
     ```bash
     docker build -t backend ./backend
     ```
2. **Database Initialization**:
   Ensure the `.env` file is properly configured with PostgreSQL details.

3. **Run the Stack**:
   ```bash
   docker network create network
   docker-compose up
   ```

### Monitoring Stack
1. **Add Monitoring Services**:
   - Configure `compose.monitoring.yml` for Grafana, Loki, Promtail, Prometheus, and cAdvisor.
2. **Start Monitoring Stack**:
   ```bash
   docker-compose -f compose.monitoring.yml up
   ```

---

## Domain and Cloud Deployment
- **Cloud**: Deploy using a cloud provider (e.g., GCP).
- **Domain**: Use DuckDNS or other DNS providers for subdomain configuration.
- **Reverse Proxy**: Configure Nginx Proxy Manager for SSL and custom domains.

---

## Testing and Usage
- **Frontend**: Accessible at `http://localhost:5173` or via the configured domain.
- **Grafana UI**: Access at `http://localhost:3000` (default admin: `admin`/`admin`).
- **Prometheus**: Metrics at `http://localhost:9090`.
- **Logs**: Managed via Loki, visualized in Grafana.

---

## Contribution
Feel free to open issues or submit PRs to improve the project. Feedback is always welcome!

--- 

Happy deploying! 🚀
