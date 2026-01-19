---
description: Review และ refactor code อย่างมีระบบ
---

# Code Review Workflow

## 1. ดูภาพรวมการเปลี่ยนแปลง

```bash
# ดู files ที่เปลี่ยน
git diff --stat

# ดู diff ทั้งหมด
git diff
```

## 2. ตรวจสอบ Code Quality

### Checklist

**Correctness**

- [ ] Logic ถูกต้อง
- [ ] Edge cases ถูก handle
- [ ] Error handling เหมาะสม

**Readability**

- [ ] ชื่อตัวแปร/function ชัดเจน
- [ ] ไม่มี magic numbers
- [ ] Comments เท่าที่จำเป็น

**Maintainability**

- [ ] ไม่มี duplicate code
- [ ] Single responsibility
- [ ] ง่ายต่อการแก้ไข

**Performance**

- [ ] ไม่มี unnecessary operations
- [ ] Database queries efficient
- [ ] ไม่มี memory leaks

**Security**

- [ ] Input validation
- [ ] ไม่มี hardcoded secrets
- [ ] ป้องกัน XSS/SQL Injection

## 3. Run Automated Checks

```bash
# Lint
npm run lint
# หรือ
./mvnw checkstyle:check

# Tests
npm test
./mvnw test
pytest

# Security scan
npm audit
```

## 4. ระบุ Issues

สร้างรายการ issues ที่พบ:

1. Critical - ต้องแก้ก่อน merge
2. Major - ควรแก้
3. Minor - Nice to have
4. Suggestion - ข้อเสนอแนะ

## 5. Suggest Improvements

ให้ suggestions สำหรับ:

- Code structure
- Design patterns ที่เหมาะสม
- Performance optimization
- Better naming

## 6. Refactor (if needed)

ถ้าต้อง refactor:

1. ทำทีละ step เล็กๆ
2. Run tests หลังทุก step
3. Commit แยก refactoring จาก feature

## 7. Summary

สรุปผลการ review:

- ✅ สิ่งที่ทำได้ดี
- ⚠️ สิ่งที่ต้องปรับปรุง
- 💡 Suggestions
- 🔥 Breaking changes (ถ้ามี)
