# พี่มุกน่าร้ากก 🌿

หน้าเว็บเล็กๆ ทำให้พี่มุกเล่น — mini quiz, tier-list ที่เที่ยว,
ปฏิทินย้อนหลัง 2 อาทิตย์ และหน้าสรุปที่กดคัดลอกส่งกลับมาได้

**ลิงก์:** https://dainovv.github.io/mook/

## โครงสร้าง

ดู [docs/STRUCTURE.md](docs/STRUCTURE.md) — มีวิธีเพิ่มหน้าใหม่
และตารางบอกว่าเนื้อหาแต่ละส่วนแก้ที่ตัวแปรไหน

สรุปสั้นๆ:

- `index.html` — หน้าหลัก (ห้ามย้ายออกจาก root ไม่งั้นลิงก์พัง)
- `assets/` — เพลง, CSS/JS ถ้าแยกออกวันหลัง
- `pages/` — หน้าใหม่ๆ ในอนาคต
- `diary/` — ไดอารี่ส่วนตัว **ไม่ขึ้น GitHub** (`.gitignore` กันไว้)
- `docs/` — โน้ตโปรเจกต์

## รันในเครื่อง

เปิด `index.html` ในเบราว์เซอร์ได้เลย ไม่ต้อง build ไม่ต้องรัน server

## Deploy

push ขึ้น `main` แล้ว GitHub Pages เอาขึ้นเองภายใน ~1 นาที

```bash
git add -A && git commit -m "..." && git push origin main
```

## เครดิตเพลง

"Carefree" โดย Kevin MacLeod (incompetech.com) — CC BY 4.0
ต้องคงเครดิตท้ายเว็บไว้ตามไลเซนส์
