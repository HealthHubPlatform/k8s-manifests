# k8s-manifests
Repo which stores the k8s manifests that are being deployed to the EKS cluster

## kubectl Installation
1. Install kubectl on your mac using Homebrew `brew install kubectl`
2. Verify it is installed by running the command `kubectl version --client`
3. Installation for other platforms is listed at https://kubernetes.io/docs/tasks/tools/install-kubectl/

## Interacting with EKS cluster
1. Detailed instructions are at https://docs.aws.amazon.com/eks/latest/userguide/managing-auth.html
2. First install `aws-iam-authenticator` using Homebrew `brew install aws-iam-authenticator`
3. Test that the binary works `aws-iam-authenticator help`
4. Make sure AWS access key and secret key are set by following the below commands
5. Export them as Environment variables. To have them exported you need to run the below commands on the terminal
6. `export AWS_ACCESS_KEY_ID="<your access key id>"` 
7. `export AWS_SECRET_ACCESS_KEY="<your secret access key>"` 
8. Generate kubeconfig for EKS `aws eks --region region-code update-kubeconfig --name cluster_name`
