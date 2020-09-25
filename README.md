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
8. Generate kubeconfig for EKS `aws eks --region region-code update-kubeconfig --name healthhubplatform-dev`
9. Set kubectl context using this command `kubectl config set-context arn:aws:eks:us-east-1:277887097296:cluster/healthhubplatform-dev`

## Applying k8s manifests
1. Any k8s manifest can be applied using `kubectl apply -f <manifest_file>.yaml`

## Local Development k8s setup
1. Before interacting directly with EKS clusters, you can interact with local k8s clusters and apply the manifests before you apply the manifests to the EKS cluster
2. To run k8s locally, you can use minikube
3. Installation of minikube on macOS can be done via Homebrew: `brew install minikube`. More instructions are available for minikube installation at https://kubernetes.io/docs/tasks/tools/install-minikube/
4. Once the installation is complete, you can start a local k8s installation by running the command `minikube start`. More instructions are available for starting the local k8s installation at https://kubernetes.io/docs/setup/learning-environment/minikube/
5. You can specify a particular version of k8s as well while starting the k8s server `minikube start --kubernetes-version=1.18.0`
6. Once the k8s server - minikube starts up, it automatically sets the `kubectl` context and you should be able to interact with the local k8s installation using `kubectl` immediately. In case you need to switch the context from another k8s server to local minikube installation you can do that using `kubectl config use-context minikube`
7. More instructions on interacting with the cluster are at: https://kubernetes.io/docs/setup/learning-environment/minikube/#interacting-with-your-cluster

## Tutorial
1. Once the minikube installation is complete, you can run through this tutorial to interact with k8s cluster: https://kubernetes.io/docs/tutorials/

