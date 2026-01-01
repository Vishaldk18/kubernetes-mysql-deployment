# Kubernetes Application Deployment with MySQL

## 📌 Overview

This project demonstrates a complete **Kubernetes-based application deployment** using core Kubernetes objects such as **Deployment, Service, PersistentVolumeClaim, and Secrets**. The setup is designed to showcase **real-world container orchestration practices**, including secure credential management and persistent storage.

The project is ideal for **DevOps / Cloud Engineer learning, interviews, and portfolio showcase**.

---

## 🧱 Architecture

**Components Used:**

* Kubernetes Deployment
* Kubernetes Service (NodePort)
* PersistentVolumeClaim (PVC)
* Kubernetes Secrets
* MySQL Database

**High-level Flow:**

1. Application Pod starts using Deployment
2. MySQL credentials are securely injected via Secrets
3. Persistent storage is provided using PVC
4. Service exposes the application to external traffic

---

## 📂 Project Structure

```bash
.
├── deployment.yaml              # Application & MySQL deployment
├── service.yaml                 # Service to expose application
├── persistentVolumeClaim.yaml   # Persistent storage for MySQL
├── secrets.yaml                 # Kubernetes secrets (DB credentials)
└── README.md                    # Project documentation
```

---

## 🔐 Secrets Management

Kubernetes **Secrets** are used to securely store sensitive information such as:

* MySQL root password
* Database credentials

Secrets are injected into the pods as **environment variables**, avoiding hardcoding sensitive values in manifests.

---

## 💾 Persistent Storage

* Uses **PersistentVolumeClaim (PVC)**
* Ensures MySQL data persists even if pods restart or are rescheduled
* Follows best practices for stateful workloads in Kubernetes

---

## 🚀 Deployment Steps

### 1️⃣ Start Kubernetes Cluster

```bash
minikube start
```

### 2️⃣ Apply Secrets

```bash
kubectl apply -f secrets.yaml
```

### 3️⃣ Create Persistent Volume Claim

```bash
kubectl apply -f persistentVolumeClaim.yaml
```

### 4️⃣ Deploy Application

```bash
kubectl apply -f deployment.yaml
```

### 5️⃣ Expose Service

```bash
kubectl apply -f service.yaml
```

---

## 🔎 Verify Resources

```bash
kubectl get pods
kubectl get svc
kubectl get pvc
```

---

## 🌐 Access the Application

For Minikube:

```bash
minikube service <service-name>
```

Or using NodePort:

```bash
http://<NODE-IP>:<NODE-PORT>
```

---

## 🛡️ Security Best Practices Followed

* No plaintext credentials in manifests
* Secrets managed using Kubernetes Secrets
* Persistent data separated from application lifecycle

---

## 🧪 Learning Outcomes

* Hands-on Kubernetes resource management
* Secure secret handling
* Stateful application deployment
* Real-world troubleshooting exposure

---

## 🧹 Cleanup

```bash
kubectl delete -f .
minikube stop
```

---

## 📌 Future Enhancements

* Add Ingress with NGINX
* Helm chart packaging
* CI/CD with GitHub Actions
* Monitoring with Prometheus & Grafana

---

## 👨‍💻 Author

**Vishal Khairnar**
Cloud & DevOps Engineer
GitHub: [https://github.com/your-username](https://github.com/vishaldk18)

---

⭐ If you find this project helpful, consider giving it a star!
