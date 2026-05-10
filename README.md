# Multi-Tier MySQL Application Deployment on Kubernetes ☸️🐳

This project outlines a complete, production-ready implementation of a multi-tier MySQL database application deployment within a managed Kubernetes cluster environment. It showcases industrial DevOps practices for namespace isolation, Resource Quota allocation, Persistent Storage volumes, and Role-Based Access Control (RBAC) security structures.

---

## 🏗️ Core Architecture Overview
1. **Isolated Namespace (`prod-mysql-app`):** Restricts resources to prevent noisy-neighbor issues on the cluster.
2. **Resource Quotas:** Restricts cluster resource usage to under 2 CPUs and 2GiB of RAM.
3. **Persistent Volume (PV & PVC):** Ensures database transactions and data remain persistent even if Pods restart.
4. **Secrets Configuration:** Secures sensitive MySQL root authentication details using K8s secrets.
5. **RBAC Control:** Configured customized IAM role bindings (Developer Role for `Karen`).

---

## 📁 Project Artifacts & Files
- `namespace-quota.yaml`: Creates the virtual environment parameters.
- `storage.yaml`: Manages manual HostPath Persistent Storage allocation.
- `mysql-deployment.yaml`: Configures the actual multi-tier database pod and its secret credentials.
- `rbac-dashboard.yaml`: Manages Role Bindings for specific developer profiles.

---

## 🚀 Step-by-Step Deployment Guide

### 1. Apply Namespace Configuration & Quota Limit
```bash
kubectl apply -f namespace-quota.yaml
