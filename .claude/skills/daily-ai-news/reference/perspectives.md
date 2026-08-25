# Perspectives — 2026-08-25

## 1. OpenAI is building an AI agent for everything — will everyone use them?

**อาจารย์ (มหาวิทยาลัย):** สอนได้ในวิชา HCI / adoption research ว่าปัญหาของ general-purpose agent ไม่ใช่ capability แต่คือ **trust gradient** — ผู้ใช้ยินดีให้ agent สรุปเอกสาร แต่ไม่ยอมให้จองตั๋วเครื่องบิน; นักศึกษาควรอ่านคู่กับ Amodei's "crisis of trust" thesis เพื่อเข้าใจว่า deployment gap มาจาก **institutional distrust** ไม่ใช่ latency หรือ accuracy.
**ผู้เชี่ยวชาญด้าน AI:** ประเด็นจริงคือ **evaluation ยัง underdeveloped** สำหรับ long-horizon agent — benchmark ที่มีอยู่ (SWE-bench, τ-bench, WebArena) วัด task completion แต่ไม่วัด **cost of an incorrect action** ที่ agent เพิ่งทำแทนคุณ (โอนเงินผิดบัญชี, ส่ง email ผิดคน); ต้องออกแบบ agent เป็น **reversible-by-default** และ **confirm-before-commit** สำหรับ side-effect ที่ irreversible.
**โปรแกรมเมอร์มืออาชีพ:** สำหรับทีมที่จะ integrate OpenAI agent ให้ scope ให้แคบก่อน (single tool, single scope, human-in-loop) แล้วค่อยขยาย; อย่าเริ่มด้วย "agent สำหรับทุกอย่าง" เพราะ debugging pipeline ที่ agent เรียก 30 tool กลายเป็นฝันร้าย — เริ่มด้วย 2-3 tools ที่ readonly, เพิ่ม write tool เฉพาะที่มี undo และ log request/response ทุก call สำหรับ post-mortem.

## 2. XPeng Robot Unit to Raise $900M — IRON humanoid targets end-2026 mass production

**อาจารย์ (มหาวิทยาลัย):** เคสสอน embodied AI + industrial policy ที่ดีมาก — XPeng ระดม $900M ที่ $6.3B valuation จาก IDG + Tencent + Alibaba คือสัญญาณว่า **จีนกำลังรวม supply chain humanoid ในประเทศ** (EV maker + chip + cloud + investor); นักศึกษาควรเปรียบเทียบกับโมเดล US (Figure + OpenAI, Boston Dynamics + Hyundai) เพื่อเห็นว่า vertical integration ต่างกันแค่ไหน.
**ผู้เชี่ยวชาญด้าน AI:** IRON spec — 76 DoF ทั้งตัว + 21 DoF ต่อมือ + 3 Turing AI chip ให้ 2,250 TOPS — คือสัญญาณว่า **on-device inference สำหรับ humanoid ต้องอยู่ระดับ 2 kTOPS ขึ้นไป** เพื่อ handle vision + planning + control loop ใน real-time; **21 DoF ต่อมือ** ใกล้เคียง human hand (ประมาณ 27 DoF) เพียงพอสำหรับ dexterous manipulation แต่ยังต้อง prove ใน long-horizon task (ล้างจาน 30 นาทีจบไหม vs สาธิต 30 วินาที).
**โปรแกรมเมอร์มืออาชีพ:** ถ้าทีม robotics ในไทยจะรับ IRON มา integrate ให้เตรียม 2 เรื่อง: (1) **safety envelope** ต้องออกแบบใน software layer ตัวเอง เพราะ vendor SDK จะ default open — humanoid ตกใส่คนต่างจาก robot arm ตกใส่เครื่องจักร; (2) **teleoperation fallback** เพราะ autonomy ระดับ demo ≠ autonomy ระดับ production, เตรียม remote-pilot กด takeover ทุก 30 นาทีในช่วงแรก แล้วค่อยลด frequency ตาม fault log.

## 3. NVIDIA ร่วมลงทุนใน Perplexity ที่มูลค่า >$30B (Blognone/The Information)

**อาจารย์ (มหาวิทยาลัย):** สอนได้ใน corporate strategy — NVIDIA ทำตัวเป็น **"landlord ของ AI compute"** ที่ลงทุนใน demand side (Perplexity, OpenAI, xAI) เพื่อ **lock GPU consumption** ที่ตัวเองผลิต; นักศึกษาต้องเข้าใจว่านี่คือ **circular capital** — เงินที่ Perplexity ได้ ~30-60% ไปเป็นค่า GPU rental กลับสู่ Nvidia — ประเด็น anti-trust ในสหรัฐจะเริ่มไล่มาที่ pattern นี้.
**ผู้เชี่ยวชาญด้าน AI:** valuation >$30B บน ARR $750M = **~40x ARR multiple** ซึ่งสูงกว่า SaaS ทั่วไป (10-15x) — market pricing Perplexity เป็น **infrastructure play** ไม่ใช่ end-user app; ตัวเลข $750M ARR ที่โตจาก <$250M ใน 8 เดือนสะท้อนว่า **Perplexity Computer (agent สำหรับ professional workflow)** เป็นตัว drive revenue ไม่ใช่ตัว search consumer; consumer search ยังแข่งกับ ChatGPT + Gemini ได้ยาก.
**โปรแกรมเมอร์มืออาชีพ:** สำหรับทีมที่ใช้ Perplexity API ใน production ให้ระวัง **pricing pressure** ที่จะมาหลัง fundraise ปิด — vendor ที่เพิ่งได้เงินก้อนใหญ่มัก raise price ใน 3-6 เดือน; ถ้า workload dependency สูงให้ negotiate multi-year contract ก่อน round ปิด, หรือเตรียม fallback ไปหา self-host (Perplexity เพิ่งเปิด open-source บางส่วน) หรือ Kagi/Exa สำหรับ programmatic search.
