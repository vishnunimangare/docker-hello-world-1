Docker Hello World - Nginx Static Site
A simple containerized static website using Nginx that demonstrates basic Docker concepts.

🚀 Features
Lightweight Nginx Alpine image
Simple HTML static site
Docker Compose setup
Kubernetes deployment ready
Multi-platform Docker image
📁 Project Structure
docker-hello-world/
├── Dockerfile
├── docker-compose.yml
├── README.md
├── html
│   └── index.html
└── k8s
    ├── deployment.yaml
    └── service.yaml

Using Docker Compose
# Clone the repository
git clone https://github.com/vishnunimangare/docker-hello-world-1.git
cd docker-hello-world-1

# Run with Docker Compose
docker compose up -d

# View the site
open http://localhost:80
Using Docker directly
# Build the image
docker build -t vishnunimangaredocker/docker-hello-world:latest .

# Run the container
docker run -d -p 80:80 vishnunimangaredocker/docker-hello-world:latest
Using Kubernetes
# Apply Kubernetes manifests
kubectl apply -f k8s/

# Check the service
kubectl get services

# Access via NodePort (if using local cluster)
# http://localhost:30080
🏗️ Build & Push to Docker Hub
# Build multi-platform image
docker buildx build --platform linux/amd64,linux/arm64 \
  -t vishnunimangaredocker/docker-hello-world:latest \
  -t vishnunimangaredocker/docker-hello-world:v1.0.0 \
  --push .
🧪 Testing
# Test the running container
curl http://localhost:80

# Expected response: HTML page with "Hello, Cloudnautic!"
🔧 Configuration
Port: 80 (HTTP)
Base Image: nginx:alpine
Content: Static HTML files in /html directory
📦 Docker Image
Registry: Docker Hub
Repository: vishnunimangare/docker-hello-world-1
Tags: latest, v1.0.0
🚀 Deployment Options
Local Development
docker compose up -d
Production (Kubernetes)
kubectl apply -f k8s/
