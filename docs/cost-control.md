
## Cost Control and Cleanup

AWS resources can generate cost, especially Amazon EKS clusters, EC2 instances, Load Balancers, EBS volumes, and public IPv4 addresses.

After completing the deployment and capturing evidence, I deleted the resources to avoid unnecessary charges.

### Delete the Application

```bash
kubectl delete -f app/release/kubernetes-manifests.yaml
```

### Delete the EKS Cluster

```bash
eksctl delete cluster --name online-boutique-cluster --region us-east-2
```

### Additional AWS Resources Checked

After deleting the cluster, I checked the AWS Console for:

- EKS clusters
- EC2 instances
- Load Balancers
- EBS volumes
- Elastic IPs
- CloudFormation stacks
- Security groups