# วิธีรัน Notebook

คู่มือนี้อธิบายวิธีติดตั้งและรัน notebook ใน `notebooks/` ตั้งแต่ต้น

[กลับหน้าแรก](../)

---

## ขั้นตอนที่ 1: ติดตั้ง Python environment

เปิด terminal หรือ PowerShell จากโฟลเดอร์ `github_upload_clean/` แล้วรันคำสั่ง:

```bash
python -m venv .venv
```

จากนั้น activate environment:

**Windows (PowerShell):**
```powershell
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux:**
```bash
source .venv/bin/activate
```

---

## ขั้นตอนที่ 2: ติดตั้ง dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

---

## ขั้นตอนที่ 3: เปิด Jupyter

```bash
jupyter lab
```

หลังจากรันคำสั่ง เบราว์เซอร์จะเปิด Jupyter Lab โดยอัตโนมัติ

---

## ขั้นตอนที่ 4: รัน Notebook ตามลำดับ

**ควรเปิดไฟล์ README.md ก่อนเพื่อทำความเข้าใจภาพรวม** จากนั้นเปิด notebook ตามลำดับ:

| ลำดับ | ไฟล์ | สิ่งที่จะเห็น |
|---|---|---|
| 1 | `notebooks/01_dataset_discovery.ipynb` | รายการ dataset และ URL แหล่งข้อมูล |
| 2 | `notebooks/02_schema_audit.ipynb` | schema ของแต่ละไฟล์ raw |
| 3 | `notebooks/03_labai_descriptive_diagnostic.ipynb` | กราฟเปรียบเทียบ demand/supply และตาราง |
| 4 | `notebooks/04_labai_interactive_report.ipynb` | กราฟ interactive ของ LABAI |
| 5 | `notebooks/05_labai_predictive_baseline.ipynb` | clustering และ classification baseline |
| 6 | `notebooks/06_labai_prescriptive_summary.ipynb` | สรุปข้อเสนอและข้อจำกัด |

**ตัวอย่างเสริม** (อ่านหลังจากเข้าใจ LABAI แล้ว):

| ลำดับ | ไฟล์ | สิ่งที่จะเห็น |
|---|---|---|
| 7 | `notebooks/examples/07_sacit_export_idea_example.ipynb` | ตัวอย่างกราฟข้อมูลผลิตภัณฑ์ SACIT |
| 8 | `notebooks/examples/08_sacit_community_idea_example.ipynb` | ตัวอย่างนับชุมชนหัตถกรรมตามภูมิภาค |
| 9 | `notebooks/examples/09_kpi_governance_conflict_idea_template.ipynb` | template วางแผนข้อมูล KPI |

---

## หมายเหตุสำหรับการรันซ้ำ

- Notebook ทั้งหมดมี output ที่บันทึกไว้แล้ว ผู้อ่านสามารถ **เปิดดูผลได้โดยไม่ต้องรันซ้ำ**
- หากต้องการรันซ้ำเพื่อตรวจสอบ ควรรันตามลำดับ `01` ถึง `06` เพราะ notebook หลังพึ่งพาไฟล์ที่สร้างโดย notebook ก่อน
- Notebook `05` มีการฝึก machine learning baseline ทุกครั้งที่รัน ผลเล็กน้อยอาจแตกต่างจาก random seed
- หากกราฟแสดงภาษาไทยไม่สมบูรณ์ ไฟล์ `Sarabun-Regular.ttf` ต้องอยู่ในโฟลเดอร์เดียวกับโปรเจกต์

---

## ไฟล์ที่ควรอ่านก่อน

1. `README.md` — ภาพรวมโปรเจกต์
2. `docs/data_sources.md` — แหล่งข้อมูลและชื่อไฟล์
3. `docs/limitations.md` — ข้อจำกัดที่สำคัญ
4. จากนั้นเปิด notebook ตามลำดับ

---

## การเปิดอ่านรายงาน HTML โดยตรง

ในกรณีที่คุณไม่ต้องการติดตั้ง Python หรือรันโค้ด คุณสามารถเปิดดูรายงานวิเคราะห์ผลลัพธ์ในรูปแบบหน้าเว็บ HTML ได้ทันที:

1. เข้าไปที่โฟลเดอร์ `reports/html/`
2. ดับเบิ้ลคลิกเพื่อเปิดไฟล์ต่อไปนี้ด้วยเว็บเบราว์เซอร์ (Chrome, Edge, Firefox, Safari) บนเครื่องของคุณ:
   - `final_summary.html` — รายงานสรุปภาพรวมปิดโครงการ
   - `interactive_data_report.html` — รายงานข้อมูลรายจังหวัดแบบ Interactive
   - `ml_baseline_report.html` — รายงานสรุปผลการทดลองโมเดล baseline

> [!NOTE]
> **หมายเหตุสำหรับการเปิดบน GitHub:**
> - หน้าเว็บ GitHub อาจไม่เรนเดอร์ (Render) ไฟล์ HTML โดยตรง และจะแสดงเป็นซอร์สโค้ดแทน
> - วิธีแก้ไขคือ ให้ดาวน์โหลด (Download) ไฟล์ HTML ลงในเครื่องคอมพิวเตอร์ของคุณก่อนแล้วค่อยเปิด หรือใช้งานผ่าน GitHub Pages
> - ทั้งนี้ **Jupyter Notebook (`.ipynb`) ยังคงเป็นรูปแบบหลัก** ที่ควรใช้สำหรับการอ่านและตรวจสอบกระบวนการทำงานทั้งหมดในโปรเจกต์นี้
