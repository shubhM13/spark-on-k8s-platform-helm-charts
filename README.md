# Spark on K8s Platform Helm Charts

This repository contains git submodules for popular Kubernetes platform helm charts that are commonly used alongside Spark on Kubernetes deployments.

## Available Helm Charts

| Chart Name | Version | App Version | Description | Chart Location |
|------------|---------|-------------|-------------|----------------|
| **cluster-autoscaler** | 9.48.0 | 1.33.0 | Scales Kubernetes worker nodes within autoscaling groups | [Chart](https://github.com/kubernetes/autoscaler/tree/master/charts/cluster-autoscaler) |
| **aws-load-balancer-controller** | 1.13.3 | v2.13.3 | AWS Load Balancer Controller Helm chart for Kubernetes | [Chart](https://github.com/kubernetes-sigs/aws-load-balancer-controller/tree/main/helm/aws-load-balancer-controller) |
| **aws-ebs-csi-driver** | 2.46.0 | 1.46.0 | A Helm chart for AWS EBS CSI Driver | [Chart](https://github.com/kubernetes-sigs/aws-ebs-csi-driver/tree/master/charts/aws-ebs-csi-driver) |
| **aws-efs-csi-driver** | 3.2.1 | 2.1.10 | A Helm chart for AWS EFS CSI Driver | [Chart](https://github.com/kubernetes-sigs/aws-efs-csi-driver/tree/master/charts/aws-efs-csi-driver) |
| **aws-fsx-csi-driver** | 1.11.0 | 1.4.0 | A Helm chart for AWS FSx for Lustre CSI Driver | [Chart](https://github.com/kubernetes-sigs/aws-fsx-csi-driver/tree/master/charts/aws-fsx-csi-driver) |
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
├── aws-ebs-csi-driver/            # Git submodule: kubernetes-sigs/aws-ebs-csi-driver
│   └── charts/
│       └── aws-ebs-csi-driver/    # AWS EBS CSI Driver Helm Chart
├── aws-efs-csi-driver/            # Git submodule: kubernetes-sigs/aws-efs-csi-driver
│   └── charts/
│       └── aws-efs-csi-driver/    # AWS EFS CSI Driver Helm Chart
├── aws-fsx-csi-driver/            # Git submodule: kubernetes-sigs/aws-fsx-csi-driver
│   └── charts/
│       └── aws-fsx-csi-driver/    # AWS FSx CSI Driver Helm Chart
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

### AWS EBS CSI Driver
- **Repository**: [kubernetes-sigs/aws-ebs-csi-driver](https://github.com/kubernetes-sigs/aws-ebs-csi-driver)
- **Chart Path**: `aws-ebs-csi-driver/charts/aws-ebs-csi-driver/`
- **Purpose**: Container Storage Interface (CSI) driver for Amazon Elastic Block Store (EBS) volumes

### AWS EFS CSI Driver
- **Repository**: [kubernetes-sigs/aws-efs-csi-driver](https://github.com/kubernetes-sigs/aws-efs-csi-driver)
- **Chart Path**: `aws-efs-csi-driver/charts/aws-efs-csi-driver/`
- **Purpose**: Container Storage Interface (CSI) driver for Amazon Elastic File System (EFS) volumes

### AWS FSx CSI Driver
- **Repository**: [kubernetes-sigs/aws-fsx-csi-driver](https://github.com/kubernetes-sigs/aws-fsx-csi-driver)
- **Chart Path**: `aws-fsx-csi-driver/charts/aws-fsx-csi-driver/`
- **Purpose**: Container Storage Interface (CSI) driver for Amazon FSx for Lustre file systems

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

# Install AWS EBS CSI Driver
helm install aws-ebs-csi-driver ./aws-ebs-csi-driver/charts/aws-ebs-csi-driver/

# Install AWS EFS CSI Driver
helm install aws-efs-csi-driver ./aws-efs-csi-driver/charts/aws-efs-csi-driver/

# Install AWS FSx CSI Driver
helm install aws-fsx-csi-driver ./aws-fsx-csi-driver/charts/aws-fsx-csi-driver/

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
- [AWS EBS CSI Driver Documentation](https://github.com/kubernetes-sigs/aws-ebs-csi-driver)
- [AWS EFS CSI Driver Documentation](https://github.com/kubernetes-sigs/aws-efs-csi-driver)
- [AWS FSx CSI Driver Documentation](https://github.com/kubernetes-sigs/aws-fsx-csi-driver)
- [Metrics Server Documentation](https://github.com/kubernetes-sigs/metrics-server) 