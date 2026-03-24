```bash
# Build and push the Docker image
docker build -t python-app .
docker tag python-app:latest fredy123456789/python-app:latest
docker push fredy123456789/python-app:latest

# Create a Ingress Controller
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.10.1/deploy/static/provider/cloud/deploy.yaml

# Apply the Kubernetes manifests
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl apply -f k8s/ingress.yaml
```