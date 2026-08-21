# Perspectives — 2026-08-21

## 1. Google gives publishers a new way to fight AI-driven traffic losses

**อาจารย์ (มหาวิทยาลัย):** เคสนี้ควรใช้สอนเรื่อง **externality ของ AI Overview** — Google เก็บเกี่ยว traffic แต่ผลักต้นทุนความเสียหายไปที่ผู้ผลิตเนื้อหา; ตัว "เครื่องมือใหม่" คือรอยยาที่ปิดแผลใหญ่กว่า และเป็นบทเรียนคลาสสิกเรื่อง two-sided market ที่แพลตฟอร์มขยับกติกาฝ่ายเดียว.
**ผู้เชี่ยวชาญด้าน AI:** ประเด็นทางเทคนิคที่น่าจับตาคือ **surface ใหม่ที่ Google ยอมเปิดให้ publisher** (labeling / opt-out / attribution) จะแก้ query-level substitution ได้จริงหรือไม่; ถ้าเป็นแค่ retention analytics ก็คือรายงาน symptom ไม่ใช่การแบ่ง revenue.
**โปรแกรมเมอร์มืออาชีพ:** ทีมที่ทำ SEO/content tech ต้องคอย monitor **click-through rate ก่อน/หลัง AI Overview** ระดับ query segment; ถ้ามี tool ใหม่จาก Google ที่เปิด API เข้าถึง impression-vs-click data ให้เร่ง integrate เข้า analytics dashboard เพื่อสื่อสารกับฝ่ายธุรกิจว่าเสียเท่าไร.

## 2. A third of web pages published since ChatGPT's launch show signs of AI authorship, study finds

**อาจารย์ (มหาวิทยาลัย):** ตัวเลข ~33% จาก Pew Research เป็น **shift ของ information environment** ระดับที่ต้องปรับ curriculum information literacy ทั้งชั้น — เดิมสอนให้ตรวจ source credibility, ต่อไปต้องสอนให้อ่านสัญญาณ AI authorship และแยก factual claim ออกจาก stylistic filler; assignment แบบ "หา 5 บทความ" ต้องเปลี่ยนสมมติฐาน.
**ผู้เชี่ยวชาญด้าน AI:** methodology สำคัญกว่าตัวเลข — "signs of AI authorship" มี false positive สูงในเนื้อหาที่ human editor ปรับคำ + false negative ในเนื้อหาที่ human rewrite AI draft; ตัวเลข 33% ไม่ควรถูกอ่านว่า "33% เขียนด้วย AI ทั้งหมด" แต่คือ **baseline ปนเปื้อน** สำหรับการเทรน model รอบต่อไป (model collapse risk).
**โปรแกรมเมอร์มืออาชีพ:** ถ้าคุณ scrape เว็บสำหรับ training data หรือทำ RAG, ต้องคิด **provenance filter** จริงจัง — เชื่อมกับ C2PA / watermark spec ที่ Anthropic + EU AI Act เริ่มบังคับ, หรือขึ้น allowlist ของ domain ที่มี editorial process; ไม่งั้น downstream model จะเรียนจากเสียงสะท้อนของตัวเอง.

## 3. Meta AI's new Mac app wants you to talk to your apps

**อาจารย์ (มหาวิทยาลัย):** นี่คือ **ambient computing** ที่พูดถึงกันมา 15 ปีลงมาถึง desktop เต็มตัว — screen context + system-wide dictation ทำให้ boundary ระหว่าง app หายไป; ต้องสอนนักศึกษา design ให้คิด interaction model แบบ **intent → action** ไม่ใช่ **screen → click** อีกต่อไป.
**ผู้เชี่ยวชาญด้าน AI:** **Muse Spark** เป็น multimodal model ที่รับ screenshot + audio + text ในหนึ่ง context; จุดที่ต้องจับตาคือ latency + privacy — screen ทั้งจอเป็น input แปลว่า sensitive data (password prompt, private chat) ผ่านโมเดลด้วย, Meta ต้อง publish clear boundary ว่าอะไรอยู่ local อะไรส่ง cloud.
**โปรแกรมเมอร์มืออาชีพ:** ถ้าคุณทำ Mac app, เตรียม **accessibility label + a11y tree ให้สมบูรณ์** เพราะ Meta AI + Apple Intelligence + Rewind ใช้ layer นี้อ่านหน้าจอ; app ที่ไม่มี label ที่ถูกต้องจะกลายเป็น "invisible" ให้ AI agent — ลูกค้าเรียกใช้ผ่าน voice ไม่ได้ คือหายจากผลลัพธ์เดียวกับหายจาก Google search เมื่อ 15 ปีก่อน.

## 4. ChatGPT can now send texts for you with new Apple Messages plug-in

**อาจารย์ (มหาวิทยาลัย):** เคสนี้เปิดคำถามคลาสสิกเรื่อง **agency + consent ใน communication** — เมื่อ AI ส่งข้อความในนามเรา, receiver มีสิทธิ์รู้หรือไม่ว่าเป็น AI, และ speech act (คำสัญญา, คำขอโทษ) ที่ AI พิมพ์ให้มีผลผูกพันเรามากแค่ไหน; ประเด็นดีสำหรับวิชา ethics of computing.
**ผู้เชี่ยวชาญด้าน AI:** จุดเทคนิคคือ **Apple อนุญาต plug-in third party** เข้า Messages ได้จริง — ก่อนหน้านี้ Apple ปิด ecosystem นี้แน่นมาก, การเปิดให้ OpenAI แปลว่า attack surface + prompt injection risk ผ่าน incoming SMS เพิ่มขึ้นทันที; adversary ส่ง message ที่แฝง instruction ให้ ChatGPT reply กลับพร้อมข้อมูลของ user ได้ในทฤษฎี.
**โปรแกรมเมอร์มืออาชีพ:** ถ้าทีมทำ chatbot / messaging automation, review **prompt injection defense** ทันที — เพราะ user จะเริ่มคาดหวังให้ AI ตอบ SMS แทน; ควร sandbox ข้อมูลจาก incoming message ไม่ให้ auto-execute action ที่มี side effect (โอนเงิน, ยกเลิกนัด, เปิดเผยข้อมูลส่วนตัว) โดยไม่มี explicit confirm.
