# Spark on K8s Platform Helm Charts

This repository contains git submodules for popular Kubernetes platform helm charts that are commonly used alongside Spark on Kubernetes deployments.

## Available Helm Charts

| Chart Name | Version | App Version | Description | Chart Location |
|------------|---------|-------------|-------------|----------------|
| **cluster-autoscaler** | 9.48.0 | 1.33.0 | Scales Kubernetes worker nodes within autoscaling groups | [Chart](https://github.com/kubernetes/autoscaler/tree/master/charts/cluster-autoscaler) |
| **aws-load-balancer-controller** | 1.13.3 | v2.13.3 | AWS Load Balancer Controller Helm chart for Kubernetes | [Chart](https://github.com/kubernetes-sigs/aws-load-balancer-controller/tree/main/helm/aws-load-balancer-controller) |
| **metrics-server** | 3.13.0 | 0.8.0 | Scalable, efficient source of container resource metrics for Kubernetes built-in autoscaling pipelines | [Chart](https://github.com/kubernetes-sigs/metrics-server/tree/master/charts/metrics-server) |

## Repository Structure

```
spark-on-k8s-platform-helm-charts/
├── autoscaler/                    # Git submodule: kubernetes/autoscaler
│   └── charts/
│       └── cluster-autoscaler/    # Cluster Autoscaler Helm Chart
├── aws-load-balancer-controller/  # Git submodule: kubernetes-sigs/aws-load-balancer-controller
│   └── helm/
│       └── aws-load-balancer-controller/  # AWS Load Balancer Controller Helm Chart
├── metrics-server/                # Git submodule: kubernetes-sigs/metrics-server
│   └── charts/
│       └── metrics-server/        # Metrics Server Helm Chart
└── README.md                      # This file
```

## Submodule Details

### Cluster Autoscaler
- **Repository**: [kubernetes/autoscaler](https://github.com/kubernetes/autoscaler)
- **Chart Path**: `autoscaler/charts/cluster-autoscaler/`
- **Purpose**: Automatically adjusts the size of Kubernetes clusters when nodes are needed or can be removed

### AWS Load Balancer Controller
- **Repository**: [kubernetes-sigs/aws-load-balancer-controller](https://github.com/kubernetes-sigs/aws-load-balancer-controller)
- **Chart Path**: `aws-load-balancer-controller/helm/aws-load-balancer-controller/`
- **Purpose**: Manages AWS Elastic Load Balancers for Kubernetes clusters running on AWS

### Metrics Server
- **Repository**: [kubernetes-sigs/metrics-server](https://github.com/kubernetes-sigs/metrics-server)
- **Chart Path**: `metrics-server/charts/metrics-server/`
- **Purpose**: Provides container resource metrics for Kubernetes built-in autoscaling pipelines

## Usage

### Initialize Submodules

```bash
git submodule update --init --recursive
```

### Installing Charts

You can install these charts directly from their local paths:

```bash
# Install Cluster Autoscaler
helm install cluster-autoscaler ./autoscaler/charts/cluster-autoscaler/

# Install AWS Load Balancer Controller
helm install aws-load-balancer-controller ./aws-load-balancer-controller/helm/aws-load-balancer-controller/

# Install Metrics Server
helm install metrics-server ./metrics-server/charts/metrics-server/
```

### Updating Submodules

To update all submodules to their latest versions:

```bash
git submodule update --remote
```

## Links

- [Kubernetes Autoscaler Documentation](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler)
- [AWS Load Balancer Controller Documentation](https://kubernetes-sigs.github.io/aws-load-balancer-controller/)
- [Metrics Server Documentation](https://github.com/kubernetes-sigs/metrics-server) 