# บริษัท Lucablock จำกัด

## Senior Full Stack Developer (AI-driven mindset)

### แบบทดสอบทางเทคนิค (Technical Assignment)

---

## ภาพรวม (Overview)

แบบทดสอบนี้เป็น **Take-home Assignment** เพื่อใช้ประเมินความสามารถของผู้สมัครในระดับ Senior

ครอบคลุมด้าน:
- Full Stack Development
- การออกแบบระบบ (System Thinking)
- การแก้ปัญหา (Problem Solving)
- แนวคิดและการทำงานร่วมกับ AI (AI-driven mindset)

**ระยะเวลาทำแบบทดสอบทั้งหมด: 7 วัน**

---

## ส่วนที่ 1: Coding & System Design

### ธีม: แพลตฟอร์มจัดการงานด้วย AI (Mini Jira)

ผู้สมัครต้องออกแบบและพัฒนาระบบ **Backend และ Frontend** โดยมีคุณภาพระดับ Production

---

### ข้อกำหนดฝั่ง Backend

1. ใช้ Backend Stack ที่ถนัดที่สุด (เช่น Node.js, C#, Go, Java ฯลฯ)
2. พัฒนา REST API โดยแยกโครงสร้างชัดเจนเป็น
   - Controller
   - Service
   - Repository
3. ระบบ CRUD สำหรับการจัดการ Task พร้อม Workflow ของสถานะงาน
4. มีการตรวจสอบ Input, จัดการ Error และรองรับ Pagination / Filtering
5. มีเอกสาร Swagger (OpenAPI)
6. มี Postman Collection
7. มี Dockerfile และ README ที่อธิบายการใช้งานอย่างชัดเจน
8. ER-Diagram

---

### ข้อกำหนดฝั่ง Frontend

1. ใช้ Framework **Next.js**
2. ใช้ **styled-components** สำหรับการจัดการ Style
3. ใช้ **Redux หรือ Zustand** สำหรับ State Management
4. ใช้
   - Formik + Yup หรือ
   - React Hook Form + Zod

   สำหรับการ Validate ฟอร์ม
5. ออกแบบ Component ให้สามารถนำกลับมาใช้ซ้ำได้ (Reusable Components)
6. แยก **UI State** และ **Server State** อย่างชัดเจน
7. โครงสร้างโฟลเดอร์อ่านง่าย ขยายต่อได้ และเหมาะกับโปรเจคขนาดใหญ่

---

## ส่วนที่ 2: คำถามเชิงอธิบาย (Written Questions)

1. หากระบบนี้มีผู้ใช้งานพร้อมกัน 1,000 คน จุดคอขวด (Scalability Bottleneck) แรกที่คุณคาดว่าจะเกิดขึ้นคืออะไร และคุณจะแก้ไขอย่างไร

2. หากต้องการเพิ่มฟีเจอร์ AI เพื่อทำนายงานที่มีความเสี่ยงล่าช้า (At-risk tasks) คุณจะออกแบบและเชื่อมต่อเข้ากับระบบเดิมอย่างไร โดยไม่กระทบ Architecture

3. อธิบายประสบการณ์ของคุณในการทำงานกับระบบ Legacy ที่คุณไม่ได้เป็นคนออกแบบเอง

4. คุณสร้างสมดุลระหว่าง **ความเร็ว ความถูกต้อง และ Scalability** ในโปรเจคจริงอย่างไร

5. คุณใช้เครื่องมือ AI ในกระบวนการพัฒนาซอฟต์แวร์ประจำวันอย่างไร และคุณกำหนดขอบเขตการใช้งานไว้ตรงไหน

6. หากพบว่า Junior Developer ใช้ AI มากเกินไปจนส่งผลต่อคุณภาพโค้ด คุณจะจัดการสถานการณ์นี้อย่างไร

7. อะไรคือแรงจูงใจที่ทำให้คุณรับผิดชอบระบบ Production อย่างจริงจัง และสิ่งใดที่คุณกังวลมากที่สุดในการดูแลระบบเหล่านั้น

---

## การส่งงาน (Submission)

ผู้สมัครต้องส่ง:
- ลิงก์ Git Repository
- README
- เอกสาร API (Swagger / OpenAPI)
- ER-Diagram
- คำตอบในส่วน Written Questions (ไฟล์ Markdown หรือ PDF)

---

## Checklist

### Backend
- [x] REST API with Controller/Service/Repository pattern
- [x] Task CRUD with status workflow
- [x] Input validation & error handling
- [x] Pagination & Filtering
- [x] Swagger (OpenAPI) documentation
- [x] Postman Collection
- [x] Dockerfile
- [x] README
- [ ] ER-Diagram

### Frontend
- [x] Next.js framework
- [ ] styled-components (ใช้ Tailwind CSS แทน)
- [x] Zustand for State Management
- [x] React Hook Form + Zod
- [x] Reusable Components
- [x] Separated UI State and Server State
- [x] Scalable folder structure

### Written Questions
- [ ] คำถามข้อ 1 - Scalability Bottleneck
- [ ] คำถามข้อ 2 - AI Feature Integration
- [ ] คำถามข้อ 3 - Legacy System Experience
- [ ] คำถามข้อ 4 - Speed vs Correctness vs Scalability
- [ ] คำถามข้อ 5 - AI Tools in Development
- [ ] คำถามข้อ 6 - Managing Junior Developers with AI
- [ ] คำถามข้อ 7 - Production System Responsibility

### Submission
- [x] Git Repository
- [x] README
- [x] Swagger / OpenAPI
- [ ] ER-Diagram
- [ ] Written Questions (Markdown/PDF)
