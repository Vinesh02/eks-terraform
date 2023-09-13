# eks-terraform
Create eks cluster using terraform
After terraform apply command eks cluster is ready to access.
Need to download Kubectl for accessing Eks Cluster for download kubectl follw below commands.

1. configure aws cli 
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    unzip awscliv2.zip
    sudo ./aws/install
    aws configure 


2. Install IAM-authenticator 
    curl -o aws-iam-authenticator https://s3.us-west-2.amazonaws.com/amazon-eks/1.21.2/2021-07-05/bin/linux/amd64/aws-iam-authenticator
    chmod +x ./aws-iam-authenticator
    mkdir -p $HOME/bin && cp ./aws-iam-authenticator $HOME/bin/aws-iam-authenticator && export PATH=$PATH:$HOME/bin
    echo 'export PATH=$PATH:$HOME/bin' >> ~/.bashrc
    aws-iam-authenticator help

3. Install kubectl 
    curl -o kubectl https://s3.us-west-2.amazonaws.com/amazon-eks/1.22.6/2022-03-09/bin/linux/amd64/kubectl
    chmod +x ./kubectl
    mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin
    echo 'export PATH=$PATH:$HOME/bin' >> ~/.bashrc
    kubectl version --short --client

4. kubectl update kube-config.
    $ aws sts get-caller-identity
    $ aws --version
    $ aws eks update-kubeconfig --region ap-south-1 --name dice-eks

    it will create $/home/user/.kube/config file.

5. After completion all this proccess run this command for checking we acceesing eks cluster or not.
   $ kubectl get ns
