# โครงสร้างโปรเจกต์

```
.
├── index.html          ← หน้าที่ส่งพี่มุก (ห้ามย้าย! GitHub Pages เสิร์ฟจาก root)
├── assets/
│   ├── audio/          เพลงประกอบ
│   ├── css/            เผื่อแยก CSS ออกจาก index.html วันหลัง
│   └── js/             เผื่อแยก JS ออกวันหลัง
├── pages/              หน้าเว็บใหม่ๆ ในอนาคต (ดูข้างล่าง)
├── diary/              ไดอารี่ส่วนตัว — ไม่ขึ้น GitHub
│   ├── entries/        ไฟล์รายวัน YYYY-MM-DD.md
│   └── TEMPLATE.md
└── docs/               โน้ตของโปรเจกต์เอง
```

## ข้อจำกัดสำคัญ

**`index.html` ต้องอยู่ที่ root** เพราะ GitHub Pages เสิร์ฟจาก branch `main`
โฟลเดอร์ `/ (root)` ถ้าย้ายไปที่อื่น ลิงก์ `https://dainovv.github.io/mook/`
ที่ส่งพี่มุกไปแล้วจะพัง

## เพิ่มหน้าใหม่ยังไง

สร้างโฟลเดอร์ใน `pages/` แล้วใส่ `index.html` ข้างใน:

```
pages/birthday/index.html   →  https://dainovv.github.io/mook/pages/birthday/
```

ถ้าอยากได้ URL สั้นกว่า ให้สร้างโฟลเดอร์ที่ root ตรงๆ:

```
birthday/index.html         →  https://dainovv.github.io/mook/birthday/
```

ใช้ path แบบ **relative** เสมอ (`assets/audio/...` ไม่ใช่ `/assets/audio/...`)
เพราะเว็บอยู่ใต้ `/mook/` ไม่ได้อยู่ที่ root ของโดเมน — ถ้าใส่ `/` นำหน้า
มันจะไปหาที่ `dainovv.github.io/assets/...` แล้วไม่เจอ

## เนื้อหาในหน้าปัจจุบันแก้ที่ไหน

ทุกอย่างอยู่ใน `index.html` ไฟล์เดียว ค้นหาตัวแปรพวกนี้ใน `<script>`:

| อยากแก้ | ค้นหา |
|---|---|
| คำถาม quiz | `QUIZ_QUESTIONS` |
| มุขไม้เทนนิส | `RACKET_WRONG_OPTIONS` |
| รายชื่อที่เที่ยว | `TIER_PLACES` |
| การ์ดปฏิทิน | `CAL_DAYS` |
| คำขอร้องตอนกดปุ่ม "ไม่" | `BEG_LINES` / `NO_TAUNTS` |
| ตำแหน่งที่ปุ่ม "ไม่" กระโดดไป | `NO_SLOTS` |

ลำดับหน้า: intro → quiz → tier-list → calendar → summary → outro
(ดูฟังก์ชัน `showScreen()` กับ `startCalendar()`)

## ถ้าไฟล์เริ่มใหญ่เกินไป

`index.html` ตอนนี้ ~1,800 บรรทัด ถ้าจะแยก:

1. ตัด `<style>` ออกไป `assets/css/main.css`
2. ตัด `<script>` ออกไป `assets/js/main.js`
3. ใน `index.html` ใส่ `<link rel="stylesheet" href="assets/css/main.css">`
   กับ `<script src="assets/js/main.js"></script>` (ไว้ก่อนปิด `</body>`)

ยังไม่จำเป็นตอนนี้ — ไฟล์เดียวข้อดีคือเปิดจาก `file://` ได้เลย
ไม่ต้องรัน server

## เพลงประกอบ

`assets/audio/carefree.mp3` — "Carefree" โดย Kevin MacLeod
(incompetech.com) licensed under CC BY 4.0 **ต้องคงเครดิตท้ายเว็บไว้**
(ดูตัวแปร `musicCredit` ใน `index.html`)
