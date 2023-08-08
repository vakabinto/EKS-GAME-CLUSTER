##Install EKS
eksctl create cluster --name demo-cluster --region us-east-1 --fargate

##delete EKS cluster
eksctl delete cluster --name demo-cluster --region us-east-1