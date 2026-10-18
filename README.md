# สมุดจองล็อค

เว็บหน้าเดียวสำหรับบันทึกการจองล็อคขายของตามตลาดและงานเทศกาล
(งาน, โซน, เลขล็อค, ราคาปิดประมูล, ขายอะไร, ติดต่อ, สถานะ) หลายคนกรอกพร้อมกันได้ผ่าน Firebase

## ตั้งค่า Firebase (ครั้งเดียว)
1. https://console.firebase.google.com → Add project
2. Build → Authentication → Sign-in method → เปิด **Anonymous**
3. Build → Firestore Database → Create database (โหมด production)
4. แท็บ Rules ของ Firestore → วางเนื้อหาจาก `firestore.rules` → Publish
5. Project settings → Your apps → เพิ่ม Web app → คัดลอกค่า config ใส่ใน `firebase-config.js`
6. Authentication → Settings → Authorized domains → เพิ่มโดเมน GitHub Pages ของคุณ (`ชื่อ.github.io`)

## เปิดใช้งาน
- GitHub: Settings → Pages → Deploy from branch → main / root
- ถ้ายังไม่ใส่ค่าใน `firebase-config.js` เว็บจะเก็บข้อมูลในเบราว์เซอร์เครื่องนั้นอย่างเดียว

## หมายเหตุความปลอดภัย
Rules ชุดนี้ให้ทุกคนที่เปิดเว็บเขียนข้อมูลได้ เหมาะกับลิงก์ที่แชร์กันในทีมเล็กๆ
ถ้าต้องการจำกัดเฉพาะบางคน ให้เปลี่ยนเป็นล็อกอินด้วยอีเมลหรือ Google แล้วกำหนดอีเมลที่อนุญาตใน Rules
