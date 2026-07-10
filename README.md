# DGA306 (รุ่น 2) Group 7 Example

## โปรเจกต์นี้คืออะไร

โปรเจกต์นี้เป็นตัวอย่างการวิเคราะห์ข้อมูลสาธารณะจากหน่วยงานภาครัฐไทย ด้วย Python และ Jupyter Notebook โดยมุ่งเน้นให้ผู้เรียนเห็นภาพว่าการทำงานกับข้อมูลจริงนั้นเริ่มต้นอย่างไร ตั้งแต่การค้นหาและตรวจสอบข้อมูล ไปจนถึงการสร้างกราฟ สำรวจ pattern และเสนอแนวทางต่อยอด

โปรเจกต์ใช้ข้อมูลของ **สถาบันบริหารจัดการธนาคารที่ดิน (LABAI)** เป็นกรณีศึกษาหลัก และเก็บตัวอย่างแนวคิดจาก **สถาบันส่งเสริมศิลปหัตถกรรมไทย (SACIT)** และ **สถาบันพระปกเกล้า (KPI)** ไว้เป็นแนวทางต่อยอดสำหรับผู้ที่สนใจ

---

## ดูผลลัพธ์
- **main** [pages version](https://1-brain-cell.github.io/dga306-july2026-group7/)
- **อ่านสรุป:** [รายงานสรุปโครงการ](reports/html/final_summary.html)
- **ดูกราฟข้อมูล:** [รายงานข้อมูล interactive](reports/html/interactive_data_report.html)
- **ดู ML baseline:** [รายงาน ML baseline](reports/html/ml_baseline_report.html)
- **ดู code/notebook:** [โฟลเดอร์ notebooks](https://github.com/1-brain-cell/dga306-july2026-group7/tree/master/notebooks)
- **รวมแหล่งข้อมูล:** [docs/data_sources.md](docs/data_sources.md)
- **ข้อจำกัด:** [docs/limitations.md](docs/limitations.md)
- **วิธีรัน:** [docs/how_to_run.md](docs/how_to_run.md)

---

## ใช้ข้อมูลอะไร

### ข้อมูลหลัก: LABAI

| ไฟล์ | เนื้อหา |
|---|---|
| `labai_registered_land_demand_supply.json` | จำนวนผู้ประสงค์ใช้ที่ดินและเจ้าของที่ดินที่ลงทะเบียน รายจังหวัด 77 แถว |
| `labai_land_matching.xlsx` | ข้อมูลการจับคู่ที่ดินรายจังหวัด (มีค่า `-` ที่ยังไม่ยืนยันความหมาย) |
| `labai_registered_landowners.json` | จำนวนเจ้าของที่ดินที่ลงทะเบียน รายจังหวัด |

### ข้อมูลตัวอย่างเสริม: SACIT

| ไฟล์ | เนื้อหา |
|---|---|
| `sacit_craft_product_overview_2568.csv` | ภาพรวมผลิตภัณฑ์ศิลปหัตถกรรมไทย รายเดือน |
| `sacit_craft_community_2564_2568.xlsx` | รายการชุมชนหัตถกรรมทั่วไทย ปี 2564–2568 |

ดูรายละเอียดแหล่งข้อมูลทั้งหมดใน [docs/data_sources.md](docs/data_sources.md)

---

## ควรเปิดไฟล์ไหนก่อน

หากต้องการดูผลลัพธ์โดยไม่รันโค้ด ให้เปิด notebook ตามลำดับนี้:

1. **`notebooks/01_dataset_discovery.ipynb`** — เริ่มจากที่นี่
2. `notebooks/02_schema_audit.ipynb`
3. `notebooks/03_labai_descriptive_diagnostic.ipynb`
4. `notebooks/04_labai_interactive_report.ipynb`
5. `notebooks/05_labai_predictive_baseline.ipynb`
6. `notebooks/06_labai_prescriptive_summary.ipynb`
7. *(ตัวอย่างเสริม)* `notebooks/examples/07_sacit_export_idea_example.ipynb`
8. *(ตัวอย่างเสริม)* `notebooks/examples/08_sacit_community_idea_example.ipynb`
9. *(ตัวอย่างเสริม)* `notebooks/examples/09_kpi_governance_conflict_idea_template.ipynb`

Notebook ทุกไฟล์มี output ที่บันทึกไว้แล้ว สามารถเปิดอ่านได้โดยไม่ต้องรันใหม่

---

## รายงาน HTML สำหรับเปิดอ่าน

นอกจาก Jupyter Notebook แล้ว โครงการยังมีรายงานสรุปในรูปแบบหน้าเว็บ HTML สำเร็จรูปเพื่อให้เปิดอ่านผลการวิเคราะห์และดูตารางสรุปได้ทันทีโดยไม่ต้องรันโค้ด:

- **[reports/html/final_summary.html](reports/html/final_summary.html)**: รายงานสรุปปิดโครงการ รวบรวมข้อมูลที่พบจริงจากการวิเคราะห์เชิงพรรณนา สรุปผลการทดลองโมเดล baseline และข้อจำกัดในการตีความ
- **[reports/html/interactive_data_report.html](reports/html/interactive_data_report.html)**: รายงานวิเคราะห์ข้อมูลแบบ Interactive ด้วยกราฟของ Plotly (เช่น กราฟส่วนต่าง demand/supply รายจังหวัดที่สามารถเอาเมาส์ชี้ดูชื่อจังหวัดและค่าตัวเลขได้)
- **[reports/html/ml_baseline_report.html](reports/html/ml_baseline_report.html)**: รายงานสรุปผลการทดลองนำข้อมูลมาทำ clustering และ classification baseline เพื่อเป็นแนวทางเบื้องต้นสำหรับผู้เรียน

> [!NOTE]
> **ข้อแนะนำในการอ่านรายงาน HTML:**
> - หากเปิดผ่าน GitHub Pages สามารถเปิดรายงาน HTML เป็นหน้าเว็บได้โดยตรง
> - หากเปิดจาก file browser ของ GitHub ระบบอาจแสดงซอร์สโค้ด HTML แทนการเรนเดอร์หน้าเว็บ
> - กรณีนั้นให้ดาวน์โหลดไฟล์ HTML แล้วเปิดด้วยเว็บเบราว์เซอร์ เช่น Chrome, Edge หรือ Safari

---

## Notebook แต่ละไฟล์ทำอะไร

| Notebook | หน้าที่ |
|---|---|
| `01_dataset_discovery.ipynb` | ลงทะเบียน dataset ของ LABAI, SACIT และ KPI พร้อม URL แหล่งข้อมูลทางการ |
| `02_schema_audit.ipynb` | ตรวจสอบ schema จากไฟล์จริง ดู row count, column, missing value |
| `03_labai_descriptive_diagnostic.ipynb` | ทำความสะอาดข้อมูล, สร้างกราฟเปรียบเทียบ demand/supply รายจังหวัด, วิเคราะห์ส่วนต่างและ correlation |
| `04_labai_interactive_report.ipynb` | สร้างกราฟ interactive ด้วย Plotly สำหรับดูค่ารายจังหวัดแบบ hover |
| `05_labai_predictive_baseline.ipynb` | สำรวจ clustering (KMeans) และสาธิต classification baseline (Logistic Regression) |
| `06_labai_prescriptive_summary.ipynb` | สรุปข้อเสนอแนะจากผลวิเคราะห์ อธิบายข้อจำกัด และแนะนำข้อมูลที่ควรเก็บเพิ่ม |
| `07_sacit_export_idea_example.ipynb` | ตัวอย่างการอ่านและสร้างกราฟจาก CSV ของ SACIT |
| `08_sacit_community_idea_example.ipynb` | ตัวอย่างนับและเปรียบเทียบชุมชนหัตถกรรมตามภูมิภาค |
| `09_kpi_governance_conflict_idea_template.ipynb` | template วางแผนสำหรับข้อมูลของ KPI (ยังไม่ดาวน์โหลดข้อมูลจริง) |

---

## ขั้นตอนการทำงาน

โปรเจกต์นี้ทำงานตามขั้นตอนต่อไปนี้:

1. **ค้นหา dataset** — ลงทะเบียน URL ทางการและสถานะ download ของแต่ละชุดข้อมูล
2. **ตรวจ schema** — อ่านไฟล์จริงเพื่อดู column, ประเภทข้อมูล, ค่าว่าง และความผิดปกติ
3. **ทำความสะอาด** — สร้าง processed CSV โดยเก็บข้อมูลต้นฉบับไว้ แปลงประเภทข้อมูล และบันทึก flag สำหรับค่าที่ไม่แน่ชัด
4. **วิเคราะห์เชิงพรรณนาและวินิจฉัย** — สร้างกราฟ ranking, scatter, comparison และคำนวณ correlation
5. **สำรวจ ML เบื้องต้น** — ทดลอง clustering และ classification เพื่อแสดง workflow ไม่ใช่เพื่อสร้าง production model
6. **สรุปข้อเสนอ** — ระบุจังหวัด/กลุ่มที่ควรตรวจ metadata เพิ่ม และแนะนำ column ที่ควรเก็บในอนาคต

---

## ผลลัพธ์หลัก

ผลต่อไปนี้มาจากไฟล์ LABAI ที่ดาวน์โหลดเมื่อ 10 กรกฎาคม 2026 และอธิบายเฉพาะไฟล์นั้น ไม่ใช่การประเมินสถานะของโครงการหรือจังหวัด

- จำนวนผู้ประสงค์ใช้ที่ดินรวม 77 จังหวัด: **1,371 ราย**
- จำนวนเจ้าของที่ดินรวม 77 จังหวัด: **80 ราย**
- จังหวัดที่มีผู้ประสงค์ใช้ที่ดินมากกว่าเจ้าของที่ดิน: **68 จังหวัด**
- Pearson correlation ระหว่างผู้ประสงค์กับเจ้าของที่ดิน: **ประมาณ 0.47**
- ข้อมูลการจับคู่ที่มีค่าตัวเลข: **7 จาก 77 แถว** (ที่เหลือเป็น `-`)

---

## ML ทำอะไร

### Clustering

ใช้ KMeans แบ่งจังหวัดออกเป็น 3 กลุ่ม โดยอิงจาก feature จำนวนผู้ประสงค์และเจ้าของที่ดิน เพื่อ **มองหา pattern เบื้องต้น** เท่านั้น ไม่ใช่การจัดอันดับหรือประเมินประสิทธิภาพจังหวัด

### Classification

สร้าง label `high_gap` จากค่า quantile 75% ของส่วนต่าง แล้วฝึก Logistic Regression เพื่อ **สาธิต workflow** การแบ่ง train/test และการดู metric เบื้องต้น label นี้ไม่ใช่สถานะทางการ

### Regression

**ไม่ได้ทำ** เพราะ feature หลายตัวมีความสัมพันธ์โดยตรงกับ target ที่เป็นไปได้ ทำให้มีความเสี่ยง data leakage ซึ่งจะให้ผลดูดีเกินจริง

---

## ข้อจำกัด

- ข้อมูลมีเพียง 77 แถว — เพียงพอสำหรับสำรวจ ไม่เพียงพอสำหรับ model ที่เชื่อถือได้สูง
- ไม่มีข้อมูลช่วงเวลา — ไม่รองรับ forecasting
- ค่า `-` ในข้อมูลการจับคู่ยังไม่มีความหมายที่ยืนยัน
- Clustering และ Classification เป็น educational baseline ไม่ใช่ระบบทำนายจริง

อ่านรายละเอียดเพิ่มเติมใน [docs/limitations.md](docs/limitations.md)

---

## วิธีรัน

```bash
# 1. สร้าง virtual environment
python -m venv .venv

# 2. Activate (Windows PowerShell)
.\.venv\Scripts\Activate.ps1

# 3. ติดตั้ง dependencies
pip install -r requirements.txt

# 4. เปิด Jupyter
jupyter lab
```

จากนั้นเปิด notebook ตามลำดับ `01` ถึง `06`

ดูคำแนะนำละเอียดใน [docs/how_to_run.md](docs/how_to_run.md)

---

## หมายเหตุ Font

ไฟล์ `Sarabun-Regular.ttf` รวมอยู่ในโปรเจกต์เพื่อให้กราฟและ notebook แสดงภาษาไทยได้ถูกต้อง Font นี้เผยแพร่ภายใต้ SIL Open Font License 1.1 จาก Google Fonts
