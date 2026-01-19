---
description: Debug และแก้ไขปัญหาอย่างเป็นระบบ
---

# Debug Workflow

## 1. รวบรวมข้อมูล

ถามผู้ใช้:

- Error message คืออะไร?
- เกิดขึ้นเมื่อไหร่ / ขั้นตอนอะไร?
- ทำซ้ำได้ไหม?
- มีการเปลี่ยนแปลงอะไรล่าสุด?

## 2. ดู Error และ Logs

### Frontend

```bash
# ดู browser console
# ดู network tab
# ดู React/Vue/Angular DevTools
```

### Backend

```bash
# ดู server logs
tail -f logs/app.log

# Docker logs
docker compose logs -f <service>
```

### Database

```bash
# PostgreSQL logs
docker compose logs db

# Check connections
SELECT * FROM pg_stat_activity;
```

## 3. ระบุสาเหตุ

1. อ่าน error message ให้ละเอียด
2. ดู stack trace หา line ที่ผิด
3. ตรวจสอบ recent changes (git diff)
4. ค้นหา similar issues

## 4. สร้าง Hypothesis

1. ตั้งสมมติฐานสาเหตุที่เป็นไปได้
2. เรียงลำดับความน่าจะเป็น
3. ทดสอบทีละสมมติฐาน

## 5. แก้ไขปัญหา

1. เขียน fix
2. ทดสอบว่าแก้ได้
3. ตรวจสอบ side effects
4. เพิ่ม test ป้องกันการเกิดซ้ำ

## 6. Verify

```bash
# Run tests
npm test
./mvnw test
pytest

# Manual test
# ทำตามขั้นตอนเดิมที่เกิด bug
```

## 7. Document

- สรุปสาเหตุและวิธีแก้
- Update documentation ถ้าจำเป็น
- Commit ด้วย message ที่ชัดเจน

```bash
git commit -m "fix: <description of the bug and fix>"
```
