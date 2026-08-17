REGION_CODE=us-east-1 CLUSTER_NAME=expense ACC_ID=315069654700

Permissions
OIDC provider
eksctl utils associate-iam-oidc-provider \
    --region $REGION_CODE \
    --cluster $CLUSTER_NAME \
    --approve

aws eks update-kubeconfig --region us-east-1 --name expense

Install kubectl

curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.36.2/2026-07-05/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv kubectl /usr/local/bin/kubectl


commands to get the user deatils

kubectl get configmap aws-auth -n kube-system -o yaml

aws sts get-caller-identity