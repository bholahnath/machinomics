# machinomics
This repo treats VMs as dynamic components of a living infrastructure system — combining automation, scaling strategies, and observability for resilient compute management. Ideal for DevOps engineers, SREs, and platform teams building with EC2, Terraform, and infrastructure-as-code.

# AWS EC2 VM Terraform Module

This repository contains Terraform configuration to deploy an AWS EC2 instance with attached data disks using a reusable module.

---

## Overview

The Terraform configuration provisions a Linux-based EC2 instance in a specified subnet and availability zone. It supports:

- Custom instance type
- SSH key pair for access
- Tagging resources for environment and ownership tracking
- Optional IAM instance profile (commented out in example)
- Attaching additional EBS data disks with configurable size, type, and tags

---

## Files

- **main.tf**  
  Defines the EC2 instance module with parameters for VM name, subnet, AZ, instance type, SSH key, tags, and data disks.

- **dev.tfvars**  
  Variable definitions for the development environment, overriding defaults such as VM name, subnet ID, availability zone, OS type, and SSH key name.

---

## Usage

1. **Clone the repository**

   ```bash
   git clone https://github.com/bholahnath/machinomics.git
   cd <repo-directory>
Initialize Terraform


terraform init
Apply the configuration


terraform apply -var-file="dev.tfvars"
Terraform will create:

An EC2 instance named my-ec2-instance

In subnet subnet-abc123 (or your specified subnet)

In availability zone eu-west-2a

Instance type t3.medium

With the specified SSH key pair

With a 100 GB gp3 EBS data disk attached
