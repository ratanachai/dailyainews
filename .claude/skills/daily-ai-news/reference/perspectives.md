# Perspectives — 2026-07-26

## 1. Librarians hosting viral "Avoiding AI" workshops

**อาจารย์ (มหาวิทยาลัย):** เคสนี้ให้นักเรียนได้เห็นว่าเทคโนโลยีที่ถูก "ผลักเป็น default" (Apple Intelligence, Gemini) กระตุ้น backlash ระดับ grassroots ผ่านสถาบันสาธารณะแบบห้องสมุด — ใช้เป็นวัสดุคลาส digital rights / consent-based design ได้ทันที เทียบกับกรณี GDPR opt-in ในยุโรป.
**ผู้เชี่ยวชาญด้าน AI:** สัญญาณสำคัญไม่ใช่คนกลุ่มนี้ "ไม่ใช้ AI" แต่คือ "ไม่ยอมรับ AI ที่ opt-out ไม่ได้" — ต่อไป vendor ต้องออกแบบ AI toggle ที่ granular ระดับ per-app ไม่ใช่ระดับ OS-wide switch เดียว มิเช่นนั้น distrust จะขยายวงและกินตลาด long-tail user.
**โปรแกรมเมอร์มืออาชีพ:** ถ้าคุณ ship product ที่มี AI feature ให้ **default off + explicit opt-in** สำหรับผู้ใช้ใหม่ และเก็บ telemetry แยกกันระหว่าง user ที่เปิด vs ปิด — เตรียมพร้อมสำหรับ regulatory ที่มีแนวโน้มจะบังคับ opt-in ในหลาย jurisdiction ปี 2027; และเวลาออก UI ให้เขียน copy ที่บอก **ทั้ง benefit และข้อมูลที่จะถูกส่งไป** ไม่ใช่แค่ "Enable AI".

## 2. Power line failure exposes AI data center grid instability

**อาจารย์ (มหาวิทยาลัย):** เปิดคลาส energy systems + AI infrastructure — เหตุการณ์นี้เป็น real-world case ของ "correlated failure" ที่หาได้ยากในตำรา; ให้ debate ว่า **ทำไม 3 GW ถึงตัดพร้อมกัน** (protective relay setting ที่ conservative เกินไปหรือเปล่า) และเสนอมาตรการเชิง system engineering.
**ผู้เชี่ยวชาญด้าน AI:** ประเด็นน่าจับตาไม่ใช่ AI training load (predictable, schedulable) แต่คือ inference load ที่ **spiky และ centralized** — inference cluster ตอบ user request แบบ real-time จึงถูก set ให้ตัดโหลดทันทีเมื่อ voltage แกว่ง เพื่อป้องกัน hardware; ยิ่ง fleet ใหญ่ ยิ่ง contagion เมื่อ trip พร้อมกัน. ต่อไปต้องมี **grid-forming inverter + BESS layer** ที่ absorb transient แทนตัด load.
**โปรแกรมเมอร์มืออาชีพ:** ถ้าระบบคุณพึ่ง 3rd-party AI API — เตรียม **circuit breaker + degraded-mode fallback** ให้ user ต่อไปได้เมื่อ upstream inference cluster ล่ม; อย่าคิดว่า AI provider outage เป็น edge case อีกต่อไป — grid-level correlated failure เป็น failure mode ใหม่ที่ SLA ของ hyperscaler ยังไม่ครอบคลุมชัดเจน.
