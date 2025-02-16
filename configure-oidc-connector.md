# commands to configure IAM OIDC provider 

**export cluster_name=demo-cluster**

oidc_id=$(aws eks describe-cluster --name $cluster_name --query "cluster.identity.oidc.issuer" --output text | cut -d '/' -f 5) 



eksctl utils associate-iam-oidc-provider --cluster $cluster_name --approve

