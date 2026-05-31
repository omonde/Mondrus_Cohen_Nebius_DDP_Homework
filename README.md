# Nebius Distributed Training MLOps Homework

## Overview
Distributed training pipeline on Nebius Cloud using:

- Managed Kubernetes cluster
- GPU nodes (H100)
- SkyPilot
- Docker container
- PyTorch Distributed Data Parallel (DDP)

## Files

- `Dockerfile` — container definition
- `train.py` — PyTorch distributed training script
- `train_job.yaml` — SkyPilot job configuration
- `mk8s-ng-config.json` — Kubernetes node group configuration
- `training_log.txt` — training logs with NCCL initialization and results

## Infrastructure

Cluster: `olga-mondrus-hw1-k8s`

Node Group: `olga-m-hw1-ng`

Configuration:
- Kubernetes 1.33
- 2 nodes
- H100 GPU nodes
- Ubuntu 24.04
- 1 GPU / 16 vCPU / 200 GB preset

## Docker Image

```text
cr.eu-north1.nebius.cloud/e00efwc202jemnfyk7/nebius-trainer:v1
```

## Training Results

NCCL initialization:

```text
[0] NCCL INFO Bootstrap : Using eth0:10.26.x.x<0>
[0] NCCL INFO NET/Plugin : No plugin found, using internal net plugin
[0] NCCL INFO Connected all rings, use ring PXN 0 GDR 0
```

Final metrics:

```text
train_loss: 20.54
eval_loss: 14.68
Job finished (status: SUCCEEDED)
```