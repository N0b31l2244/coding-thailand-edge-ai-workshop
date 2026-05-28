<!-- workshop-header -->
<img width="1347" height="127" alt="Coding Thailand 2026 header" src="https://github.com/user-attachments/assets/ba5cf267-f460-4fb0-b69b-c461ae061a3b" />

# 📝 Worksheet W4 — Idea Canvas สำหรับรอบต่อยอด

> **ทำในช่วง 16:00-16:30**
> เปลี่ยนสิ่งที่ทีมทำได้ในรอบแรก ให้เป็นแผน prototype ที่อธิบายและต่อยอดได้ต่อ

---

## ข้อมูลทีม

- **ชื่อทีม:** _________________
- **ชื่อ Prototype (working title):** _________________

---

## 🎯 1. Problem & User

### a) เราจะแก้ปัญหาอะไร?
ที่จอดรถในอาคาร ห้าง หรือโรงพยาบาลไม่มีระบบแสดงสถานะแบบ real-time ทำให้ผู้ขับขี่วนหาที่จอดเสียเวลาและเชื้อเพลิง ระบบกล้อง AI แบบ Edge สามารถ classify ภาพช่องจอดได้ทันทีโดยไม่ต้องส่งข้อมูลออก cloud

### b) ใครคือ user หลัก?
• ผู้ขับขี่ที่เข้าจอดในลานจอดรถอาคาร/ห้างขนาดกลาง
• เจ้าหน้าที่/ผู้ดูแลลานจอดที่ต้องการ dashboard สถานะ
• โรงพยาบาลหรือ office building ที่ต้องการ privacy สูง

### c) ทำไม Edge AI ถึงเหมาะกับปัญหานี้? (ทำไมไม่ใช่ Cloud)
• ข้อมูลภาพกล้องในลานจอดมีความ sensitive — ไม่ควรส่งออก cloud
• ต้องการ inference < 300ms เพื่อเปลี่ยนสัญญาณ LED ทันที
• ลานจอดในอาคารบางแห่ง Wi-Fi ไม่ครอบคลุมทุกชั้น

---

## 💎 2. Value Proposition

### Unique Value (USP)
ในประโยคเดียว:

ParkVision AI ช่วย ผู้ขับขี่และผู้ดูแลลานจอด รู้สถานะช่องจอดแบบ real-time ด้วยกล้อง
ต่างจากระบบ sensor หรือ ticket เดิม เพราะ ไม่ต้องติด sensor ทุกช่อง ใช้กล้องเดียว cover หลาย slot และ AI classify ภาพได้ทันทีบน device

---

## 🛠️ 3. Solution

### a) Hardware ที่จะใช้
- UNO Q + Modulino พื้นฐาน
- เพิ่มเติม:
☑ UNO Q (main board + inference)
☑ Camera module (OV2640 หรือ ArduCAM)
☑ Modulino Pixels (LED แดง/เขียวต่อช่อง)
☑ OLED Display (แสดง slot ว่าง/เต็ม)
☐ Buzzer (แจ้งเตือนเมื่อ full)

### b) AI Model
Track: Vision (Camera)
vacant occupied blocked/unknown
Improve V2:
— เพิ่ม dataset แสงน้อย (basement)
— เก็บภาพมุมกล้องสูง (top-down)
— augment หลายสีรถ/ขนาดรถ


### c) Form Factor
- จะติดที่ไหน? ใช้ยังไง?
กล้องติดเพดานมุมสูง (top-down view) มอง slot 2–4 ช่องพร้อมกัน | inference บน UNO Q | LED bar ติดเสาทางเข้าแต่ละแถว | OLED ที่ป้ายทางเข้าหลัก

---

## 🎬 4. Scenario ตอนโชว์การทำงาน

ถ้าต้องโชว์การทำงานภายใน 2 นาที จะเรียงขั้นตอนอย่างไร?

| ขั้นตอน | ทำอะไร | เวลา |
|---|---|---|
| 1 |เปิดระบบ — กล้อง capture ภาพ slot ว่างทั้งหมด, LED เขียว, OLED "3/3 available" | 15วินาที |
| 2 |วางรถจำลอง (กล่อง/โมเดล) ใน slot 1 — AI classify "occupied", LED เปลี่ยนแดง | 20วินาที |
| 3 |วางรถครบทุก slot — OLED แสดง "FULL", buzzer ดัง, LED แดงทั้งหมด | 20วินาที |
| 4 |	นำรถออก 1 คัน — AI detect "vacant" อัตโนมัติ, LED เขียว, OLED อัปเดต | 15วินาที |

---

## 🪙 5. Token Budget Plan

เราคาดว่าจะใช้ token เท่าไหร่? (จำกัด 5 คะแนน Token Management)

| Item | จำนวน | Token | เหตุผล |
|---|---|---|---|
| | | | |
| | | | |
| | | | |
| **รวม** | | _____ | |

⚠️ **อย่าเบิกของที่ไม่ใช้** — เสีย token เปล่า

---

## 📊 6. Success Metrics

ในรอบสรุปงาน ทีมจะถือว่า prototype สำเร็จเมื่อ:

- [ ] ✅ Functionality: ________________________
- [ ] ✅ Accuracy: ______% ขึ้นไป
- [ ] ✅ Response time: ภายใน ____ms
- [ ] ✅ ทดสอบจริงในห้องแล้วทำงานได้
- [ ] ✅ User เข้าใจในการดูครั้งแรก

---

## 🚧 7. Risk & Mitigation

### Top 3 ความเสี่ยง

| ความเสี่ยง | ผลกระทบ | วิธีแก้ |
|---|---|---|
| | | |
| | | |
| | | |

ตัวอย่าง:
| ความเสี่ยง | ผลกระทบ | วิธีแก้ |
|---|---|---|
| Model accuracy drop ในสภาพแสงต่ำ | ใช้จริงไม่ได้ | เก็บข้อมูล low-light เพิ่มในรอบถัดไป |
| Servo ไม่ทำงานบน UNO Q | ไม่มี output | เตรียม Pixels เป็น backup |


## 👥 8. Team Role Assignment (รอบถัดไป)

ในรอบถัดไปแต่ละคนรับผิดชอบอะไร?

| ชื่อ | บทบาท 3H | งานหลักรอบถัดไป |
|---|---|---|
| | Hacker | Train V3 + Code integration |
| | Hipster | Form factor + UI/Output design |
| | Hustler | Documentation + Pitch deck + Idea validation |

---

## 🌟 9. Stretch Goals (ถ้ามีเวลา)

ถ้าทุกอย่างเสร็จเร็ว จะทำอะไรเพิ่ม?

- [ ] _________________
- [ ] _________________
- [ ] _________________

---

## 📤 วิธี submit

```bash
git add worksheets/W4-idea-canvas.md
git commit -m "docs: เพิ่ม Idea Canvas สำหรับรอบต่อยอด — [ชื่อ prototype]"
git push
```

---

## 💡 Tips สำหรับช่วงต่อยอด

1. **ถ้าต้องอธิบายงาน 2 นาที ทีมควรแบ่งช่วงพูดกันล่วงหน้า**
2. **ถ้าต้องโชว์สด ควรมีแผนสำรองเมื่อ internet หรือ hardware มีปัญหา**
3. **Document ทุก iteration** ใน GitHub — commit ทุก hour
4. **Token = constraint ที่สอนการตัดสินใจ** — เลือกสิ่งจำเป็น
5. **ไอเดียดี + execute ไม่จบ < ไอเดียเรียบง่าย + execute เสร็จ**
