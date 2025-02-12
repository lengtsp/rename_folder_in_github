# วิธีการ Rename Directory ใน GitHub Repository

คู่มือนี้จะแสดงวิธีการเปลี่ยนชื่อ (rename) directory ใน GitHub repository

## ขั้นตอนการทำงาน

### 1. Clone Repository

ดาวน์โหลด repository จาก GitHub มายังเครื่องของคุณด้วยคำสั่ง:

```bash
git clone https://github.com/lengtsp/custom_rag_pipeline.git
```

### 2. เข้าสู่ Directory ของ Repository

เปลี่ยน directory ไปยัง repository ที่เพิ่ง clone มา:

```bash
cd custom_rag_pipeline
```

### 3. Rename Directory และ Push การเปลี่ยนแปลง

ทำการเปลี่ยนชื่อ directory และอัพเดทขึ้น GitHub:

```bash
# เปลี่ยนชื่อ directory
git mv "extract pdf" "1. extract pdf"

# commit การเปลี่ยนแปลง
git commit -m "rename directory"

# push ขึ้น GitHub
git push origin main
```

## คำแนะนำเพิ่มเติม

- ควรใช้คำสั่ง `git mv` แทนการ rename ด้วยวิธีปกติ เพราะ git จะติดตามประวัติการเปลี่ยนแปลงได้ดีกว่า
- ถ้าเจอ error "not a git repository" ให้ตรวจสอบว่าคุณอยู่ใน directory ที่ถูกต้องหรือไม่
- แนะนำให้หลีกเลี่ยงการใช้เว้นวรรคในชื่อไฟล์และโฟลเดอร์ ควรใช้ underscore (_) หรือ hyphen (-) แทน

## การแก้ไขปัญหาที่พบบ่อย

1. **Error: not a git repository**
   - ตรวจสอบว่าคุณได้ clone repository และอยู่ใน directory ที่ถูกต้อง

2. **Error: Permission denied**
   - ตรวจสอบว่าคุณมีสิทธิ์ในการ push ไปยัง repository
   - ตรวจสอบการตั้งค่า GitHub authentication

3. **Error: Failed to push some refs**
   - ลอง pull การเปลี่ยนแปลงล่าสุดจาก repository ก่อน:
   ```bash
   git pull origin main
   ```

## การติดต่อและสอบถามเพิ่มเติม

หากมีคำถามหรือพบปัญหาในการใช้งาน สามารถติดต่อผ่าน:
- สร้าง Issue ใน GitHub Repository
- ติดต่อผู้ดูแล Repository โดยตรง
