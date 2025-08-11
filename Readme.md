----------------Instruction For minikube installation----------------
Kubernetes Deployment with Minikube
This project demonstrates deploying an Nginx application on a local Kubernetes cluster using Minikube, exposing it via a NodePort service, scaling the deployment, setting up horizontal pod autoscaling, and viewing logs.
📌 Prerequisites
- kubectl installed → https://kubernetes.io/docs/tasks/tools/
- Minikube installed → https://minikube.sigs.k8s.io/docs/start/
- Docker installed (Minikube uses it as a backend)
⚙️ Install & Start Minikube
Start Minikube with default driver:
minikube start
Verify cluster status:
kubectl get nodes

---------------------deployment & service------------------------

Now checkout to my repo link: [https://github.com/NipurJain4/minikube-kubernetes.git]

Apply both deployement.yaml and service.yaml 
Apply Deployment:
kubectl apply -f deployment.yaml
kubectl get pods

Apply it:
kubectl apply -f service.yaml
kubectl get svc

3. Access the Application
minikube service my-service
Or:
minikube service my-service --url
curl $(minikube service my-service --url)
![Description of image](Screenshorts/Screenshot(56).png)

📈 Scaling the Deployment
kubectl scale deployment MyApp --replicas=5
kubectl get pods
![Description of image](Screenshorts/Screenshot(57).png)
![Description of image](Screenshorts/Screenshot(58).png)


--------------------------logs---------------------------------

📜 Viewing Logs
kubectl logs <pod-name>
kubectl logs -f <pod-name>
kubectl describe pod <pod-name>
🧹 Clean Up
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml
minikube stop
minikube delete
📂 Repository Structure
.
├── deployment.yaml   # Nginx deployment
├── service.yaml      # NodePort service
└── README.md         # Instructions
✅ Summary
This setup:
- Installs Minikube locally
- Deploys an Nginx application
- Exposes it via NodePort service
- Scales manually
- Checks logs for debugging


