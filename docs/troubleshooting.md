
## Troubleshooting

During this project, the following troubleshooting commands are useful:

```bash
kubectl get pods
kubectl describe pod POD_NAME
kubectl logs POD_NAME
kubectl get svc
kubectl describe svc frontend-external
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl get nodes
kubectl describe node NODE_NAME
```

### Common Issues and Fixes

| Issue | Possible Cause | Solution |
|---|---|---|
| `kubectl command not found` | kubectl is not installed on Jenkins server | Install kubectl and verify with `kubectl version --client` |
| `Unable to locate credentials` | AWS CLI is not configured for the Jenkins user | Configure AWS CLI for the Jenkins user or attach an IAM role |
| `You must be logged in to the server` | kubeconfig is not configured correctly | Run `aws eks update-kubeconfig` |
| Pods stuck in `Pending` | Worker nodes may not have enough resources | Check node status and describe the pending pods |
| LoadBalancer stuck in `Pending` | AWS Load Balancer is still provisioning | Wait and check service events |
| Jenkins pipeline fails at EKS connection | Jenkins user cannot access the cluster | Confirm AWS credentials and kubeconfig for the Jenkins user |