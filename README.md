### Deployed Tradein application on Kubernetes using minikube

##### Versions

minikube version: v1.32.0
kubectl Client Version: v1.29.4
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3

##### Installations

Dependencies

`sudo apt update
sudo apt install -y     apt-transport-https     ca-certificates     curl     gnupg     lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo   "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
`
Docker

`sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
`

Minikube

`curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version
sudo usermod -aG docker $USER && newgrp docker
minikube start
minikube status`

Kubectl

` sudo snap install kubectl --classic
 kubectl version --client
`

Kubectl commands for creating pods, deployment or services

`kubectl apply -f backend.yaml`
`kubectl apply -f fronend.yaml`

Frontend Port Forwarding - kubectl port-forward svc/tradein-frontend-service 31000:80 --address 0.0.0.0 &

Backend Port Forwarding - kubectl port-forward svc/tradein-backend-service 8000:8000 --address 0.0.0.0 &
