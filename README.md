# Lichen AI

เว็บแอป AI สำหรับโครงงานวิทยาศาสตร์เรื่องการใช้ไลเคนเป็นตัวชี้วัดคุณภาพอากาศ

## ฟังก์ชัน

- เปิดกล้องมือถือและถ่ายภาพจริง
- เลือกรูปจากอุปกรณ์
- ใช้โมเดล Teachable Machine Image Classification
- แสดงชนิด/ลักษณะไลเคน
- แสดงความมั่นใจของโมเดล
- แสดงผลประเมินคุณภาพอากาศ
- ใช้งานผ่าน GitHub Pages

## 1. สร้างโมเดล AI

เข้า Teachable Machine > Image Project

แนะนำให้สร้างคลาสตามข้อมูลที่มีจริง เช่น

- Crustose
- Foliose
- Fruticose
- Poor

**สำคัญ:** อย่ากำหนดว่าไลเคนชนิดหนึ่ง = คุณภาพอากาศระดับใดโดยไม่มีข้อมูลภาคสนามรองรับ
สำหรับโครงงานที่จริงจัง ควรเก็บภาพจากพื้นที่ที่มีข้อมูลคุณภาพอากาศจริง แล้วฝึกโมเดลจากข้อมูลนั้น

เมื่อ Train เสร็จ ให้กด Export Model > Upload > Copy URL

## 2. ใส่ Model URL

เปิด `script.js`

แก้:

const MODEL_URL = "PUT_YOUR_TEACHABLE_MACHINE_MODEL_URL_HERE/";

เป็น URL ของโมเดล เช่น:

const MODEL_URL = "https://teachablemachine.withgoogle.com/models/XXXXXXXXX/";

## 3. ทดสอบ

เปิดเว็บไซต์ผ่าน HTTPS หรือ GitHub Pages

การใช้กล้องบนมือถือมักต้องการ secure context (HTTPS)

## 4. GitHub Pages

สร้าง repository ชื่อ:

Lichen_AI

อัปโหลด:

- index.html
- style.css
- script.js
- README.md

จากนั้น:

Settings
> Pages
> Build and deployment
> Deploy from a branch
> Branch: main
> Folder: / (root)
> Save

รอ GitHub สร้างเว็บไซต์ แล้วเปิด URL ของ GitHub Pages

## หมายเหตุทางวิทยาศาสตร์

Lichen AI ในตัวอย่างนี้เป็นระบบจำแนกภาพและประเมินตามเกณฑ์ที่ผู้พัฒนากำหนด ไม่ใช่เครื่องวัด PM2.5 โดยตรง

หากต้องการอ้างว่า "คุณภาพอากาศดี/ปานกลาง/ไม่ดี" ควรมีข้อมูลอ้างอิง เช่น PM2.5, PM10, NO2 หรือข้อมูลสถานีตรวจวัดในพื้นที่เดียวกัน เพื่อสร้างเกณฑ์และตรวจสอบความแม่นยำของโมเดล
