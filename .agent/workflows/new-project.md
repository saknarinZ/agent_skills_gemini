---
description: สร้างโปรเจคใหม่พร้อม setup ครบถ้วน
---

# New Project Workflow

// turbo-all

## 1. ถามข้อมูลโปรเจค

ถามผู้ใช้:

- ชื่อโปรเจค?
- ประเภท? (Full-stack / Frontend only / Backend only)
- Frontend framework? (Angular / React / Vue / Next.js)
- Backend stack? (Spring Boot / Node.js / Python)
- Database? (PostgreSQL / MongoDB / None)
- ต้องการ Docker? (Yes / No)

## 2. สร้าง Frontend

### Angular

```bash
npx -y @angular/cli new <name> --style=scss --routing=true --ssr=false
cd <name>
```

### React (Vite)

```bash
npx -y create-vite@latest <name> --template react-ts
cd <name>
npm install
```

### Vue 3

```bash
npx -y create-vue@latest <name>
cd <name>
npm install
```

### Next.js

```bash
npx -y create-next-app@latest <name> --typescript --tailwind --eslint --app --src-dir
cd <name>
```

## 3. สร้าง Backend

### Spring Boot

```bash
curl -G https://start.spring.io/starter.zip \
  -d type=maven-project \
  -d language=java \
  -d bootVersion=3.4.1 \
  -d baseDir=<name>-api \
  -d groupId=com.example \
  -d artifactId=<name>-api \
  -d dependencies=web,data-jpa,postgresql,lombok,validation \
  -o backend.zip && unzip backend.zip && rm backend.zip
```

### Node.js (Express)

```bash
mkdir <name>-api && cd <name>-api
npm init -y
npm install express cors helmet morgan dotenv
npm install -D typescript @types/node @types/express ts-node nodemon
npx tsc --init
mkdir -p src/{controllers,services,routes,middlewares}
```

### Python (FastAPI)

```bash
mkdir <name>-api && cd <name>-api
python -m venv venv
source venv/bin/activate
pip install fastapi uvicorn sqlalchemy psycopg2-binary python-dotenv
mkdir -p app/{api,core,models,schemas,services}
```

## 4. Setup Database (Docker)

```bash
cat > docker-compose.yml << 'EOF'
version: '3.8'
services:
  db:
    image: postgres:16-alpine
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: mydb
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data
volumes:
  postgres_data:
EOF
```

## 5. สร้าง Git Repository

```bash
git init
git add .
git commit -m "Initial commit"
```

## 6. ทดสอบว่า Run ได้

### Frontend

```bash
npm run dev
# หรือ npm start สำหรับ Angular
```

### Backend

```bash
# Spring Boot
./mvnw spring-boot:run

# Node.js
npm run dev

# Python
uvicorn app.main:app --reload
```

## 7. เปิด Browser ทดสอบ

ใช้ browser tool เปิดดู frontend ที่ http://localhost:3000 หรือ http://localhost:4200
