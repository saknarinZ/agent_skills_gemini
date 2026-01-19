# Agent LLM Gemini Workspace

## Overview

Workspace สำหรับพัฒนา Web Applications โดยใช้ Antigravity AI Agent พร้อม Skills และ Workflows ที่ครอบคลุม

## Available Skills

เมื่อต้องการให้ Agent ใช้ skill เฉพาะทาง ให้อ้างอิง:

| Skill              | Description                   |
| ------------------ | ----------------------------- |
| `project-creation` | สร้างโปรเจคใหม่ทุก Tech Stack |
| `debugging`        | วิเคราะห์และแก้ไขบั๊ก         |
| `refactoring`      | ปรับปรุงโค้ดให้ดีขึ้น         |
| `testing`          | เขียน Tests ทุกประเภท         |
| `deployment`       | Deploy ไปยังทุก Platform      |
| `frontend`         | Angular, React, Vue, Next.js  |
| `backend`          | Spring Boot, Node.js, Python  |
| `database`         | PostgreSQL, MongoDB           |
| `devops`           | Docker, Kubernetes, CI/CD     |

## Available Workflows

| Command        | Description              |
| -------------- | ------------------------ |
| `/new-project` | สร้างโปรเจคใหม่          |
| `/debug`       | Debug อย่างเป็นระบบ      |
| `/deploy`      | Deploy to production     |
| `/code-review` | Review และ refactor code |

## Tech Stack Support

### Frontend

- Angular 17+
- React 18+ with Vite
- Vue 3 with Composition API
- Next.js 14+ with App Router

### Backend

- Spring Boot 3.x (Java 21)
- Node.js with Express/NestJS
- Python with FastAPI

### Database

- PostgreSQL 16
- MongoDB 7

### DevOps

- Docker & Docker Compose
- Kubernetes
- GitHub Actions

## Project Guidelines

1. **ใช้ TypeScript** สำหรับทุก JavaScript project
2. **Follow folder structure** ตามที่กำหนดใน Skills
3. **เขียน tests** สำหรับ business logic
4. **ใช้ Docker** สำหรับ development environment
5. **Document APIs** ด้วย OpenAPI/Swagger

## Getting Started

```bash
# สร้างโปรเจคใหม่
# ใช้ /new-project workflow

# หรือบอก Agent ว่า:
# "สร้างโปรเจค Next.js + Spring Boot + PostgreSQL ให้หน่อย"
```
