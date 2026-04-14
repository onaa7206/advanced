1. Install Docker
✔ Download:
Docker Desktop (Windows/Mac)
✔ Verify:
docker --version
✔ Must be running:

Open Docker Desktop → keep it ON

☸️ 2. Install kubectl
Windows (Chocolatey):
choco install kubernetes-cli
Verify:
kubectl version --client
📦 3. Install Minikube
Windows:
choco install minikube
Verify:
minikube version
💻 4. Install Git Bash / WSL (Recommended)

Needed for touch commands.

Check:
touch test.txt

If error → install Git Bash or WSL.

⚙️ 5. System Requirement Check

Make sure:

Virtualization ON (BIOS)
At least:
2 CPUs
4GB RAM (minimum)
20GB free disk
🚀 1. START MINIKUBE
minikube start --driver=docker

Check cluster:

kubectl get nodes
🐍 2. CREATE PROJECT
mkdir ai-k8s-app
cd ai-k8s-app
🧾 3. CREATE FILES (using touch)
touch app.py requirements.txt Dockerfile deployment.yaml service.yaml
🐍 4. FLASK APP
app.py
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello Kubernetes AI App!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
requirements.txt
flask
🐳 5. DOCKER FILE
FROM python:3.10

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "app.py"]
🐳 6. CONNECT DOCKER TO MINIKUBE
eval $(minikube docker-env)

👉 Windows PowerShell:

& minikube -p minikube docker-env | Invoke-Expression
🏗️ 7. BUILD IMAGE
docker build -t ai-app:v1 .
📄 8. DEPLOYMENT YAML
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ai-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: ai-app
  template:
    metadata:
      labels:
        app: ai-app
    spec:
      containers:
      - name: ai-app
        image: ai-app:v1
        ports:
        - containerPort: 5000
📄 9. SERVICE YAML
apiVersion: v1
kind: Service
metadata:
  name: ai-app-service
spec:
  type: NodePort
  selector:
    app: ai-app
  ports:
    - port: 80
      targetPort: 5000
      nodePort: 30007
🚀 10. DEPLOY
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
🔍 11. CHECK STATUS
kubectl get pods
kubectl get services
kubectl get deployments
🌐 12. OPEN APP
minikube service ai-app-service
📈 13. SCALING
kubectl scale deployment ai-app --replicas=5

Check:

kubectl get pods
🧪 14. DEBUG
kubectl logs <pod-name>
kubectl describe pod <pod-name>
🧹 15. DELETE
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml

OR FULL RESET:

minikube delete
