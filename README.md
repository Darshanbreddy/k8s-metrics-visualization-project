# k8s-metrics-visualization-project

🧩 Overview

This project explores monitoring and observability in Kubernetes using Prometheus and Grafana.
The work is based on the k8s-kind-voting-app
 repository, where I deployed the full voting app stack and integrated it with Prometheus metrics and Grafana dashboards.

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

