# 📊 Open Data Storytelling: From Data to Insight

## 📌 ภาพรวมโครงการ
Repository นี้เป็นส่วนหนึ่งของการแข่งขัน **mini-Hackathon: From Data to Insight - การใช้ประโยชน์จากข้อมูล Open Data**

**โจทย์การแข่งขัน:** การฝึกการใช้ประโยชน์จากข้อมูล Open Data ตั้งแต่การเตรียมข้อมูล (Data Preparation) การสำรวจข้อมูล (Exploratory Data Analysis - EDA) ไปจนถึงการหา Insight ที่มีคุณค่าเพื่อนำไปใช้งานต่อ

## 🧠 Challenge Description
การแข่งขันนี้มีเป้าหมายเพื่อส่งเสริมการเรียนรู้การใช้ประโยชน์จาก Open Data ผ่านกระบวนการวิเคราะห์ข้อมูลอย่างเป็นระบบ ตั้งแต่การเตรียมข้อมูล การสำรวจข้อมูล ไปจนถึงการสกัด Insight ที่มีความหมายต่อการตัดสินใจ

## 🗓️ ระยะเวลากิจกรรม
- **กำหนดส่งผลงาน:** 12 มีนาคม 2569

## 🏗️ โครงสร้างไฟล์ปัจจุบัน (Project Structure)
เพื่อให้การทำงานเป็นระบบและดูแลรักษาได้ง่าย (Maintainability) โครงสร้างโฟลเดอร์ในโปรเจกต์นี้จึงถูกแบ่งตามความรับผิดชอบ (Single Responsibility Principle) ดังนี้:

```text
open_data_storytelling/
│
├── dataset/                     # [Data Access Layer] โฟลเดอร์จัดเก็บข้อมูลดิบ
│   └── import_export.csv        # ชุดข้อมูลหลักที่ใช้ในการวิเคราะห์
│
├── 01_data_story.ipynb          # [Presentation Layer] สมุดโน้ตหลักสำหรับการทำ EDA วิเคราะห์ข้อมูล และสร้าง Storytelling
│
├── venv/                        # [Environment] โฟลเดอร์ Virtual Environment สำหรับแยกเก็บไลบรารีของโปรเจกต์ (Ignored โดย Git)
│
├── .gitignore                   # ไฟล์กำหนดข้อยกเว้นไม่ให้นำ venv และไฟล์ขยะขึ้น Git
└── README.md                    # เอกสารอธิบายภาพรวมของโปรเจกต์ (ไฟล์นี้)
```

## ⚙️ วิธีการติดตั้งและใช้งาน (Setup & Installation)
1. **Clone Repository (ถ้ามีผู้ร่วมทีม):**
   ```bash
   git clone https://github.com/Mike0165115321/open_data_storytelling.git
   cd open_data_storytelling
   ```

2. **เปิดการใช้งาน Virtual Environment:**
   เพื่อให้มั่นใจว่าแพ็กเกจ (Dependencies) ไม่ไปตีกับระบบหลักของเครื่อง
   ```bash
   # สำหรับ Linux/Mac
   source venv/bin/activate
   
   # สำหรับ Windows (ถ้าเพื่อนร่วมทีมใช้)
   venv\Scripts\activate
   ```

3. **ติดตั้งแพ็กเกจที่จำเป็น (ถ้ามีการ Export ไว้):**
   *(หมายเหตุ: แนะนำให้รัน `pip freeze > requirements.txt` เพื่อให้นำไปรันซ้ำได้ง่าย)*

4. **เริ่มการวิเคราะห์:**
   รัน Jupyter Notebook เพื่อเปิดไฟล์ `01_data_story.ipynb` และเริ่มไล่โค้ดทีละเซลล์
   ```bash
   jupyter notebook
   ```

## 🏆 ส่วนประกอบอื่นๆ ของงาน (Hackathon Components)
- **ข้อมูล (Data):** อยู่ในโฟลเดอร์ `dataset`
- **โค้ด (Code):** การประมวลผลทั้งหมดอยู่ใน `01_data_story.ipynb`
- **สนทนา (Private/Public) & ตารางคะแนน:** สามารถติดตามได้จากแพลตฟอร์มหลักของการแข่งขัน
- **ทีม & กติกา:** อ้างอิงตามประกาศของคณะกรรมการผู้จัดงาน
