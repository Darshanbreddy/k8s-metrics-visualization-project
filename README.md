# k8s-metrics-visualization-project

🧩 Overview

This project explores monitoring and observability in Kubernetes using Prometheus and Grafana.
The work is based on the k8s-kind-voting-app
 repository(https://github.com/LondheShubham153/k8s-kind-voting-app.git), where I deployed the full voting app stack and integrated it with Prometheus metrics and Grafana dashboards.

⚙️ Cluster Setup

Created a Kind cluster with:

1 Control Plane node

2 Worker nodes

Deployed the following workloads:

db-deployment.yaml & db-service.yaml

redis-deployment.yaml & redis-service.yaml

vote-deployment.yaml & vote-service.yaml

result-deployment.yaml & result-service.yaml

worker-deployment.yaml

📊 Monitoring Stack

Installed Helm and used it to deploy Prometheus and Grafana.

Collected metrics for CPU, memory, and network usage using the following PromQL queries:

# CPU Usage (%)
sum(rate(container_cpu_usage_seconds_total{namespace="default"}[1m])) / sum(machine_cpu_cores) * 100

# Memory Usage by Pod
sum(container_memory_usage_bytes{namespace="default"}) by (pod)

# Network I/O
sum(rate(container_network_receive_bytes_total{namespace="default"}[5m])) by (pod)
sum(rate(container_network_transmit_bytes_total{namespace="default"}[5m])) by (pod)
📈 Grafana Dashboards

Created custom visualizations using both standard panels and Grafana templates.

Visualized container-level CPU, memory, and network metrics for all deployed pods.

⚠️ Note

Originally, screenshots of the dashboards and metrics were taken, but the EC2 instance had to be deleted due to an AWS error before the files could be uploaded. The repository therefore contains configurations and documentation, but not the visual outputs.

🧠 Learning Focus

Setting up Kubernetes clusters locally using Kind

Deploying multi-service applications

Installing Prometheus and Grafana via Helm

Writing and testing PromQL queries

Building Grafana dashboards from scratch

