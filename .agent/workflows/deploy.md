---
description: Deploy application ไปยัง production
---

# Deploy Workflow

// turbo-all

## 1. Pre-deployment Checks

### Run Tests

```bash
# Frontend
npm test
npm run lint

# Backend
./mvnw test
# หรือ
npm test
# หรือ
pytest
```

### Build Application

```bash
# Frontend
npm run build

# Backend (Spring Boot)
./mvnw package -DskipTests

# Backend (Node.js)
npm run build
```

## 2. Build Docker Images

```bash
# Build images
docker build -t myapp-frontend:latest ./frontend
docker build -t myapp-backend:latest ./backend

# Tag with version
docker tag myapp-frontend:latest myregistry/myapp-frontend:v1.0.0
docker tag myapp-backend:latest myregistry/myapp-backend:v1.0.0
```

## 3. Push to Registry

```bash
# Login to registry
docker login myregistry

# Push images
docker push myregistry/myapp-frontend:v1.0.0
docker push myregistry/myapp-backend:v1.0.0
```

## 4. Update Kubernetes Manifests

```bash
# Update image version
kubectl set image deployment/frontend frontend=myregistry/myapp-frontend:v1.0.0
kubectl set image deployment/backend backend=myregistry/myapp-backend:v1.0.0

# หรือ apply manifests
kubectl apply -f k8s/
```

## 5. Monitor Deployment

```bash
# Watch rollout
kubectl rollout status deployment/frontend
kubectl rollout status deployment/backend

# Check pods
kubectl get pods -w

# View logs
kubectl logs -f deployment/backend
```

## 6. Smoke Test

```bash
# Test endpoints
curl https://api.myapp.com/health
curl https://myapp.com

# ใช้ browser tool ทดสอบ UI
```

## 7. Rollback (if needed)

```bash
# Rollback to previous version
kubectl rollout undo deployment/frontend
kubectl rollout undo deployment/backend

# Rollback to specific revision
kubectl rollout undo deployment/backend --to-revision=2
```

## 8. Post-deployment

- [ ] ตรวจสอบ logs ไม่มี errors
- [ ] ตรวจสอบ metrics ปกติ
- [ ] แจ้ง team ว่า deploy เสร็จ
- [ ] Update changelog/release notes
