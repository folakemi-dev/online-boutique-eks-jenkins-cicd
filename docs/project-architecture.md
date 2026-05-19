# Project Architecture

This project uses Jenkins to automate the deployment of Google Online Boutique to Amazon EKS.

## Architecture Flow

Developer pushes project files to GitHub
            |
            v
Jenkins pulls the repository from GitHub
            |
            v
Jenkins connects to Amazon EKS using AWS CLI and kubeconfig
            |
            v
Jenkins applies Kubernetes manifests
            |
            v
Amazon EKS schedules microservices pods on worker nodes
            |
            v
Kubernetes Service exposes the frontend through AWS Load Balancer
            |
            v
Online Boutique becomes accessible in the browser