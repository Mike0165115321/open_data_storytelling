# 📊 Open Data Storytelling: From Data to Insight

## 📌 ภาพรวมโครงการ
Repository นี้เป็นส่วนหนึ่งของการแข่งขัน **mini-Hackathon: From Data to Insight - การใช้ประโยชน์จากข้อมูล Open Data**

**โจทย์การแข่งขัน:** การฝึกการใช้ประโยชน์จากข้อมูล Open Data ตั้งแต่การเตรียมข้อมูล (Data Preparation) การสำรวจข้อมูล (Exploratory Data Analysis - EDA) ไปจนถึงการหา Insight ที่มีคุณค่าเพื่อนำไปใช้งานต่อ

## 🧠 Challenge Description
การแข่งขันนี้มีเป้าหมายเพื่อส่งเสริมการเรียนรู้การใช้ประโยชน์จาก Open Data ผ่านกระบวนการวิเคราะห์ข้อมูลอย่างเป็นระบบ ตั้งแต่การเตรียมข้อมูล การสำรวจข้อมูล ไปจนถึงการสกัด Insight ที่มีความหมายต่อการตัดสินใจ

## 🗓️ ระยะเวลากิจกรรม
- **กำหนดส่งผลงาน:** 12 มีนาคม 2569

## 🏗️ โครงสร้างและการออกแบบระบบ (System Architecture & Design)

เพื่อให้การวิเคราะห์ข้อมูลและนำเสนอผลลัพธ์เป็นไปอย่างเป็นระบบ ดูแลรักษาง่าย (Maintainability) และมีประสิทธิภาพสูงสุด โครงสร้างของโปรเจกต์และสมุดโน้ต (Notebook) จึงถูกออกแบบภายใต้หลักการทางวิศวกรรมซอฟต์แวร์ดังนี้:

### โครงสร้างไฟล์ใน Repository
```text
open_data_storytelling/
│
├── dataset/                     # [Data Layer] แหล่งจัดเก็บข้อมูลดิบ
│   └── import_export.csv        # ชุดข้อมูลหลัก (มี 12 คอลัมน์, ~42,000 แถว)
│
├── 01_data_story.ipynb          # [Presentation & Business Logic Layer] หัวใจหลักของโปรเจกต์
│
├── venv/                        # [Environment] Virtual Environment สำหรับจัดการ Dependencies
├── .gitignore                   # กฎการเพิกเฉยไฟล์ขยะและไฟล์ระบบ
└── README.md                    # เอกสารอธิบายภาพรวมและสถาปัตยกรรม (ไฟล์นี้)
```

### สถาปัตยกรรมภายใน Notebook (Separation of Concerns - SoC)
สมุดโน้ต `01_data_story.ipynb` ได้รับการ Refactor เพื่อลบความเป็น Monolithic (โค้ดยาวติดกัน) ออก และแบ่งเป็น **10 เซลล์ (Cells)** ที่แยกหน้าที่กันอย่างชัดเจนตามหลัก **Single Responsibility Principle (SRP)** พร้อมแทรกร้อยเรียงเรื่องราว (Storytelling Narrative Flow) ด้วย Markdown ดังนี้:

**ส่วนที่ 1: การตั้งค่าพื้นฐาน (Foundation)**
*   **Cell 0 (Markdown):** แนะนำหัวข้อการนำเสนอ, ภาพรวม, ชุดข้อมูล, และ Roadmap นำทาง
*   **Cell 1 (Code - Dependency):** ศูนย์รวมไลบรารีที่จำเป็นทั้งหมด (pandas, numpy, plotly) ป้องกันการนำเข้าซ้ำซ้อนในเซลล์อื่น
*   **Cell 2 (Code - Config & Helper):** กำหนด Design System ระบบสี (Color Palette) และฟังก์ชันเพื่อตกแต่งกราฟแบบ Premium Dark Theme 

**ส่วนที่ 2: การประมวลผลและเตรียมข้อมูล (Data Processing)**
*   **Cell 3 (Code - ETL):** การโหลดไฟล์ CSV, การลีนข้อมูล (ลบซ้ำซ้อน, จัดการ NA), วิศวกรรมฟีเจอร์ (Feature Engineering), และพิมพ์สรุป Log ข้อมูลที่พร้อมใช้งาน

**ส่วนที่ 3: การสำรวจข้อมูลและค้นหา Insight (EDA & Deep Dive)**
*   **Cell 4 (Markdown):** อธิบาย "กลยุทธ์และเหตุผล" ว่าเหตุใดจึงเลือกใช้ Log Transform กับชุดข้อมูลนี้
*   **Cell 5 (Code - Distribution):** โค้ดแสดงความถี่ของตัวแปรเป้าหมายผ่าน Histogram และ Boxplot ด้วย Plotly
*   **Cell 6 (Markdown):** สรุป Insight เบื้องต้น และตั้งคำถามเชื่อมโยง (Bridge Question) ไปสู่ประเด็นที่เจาะลึกขึ้น
*   **Cell 7 (Code - Deep Dive):** วิเคราะห์แบบ 4 มิติด้วย Interactive Scatter Plot หาสินค้า "Hidden Gem" (รายได้สูง, น้ำหนักน้อย)

**ส่วนที่ 4: สรุปและสะท้อนผล (Actionable Conclusion)**
*   **Cell 8 (Markdown):** อธิบาย "เหตุผลในการเลือกชนิดกราฟ" และสรุปข้อเสนอแนะเชิงนโยบาย (Actionable Recommendation) แก่รัฐและภาคเอกชน
*   **Cell 9 (Code - Dashboard):** สร้างกระดาน KPI สรุปตัวเลขเศรษฐกิจมูลค่ารวม 6 มิติ ให้เห็นภาพรวมทั้งหมดได้อย่างรวดเร็ว

---

## ⚡ การเพิ่มประสิทธิภาพเชิงรุก (Proactive Optimization)

นอกจากการจัดโครงสร้างให้อ่านและรักษาง่ายแล้ว โปรเจกต์นี้ยังให้ความสำคัญกับการจัดการทรัพยากร (Resource Efficiency) อีกด้วย:

1. **Vectorized Operations (CPU & Latency Optimization):** 
   *   ในการคำนวณ `price_per_weight` (ราคาต่อหน่วยน้ำหนัก) มีการละทิ้งการใช้คำสั่ง `df.apply(lambda ...)` ที่ทำงานช้า ไปใช้ `np.where()` ของ Numpy แทน
   *   **ผลลัพธ์:** การคำนวณถูกส่งผ่านไปยัง C-backend ลด Latency ลงมหาศาล และคำนวณข้อมูลระดับหมื่น/แสนแถวได้เร็วกว่าเดิมถึง ~100 เท่า
2. **Notebook Output Cleansing (Memory Management):** 
   *   การใช้งานไลบรารีกราฟ Interactive (Plotly) จะทำการฝังข้อมูล JSON ชุดใหญ่เข้าไปในไฟล์ `.ipynb` เสมอ
   *   **ผลลัพธ์:** ไฟล์ Notebook เริ่มต้นที่มีขนาดบวมถึง ~13 MB ถูกคลีนล้างสถานะในเซลล์เพื่อลดขนาดเหลือเพียง **~22 KB** ช่วยลดต้นทุนพื้นที่บน Git Repository และลดโหลดการดึงข้อมูลจาก Server เวลาดูผ่านออนไลน์

---

## ⚙️ วิธีการติดตั้งและใช้งาน (Setup & Installation)

1. **Clone Repository:**
   ```bash
   git clone https://github.com/Mike0165115321/open_data_storytelling.git
   cd open_data_storytelling
   ```

2. **เปิดการใช้งาน Virtual Environment:**
   เพื่อให้มั่นใจว่าแพ็กเกจ (Dependencies) ถูกแยกออกจากระบบหลักของเครื่อง ไม่เกิดการตีกันของเวอร์ชันไลบรารี
   ```bash
   # สำหรับ Linux/Mac (Bash/Zsh)
   source venv/bin/activate
   ```

3. **ติดตั้งไลบรารีที่ปรากฏในไฟล์ Notebook (Requirements):**
   *โปรเจกต์นี้ใช้งานไลบรารีหลัก ได้แก่ `pandas`, `numpy`, และ `plotly`*

4. **รันสมุดโน้ตวิเคราะห์ผลลัพธ์:**
   ```bash
   jupyter notebook 01_data_story.ipynb
   ```
   **✨ คำแนะนำ:** เมื่อเปิดไฟล์แล้ว ให้ไปที่เมนู **`Kernel`** -> เลือก **`Restart & Run All`** เพื่อให้โค้ดประมวลผลข้อมูลใหม่ วาดกราฟทุกรูปใหม่ตามโครงสร้างและธีม Premium Dark Theme ที่ตั้งไว้
