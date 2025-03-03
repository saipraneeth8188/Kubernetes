**Kubernetes & OpenShift -** 

**Why Kubernetes?**

Kubernetes (K8s) is widely used by companies like Google, Netflix, Amazon (EKS), Spotify, and Tinder.

OpenShift is RedHat’s enterprise Kubernetes solution.

Types of Kubernetes Deployments:

**Open-Source:** Rancher, Docker K8s Service
**Cloud-Managed:** GKE (Google), EKS (AWS), AKS (Azure)
**Enterprise:** OpenShift, Mirantis, Tanzu K8s Grid

**Containers & K8s Overview**

1. Why Use Containers?

Developers need OS to run applications.

Containers provide lightweight OS instances using Docker, Podman, CRI-O.

Companies like Google launch millions of containers weekly.

2. Challenges of Container Management:

Containers fail, and managing 1000s of them manually is impossible.

K8s automates monitoring and container recovery.

3. K8s vs. Docker

Docker → Launches containers but doesn’t restart them if they fail.

K8s → Monitors containers and restarts failed ones automatically.

**Kubernetes Key Concepts**

K8s is a management layer over Docker.

IT teams interact with K8s (not Docker) using kubectl.

Pod → The smallest deployable unit (K8s wraps a container inside a Pod).

K8s Services:

Pod → Runs the container.

Deployment → Ensures the correct number of Pods.

Service → Acts as a Load Balancer (LB) for Pods.

**Installing Kubernetes**

Installation Methods:

Minikube (Local)

Kubeadm (For setting up clusters)

Kind (K8s in Docker)

Minikube sets up a VM with Kubernetes pre-installed using VirtualBox.

**Kubernetes Architecture**

Components:

Kube-Scheduler → Decides where to run Pods.

etcd → Stores K8s data (like a database).

Command to check cluster info:

```kubectl cluster-info```

Using Kubernetes

Basic Commands

Check running pods:

```kubectl get pods```

Create a deployment:

```kubectl create deployment myapp --image=nginx```

Describe a pod:

```kubectl describe pod <pod-name>```

Delete a pod:

```kubectl delete pod <pod-name>```

Scale pods:

```kubectl scale deployment myapp --replicas=4```

Expose a deployment (create a LoadBalancer):

```kubectl expose deployment myapp --type=NodePort```

Get service details:

```kubectl get svc```

Access application using NodePort:

```http://<minikube-ip>:<node-port>```

(Get Minikube IP using minikube ip command.)

**Key Kubernetes Features**

**Self-Healing** → If a Pod fails, K8s recreates it automatically.

**Load Balancing** → K8s distributes traffic among Pods.

Scaling →

**Horizontal Scaling:** kubectl scale to increase Pod count.

**Vertical Scaling:** Allocating more CPU/memory.

High Availability → Ensures uptime by replacing failed Pods.

**Load Balancing in Kubernetes**

Load balancing ensures even distribution of traffic across multiple pods.

Types of Load Balancing in K8s:

ClusterIP (Default) → Internal communication within the cluster.

NodePort → Exposes the service on a static port across all cluster nodes.

LoadBalancer → Provisions an external load balancer (Cloud Provider required).

Ingress → Advanced routing using a single external IP with multiple services.

Example Commands for Load Balancing:

Creating a LoadBalancer service:

```kubectl expose deployment myapp --type=LoadBalancer --port=80 --target-port=8080```

Get LoadBalancer IP after deployment:

```kubectl get svc myapp```

**API & Code in Kubernetes**

Kubernetes has an API server that handles all requests.

Ways to interact with K8s:

1. Web UI (Dashboard)
2. CLI (kubectl)
3. API Requests

Most real-world implementations rely on API & Automation instead of manual commands.

List all API resources in Kubernetes:

```kubectl api-resources```

**Final Thoughts**

K8s automates container deployment, monitoring, and scaling.

K8s ≠ Docker → Docker launches containers; K8s manages them.

Learning Kubernetes = Better job opportunities in DevOps.