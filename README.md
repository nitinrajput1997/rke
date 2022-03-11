# rke

### 1. Install Docker
```bash
curl https://releases.rancher.com/install-docker/20.10.sh | sh
sudo usermod -aG docker $USER
reboot
```

### 2. Install RKE
```bash
sudo wget https://github.com/rancher/rke/releases/download/v1.3.0/rke_linux-amd64 \
-O /usr/local/bin/rke

sudo chmod +x /usr/local/bin/rke
```

### 3. Configuration
```bash
rke config
```

### 4. Move rke config to diff folder
```bash
mkdir rke 
mv /home/name/.ssh/cluster.yml /home/name/rke
```

### 5. Install kubectl
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin
```

### 6. Install kubectx and kubens
```bash
sudo git clone https://github.com/ahmetb/kubectx
cd kubectx
ls
sudo mv kubectx kubens /usr/local/bin
```

### 7. SSH
```bash
ssh-keygen
ssh-copy-id ubuntu@ip
```   

### 8. Running cluster
```bash
rke up
```

### 9. Move kubeconfig
```bash
mv kubeconfig.yml file to .kube with rename as config
```

### 10. Set the kubeconfig environment variable
```bash    
export KUBECONFIG=$HOME/.kube/config
```

### 11. Check nodes and pods to verify
```bash
kubectl get no
kubectl get po -A
```
