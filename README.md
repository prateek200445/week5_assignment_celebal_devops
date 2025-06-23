# week5_assignment_celebal_devops
🧠** Scalable Kubernetes Internship Assignment – DevOps Project by Prateek
This repository contains solutions to a comprehensive DevOps assignment focused on Kubernetes cluster deployment, role-based access control (RBAC), and microservice architecture using tools like Minikube, Kubeadm, and Azure Kubernetes Service (AKS).
**
All tasks have been completed with hands-on configuration and step-by-step validation. Each task is documented as a PDF and uploaded to this repo for easy access and verification.

📂 PDF Solutions
Task No.	Title	PDF
Q1	Kubernetes Cluster using Minikube	celebal_que_s1.pdf
Q2	Kubernetes Cluster using Kubeadm	ques_2.pdf
Q3–Q5	AKS Cluster with RBAC, Microservice Deployment, and Service Exposure	ques_3_4_5.pdf

✅ **Tasks Completed**
🔹** Q1: Create a Kubernetes Cluster Using Minikube**
Installed kubectl and minikube using Chocolatey on Windows.

Started a local single-node cluster using Docker as the driver.

Deployed an nginx app and exposed it using a NodePort service.

Accessed the service via minikube service and dashboard.

Deployed an NGINX Helm chart from the Bitnami repo and accessed it at:
**http://127.0.0.1:52047/**

🔹 **Q2: Create a Kubernetes Cluster Using Kubeadm**
Provisioned a multi-node cluster with 1 master + 1 worker using Azure VMs.

Installed containerd, kubeadm, kubelet, kubectl, and initialized the cluster.

Enabled Calico CNI, fixed IP forwarding, and resolved node taint issues.

Deployed and accessed:

nginx app using NodePort

Custom microservice using Docker image: prateek2004/my-frontend

Accessed via:
*http://<your-node-ip>:<node-port>*

🔹** Q3: Deploy an AKS Cluster and Enable RBAC Dashboard**
Created an AKS cluster (new_kuber) using the Azure portal.

Configured access using:

commands: 
az aks get-credentials --name new_kuber
kubectl get nodes
Enabled Kubernetes Dashboard:

commands:
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
kubectl proxy
Accessed dashboard at:
**http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/**

**🔐 RBAC Roles Configured (Q3 Continued)
📄 Viewer Role
Read-only access limited to default namespace.

Used ServiceAccount, Role, and RoleBinding.

📄 Developer Role
Full CRUD access to the dev namespace.**

**Deployed a microservice (nginx) in dev, restricted access from Viewer role.**

🔹 Q4: Deploy a Microservice on AKS (Public Access)
Deployed app:

commands:
kubectl create deployment myfrontend --image=prateek2004/my-frontend:latest
kubectl expose deployment myfrontend --type=LoadBalancer --port=80 --target-port=80
Successfully accessed public-facing frontend at:
**🌐 http://172.212.79.224**

🔹** Q5: Expose Services Using All Service Types**
✅ **ClusterIP:** Default internal service.

✅ **NodePort:** Port-based access (for local dev or node IP).

✅** LoadBalancer:** Public access with AKS cloud integration.

Example commands used:

commands:
kubectl expose deployment myfrontend --type=ClusterIP --port=80 --target-port=80
kubectl expose deployment myfrontend --type=NodePort --port=80 --target-port=80
kubectl expose deployment myfrontend --type=LoadBalancer --port=80 --target-port=80
🧾 Skills Demonstrated
Kubernetes cluster provisioning (local and cloud)

YAML configuration, RBAC security

Kubernetes Dashboard management

Helm chart deployment

Azure AKS DevOps integration

Service exposure and public app hosting

Debugging Calico, taints, ports, and IP forwarding issues

**💡 Public App IP
✅ Deployed frontend app (portfolio):
🔗 http://172.212.79.224**

**🤝 Let's Connect**
If you're a recruiter, contributor, or mentor exploring Kubernetes/DevOps talent, this repository demonstrates real deployment-level command over Kubernetes, RBAC, cloud infrastructure, and observability.
