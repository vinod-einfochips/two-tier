# How to setup two-tier application deployment on kubernetes cluster
## First setup kubernetes kubeadm cluster

## SetUp
- First clone the code to your machine
```bash
git clone https://github.com/vinod-einfochips/two-tier.git
```
- Move to k8s directory
```bash
cd two-tier-flask-app/k8s
```
- Now, execute below commands one by one
```bash
kubectl apply -f two-tier-app-deployment.yml
```
```bash
kubectl apply -f two-tier-app-svc.yml
```
```bash
kubectl apply -f mysql-deployment.yml
```
```bash
kubectl apply -f mysql-svc.yml
```
```bash
kubectl apply -f mysql-pv.yml
```
```bash
kubectl apply -f mysql-pvc.yml
```

## To access a MySQL instance running in a Kubernetes cluster

```bash
kubectl get pods -n default
kubectl exec -it mysql-004433 -n default -- /bin/bash
mysql -u root -p
```
```bash
show databases;
use mydb;
```
```bash
 CREATE TABLE messages (
    ->     id INT AUTO_INCREMENT PRIMARY KEY,
    ->     message TEXT
    -> );
```
