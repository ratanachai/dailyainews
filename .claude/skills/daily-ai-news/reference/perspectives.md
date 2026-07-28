# Perspectives — 2026-07-28

## 1. Nvidia $5B in Safe Superintelligence

**อาจารย์ (มหาวิทยาลัย):** เคสนี้เหมาะเปิดคลาส economics of AI research — ทุน + hardware access คือ moat จริง; SSI เงียบมา 2 ปีเพราะรอ compute ระดับ order of magnitude ก่อนจะประกาศงาน สอน "compute-first vs paper-first" research culture ให้ชัด
**ผู้เชี่ยวชาญด้าน AI:** Vera Rubin + compute เพิ่ม 10× บอกใบ้ว่า SSI ใกล้เข้าสู่ training run ระดับ frontier แล้ว; ทีมเน้น "aligned superintelligence" แบบ single-shot (ไม่ออก product ระหว่างทาง) ทำให้ result แรกจะน่าจับตากว่าปกติเพราะไม่มี intermediate signal ให้ประเมิน
**โปรแกรมเมอร์มืออาชีพ:** ปัจจุบันไม่มี SSI API — ไม่ต้องรีบวางแผน integration แต่การที่ Nvidia ยอมใส่ $5B ในสตาร์ทอัพที่ยังไม่มีรายได้ ตอกย้ำว่า **compute contracts (multi-year Nvidia reservations)** กำลังกลายเป็น business moat ที่จับต้องได้กว่าโมเดลตัวเอง

## 2. Microsoft Project Perception (cybersecurity AI)

**อาจารย์ (มหาวิทยาลัย):** ใช้ Perception เปิดคลาส agentic architecture — red / blue / green team คือ pattern ที่สอนจริงได้ตั้งแต่ปริญญาตรี; ให้นักเรียน design agent handoff protocol กับ blast-radius control เอง
**ผู้เชี่ยวชาญด้าน AI:** MAI-Cyber-1-Flash ทำคะแนน 96% บน CyberGym ที่ต้นทุนครึ่งเดียวของ frontier general model เป็นหลักฐานว่า **specialized code-tuned model ยังชนะ general model ในโดเมนแคบ** — คำถามคือ false-positive rate ที่ Microsoft ไม่ได้ประกาศ; benchmark ดีไม่ได้แปลว่า production ready
**โปรแกรมเมอร์มืออาชีพ:** ถ้าใช้ Defender / Sentinel อยู่แล้ว preview 3 ส.ค. คุ้มลอง — แต่ **agent ที่ execute remediation ต้องมี rate limit + full audit log + kill switch** ก่อนเปิด production; อย่าให้ agent ที่ผิดพลาด rollback config ทั้ง fleet โดยไม่มีคนขวาง

## 3. Claude shared chats indexed on Google

**อาจารย์ (มหาวิทยาลัย):** intro to threat modeling ที่ perfect — สอนความต่างระหว่าง **confidentiality (เข้ารหัส) vs obscurity (unlisted URL) vs privacy (ไม่ให้ index)** โดยใช้เคสนี้เป็นตัวอย่างว่า "share link" ในผลิตภัณฑ์ LLM ≠ "private link"
**ผู้เชี่ยวชาญด้าน AI:** สาเหตุคือ **missing `noindex` meta tag** บน share endpoint — bug คลาส OWASP privacy ระดับ 101 ที่ frontier lab ก็ยังพลาดได้ ประเด็นลึกกว่าคือ share feature ของ LLM product ทุกเจ้ามี attack surface เดียวกัน; คาดว่า OpenAI / Google / Grok จะรีบ audit endpoint ของตัวเองในสัปดาห์นี้
**โปรแกรมเมอร์มืออาชีพ:** วันนี้เลย — audit ผลิตภัณฑ์ตัวเอง: (1) `<meta name="robots" content="noindex,nofollow">` บนทุก public share page, (2) `X-Robots-Tag: noindex` header, (3) `robots.txt` disallow, (4) สมมติว่า **URL ใดก็ตามที่หลุดออกไปจะถูก index** — ออกแบบให้ share link มี expiry + revoke ได้

## 4. Nadella multi-vendor AI warning

**อาจารย์ (มหาวิทยาลัย):** เคสสอน rhetorical framing — Microsoft ลงทุนใน Anthropic และ OpenAI แล้วออกมาเตือนไม่ให้พึ่ง single provider; ให้นักเรียนแยก **sales pitch** ออกจาก **underlying architectural advice** ทั้งสองอย่างมีความจริงคนละส่วน
**ผู้เชี่ยวชาญด้าน AI:** "AI gateway" pattern ที่ Nadella อธิบาย (แยก prompt / context / memory ออกจากโมเดล) เป็น architecture ที่ถูกต้อง — ไม่ใช่ของใหม่ (LiteLLM, Portkey, Kong AI Gateway ทำได้ตั้งแต่ปี 2024) แต่คำเตือนจาก CEO Microsoft ทำให้ enterprise procurement team เริ่มถามถึง gateway strategy อย่างจริงจัง
**โปรแกรมเมอร์มืออาชีพ:** ถ้าโค้ดยัง `openai_client = OpenAI(...)` แข็ง refactor ให้ไปผ่าน gateway ในสไปรนต์นี้ — ต้นทุน ~1 sprint, ต้นทุนที่ไม่ทำคือ **provider lock-in + ต่อรอง pricing ไม่ได้ + สลับได้ช้าเมื่อ provider เปลี่ยน policy / ถูก sanction / ล่ม**

## 5. Nvidia $750B circular financing fears

**อาจารย์ (มหาวิทยาลัย):** case study ทันสมัยสำหรับคลาส finance — เปรียบเทียบ vendor financing loop 2026 (NVDA ↔ OpenAI ↔ SoftBank ↔ SK) กับ dotcom-era (Lucent ↔ CLECs, Cisco ↔ Nortel); คำถาม pedagogy คือ **structural similarity vs structural difference**
**ผู้เชี่ยวชาญด้าน AI:** ถ้า node ใดใน loop สะดุด (OpenAI ชะลอ ค่า inference, SK reduce commit, ราคา memory ตก) impact จะกระจายเป็น **compute supply shock** ที่กระทบทั้ง industry — capex ที่ประกาศไว้ยังไม่แปลว่า capacity จะ online ตามแผน
**โปรแกรมเมอร์มืออาชีพ:** วางงบเผื่อ **GPU shortage / price spike ในไตรมาส 2027 H1** — ถ้า loop ตึงตัว, hyperscaler จะดึง capacity ให้ enterprise ตัวเองก่อน SME; keep inference stack **portable ระหว่าง cloud + on-prem** (vLLM / TGI / SGLang) เพื่อไม่ให้ business หยุดถ้า provider หลัก throttle
