# EKS-GAME-CLUSTER
This is a game project, that will be launched on the AWS EKS platform. for a quick review, we will lunch our kubernetes worker nodes using fargate, as AWS offers us a managed chaotic cluster environment, by not just managing our control plane since we are using EKS(a managed kubernetes service by AWS which is responsible for managing our control plane) and also managing the behaviour of our worker nodes by the introduction of the serverless service by AWS, the Fargate.
 # PREREQUSITE
 before you begin such project, i expect you should ensure you have the below tools that i will listing here and as well make sure you are using the latest tools. so i will advise you ensure you update your packages.
 - AWSCLI
 - Kubectl
 - EKSCLI

Firstly, you install the AWSCLI tool, then you configure your awscli tool using this command "AWS CONFIGURE", if you had successfully installed you tool, it will prompt a message requesting for your below details:
- AWS ACCESS KEY ID: ******************************************************************************************
- AWS SECRET ACCESS KEY: *********************
- DEFAULT REGION NAME: **********************
- DEFAULT OUTPUT NAME: **********************

do ensure you fill the above information correctly, as this gives AWSCLI tool access to communicate with the AWS API.
For security and good practise as a DevOps engineer, you are advised not to use the root account, always make sure you create a user account and grant the user the least privilledge access it needs for the project.

# STEPS
first of all, we create our EKS cluster using the EKSCTL command:

eksctl create cluster --name GAME-DEMO --region us-east-1 --fargate

after you must have confirmed that your cluster has been created, you can update the EKSCTL on your terminal to enable you interact with the kubernetes cluster from the terminal, by using this simple command:
  
  aws eks update-kubeconfig --name GAME-DEMO --region us-east-1

Now, we create a fargate profile and then deploy our application into our cluster
