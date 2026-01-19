# Antigravity Rules & Best Practices

## 🌐 Language

- ตอบเป็นภาษาไทยเป็นหลัก ยกเว้น technical terms
- Code และ comments เขียนเป็นภาษาอังกฤษ

## 💻 Code Style

### General

- ใช้ TypeScript สำหรับ JavaScript projects เสมอ
- ใช้ meaningful names สำหรับ variables และ functions
- ไม่ใช้ magic numbers - ใช้ constants แทน
- Keep functions short (< 20 lines ideally)
- Follow Single Responsibility Principle

### Naming Conventions

- **Variables/Functions**: camelCase
- **Classes/Components**: PascalCase
- **Constants**: UPPER_SNAKE_CASE
- **Files**: kebab-case (frontend) หรือ PascalCase (components)
- **Database tables**: snake_case

### Comments

- เขียน comments เฉพาะเมื่อ "ทำไม" ไม่ชัดเจน
- ไม่ comment สิ่งที่ code บอกอยู่แล้ว
- ใช้ JSDoc/JavaDoc สำหรับ public APIs

## 🏗️ Architecture

### Frontend

- ใช้ feature-based folder structure
- แยก smart components (containers) กับ dumb components (presentational)
- State management: ใช้เมื่อจำเป็น (Zustand/Pinia/NgRx)
- API calls: รวมใน dedicated service/hooks

### Backend

- Layer architecture: Controller → Service → Repository
- ใช้ DTOs สำหรับ API input/output
- Handle errors ด้วย Global Exception Handler
- Validation ที่ controller layer

### Database

- ใช้ migrations สำหรับ schema changes
- เพิ่ม indexes สำหรับ frequently queried columns
- ใช้ soft delete เมื่อต้องการ audit trail

## 🧪 Testing

- Unit test สำหรับ business logic
- Integration test สำหรับ APIs
- E2E test สำหรับ critical user flows
- Target: 80%+ code coverage

## 🔒 Security

- ไม่ hardcode secrets
- Validate all inputs
- Use parameterized queries
- Implement proper authentication/authorization
- HTTPS only in production

## 📦 Git

### Commit Messages

```
<type>: <description>

Types: feat, fix, docs, style, refactor, test, chore
```

### Branch Naming

```
feature/<description>
bugfix/<description>
hotfix/<description>
```

## 🐳 Docker

- ใช้ multi-stage builds
- ไม่ run as root
- ใช้ specific image versions
- Include health checks

## 📝 Documentation

- README.md สำหรับทุกโปรเจค
- API documentation (Swagger/OpenAPI)
- Update docs เมื่อมีการเปลี่ยนแปลง
