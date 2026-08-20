# Perspectives — 2026-08-20

## 1. Google packs Search and Gemini with new AI study tools

**อาจารย์ (มหาวิทยาลัย):** 3D simulation + interactive visual แทน static diagram = shift ครั้งใหญ่จาก "อ่านหนังสือแล้วท่อง" ไป "manipulate object เพื่อ build intuition"; แต่ต้องระวังว่า *understanding* กับ *interactivity* ไม่ใช่สิ่งเดียวกัน — นักเรียนที่ rotate DNA structure ในหน้าจอไม่ได้แปลว่าเข้าใจ replication mechanism ถ้าไม่มีคำถามที่บังคับให้อธิบาย.
**ผู้เชี่ยวชาญด้าน AI:** feature ที่น่าจับตาที่สุดไม่ใช่ 3D visual แต่คือ **background research report** ใน Gemini Live — เป็นก้าวจาก synchronous chat ไปสู่ async agent workflow ที่ทำงานต่อได้แม้ user ปิดแชท; นี่คือ pattern เดียวกับ OpenAI Deep Research แต่ Google เอามาจับกับ voice recap ทำให้ retention loop สั้นลง.
**โปรแกรมเมอร์มืออาชีพ:** free 12 เดือนสำหรับ US college + 140 markets = distribution moat ระดับ Chromebook era; ถ้าคุณ build edtech product ต้องคิดใหม่ว่า willingness-to-pay ของนักเรียนหายไป — Google เพิ่งตั้ง floor price = 0 เป็นเวลา 1 ปี, product ของคุณต้อง justify subscription บนอะไรที่ไม่ใช่ AI generic.

## 2. Researchers say OpenAI revoked their access to limited cyber program

**อาจารย์ (มหาวิทยาลัย):** เคสสอน governance ของ dual-use technology — TAC (Trusted Access for Cyber) คือ trust-based access control ที่ต้อง verify identity + intent; เมื่อ verification pipeline พัง ผลกระทบไม่ใช่ระบบล่มธรรมดา แต่คือ *legitimate defensive researcher ถูกตัดสิทธิ์กลางงาน* ซึ่งอาจแปลว่างานวิจัย vulnerability disclosure สะดุด, malicious actor ที่ยังใช้ jailbreak ปกติได้เปรียบชั่วคราว.
**ผู้เชี่ยวชาญด้าน AI:** ข้อสังเกตทางเทคนิค: TAC = safeguard-tailored access ไม่ใช่ safeguard-removed access; ระบบเลเยอร์ trust tier (Daybreak Blue เปิด 10 ส.ค.) ต้องมี **fail-safe direction** ที่ถูก — ถ้า verify fail ระบบเลือก deny (fail-closed) ซึ่ง safe แต่ block งาน, หรือ allow (fail-open) ซึ่งเสี่ยง abuse; OpenAI เลือก fail-closed = correct default แต่ operator ต้องแจ้ง user ทันทีและมี fast-path recovery ไม่ใช่ให้ researcher ไปโพสต์ Twitter เพื่อขอความช่วยเหลือ.
**โปรแกรมเมอร์มืออาชีพ:** ถ้า production ของคุณพึ่ง TAC หรือ elevated-access tier ใด ๆ (Anthropic, Google, xAI ก็มี tier คล้ายกัน) ให้ **build fallback path** — degraded operation ผ่าน consumer-tier model + explicit warning message; อย่า assume elevated tier จะเสถียร 100%, especially ในช่วง 3-6 เดือนแรกของ new tier rollout.

## 3. TerraPower's nuclear reactor has a secret weapon for powering AI data centers

**อาจารย์ (มหาวิทยาลัย):** เคสสอน **thermodynamic storage = economic multiplier** — molten sodium reservoir เปลี่ยน baseload nuclear ให้เป็น dispatchable power ได้; แนวคิดเดียวกับ concentrated solar + molten salt แต่ประยุกต์กับ nuclear; นี่คือจุดที่ engineering physics มาจบที่ economic viability (amortize capex ต่อชั่วโมงเดินเครื่อง).
**ผู้เชี่ยวชาญด้าน AI:** data-center load ของ frontier model training มี **duty cycle ไม่คงที่** — training run 3-6 สัปดาห์ + gaps ระหว่าง experiments + spike ตอน RLHF; TerraPower ตอบโจทย์นี้เพราะ reactor ไม่ต้อง ramp (ซึ่ง nuclear ทำไม่ดี) แต่ให้ molten salt เป็นบัฟเฟอร์; ถ้าใช้ได้จริง 2027-2028 นี่ decouple GPU scaling จาก grid constraint ในหลายรัฐ.
**โปรแกรมเมอร์มืออาชีพ:** ระยะสั้นไม่กระทบ workflow ประจำวัน — แต่ถ้าทีมต้อง commit multi-year training compute budget, การเลือก data-center partner ที่มี PPA กับ TerraPower/Kairos/X-Energy จะให้ **cost predictability 10-year** แทน 2-year natural gas hedge; carbon-free footprint ก็เป็น input ของ enterprise procurement policy ที่ EU + Big Tech customer เริ่มบังคับ.

## 4. Calendly throws its hat into meeting note-taker circus

**อาจารย์ (มหาวิทยาลัย):** ตำราเรียน adjacency expansion — Calendly (scheduling) → Notetaker (post-meeting workflow) เพราะเข้าใจ **calendar as system of record**; แต่ competitor ทั้งหมด (Granola, Fireflies, Otter, Notion, ClickUp) attack ปัญหาเดียวกันจากต่างมุม; เคสสอน positioning: differentiation ไม่ใช่ feature list แต่คือ "which upstream event do you own?" — Calendly ตอบว่า "การนัดหมาย" ซึ่ง unique.
**ผู้เชี่ยวชาญด้าน AI:** เทคนิคที่น่าจับตา = **cross-meeting context** — Callie ดึง context จาก prior meetings ผ่าน scheduling metadata; ถ้าออกแบบดี = memory graph ที่ scoped ระดับ user + calendar event ID + participant, ไม่ใช่ raw transcript; ปัญหา privacy จะเข้ม (คนเข้าประชุมไม่ได้ยอมให้ AI จำ) และ classic RAG failure mode (hallucinated "as we discussed last week…") จะสูง ถ้าไม่ track provenance ต่อ meeting.
**โปรแกรมเมอร์มืออาชีพ:** ถ้าองค์กรใช้ Calendly อยู่แล้ว = trigger point ให้ทบทวน **AI notetaker policy** ก่อน rollout — recording consent, transcript retention, cross-tenant data leakage, integration กับ Slack/Notion; อย่าให้ทีม sales adopt แบบ shadow IT; feature ที่จะ tie-in สำเร็จ = Google Meet/Teams calendar events อยู่แล้ว, ไม่ต้อง onboard user ใหม่.

## 5. Rillet raises $100M Series C at $1B valuation — 2 years after emerging from stealth

**อาจารย์ (มหาวิทยาลัย):** เคสสอน **AI-native vertical SaaS economics** — Rillet doubled ARR ใน 3 เดือน + 3 rounds ใน 14 เดือน = pattern ของ vertical AI ที่ **replace back-office labor** (accounting close จากสัปดาห์ → hours); ควร cross-reference กับ Harvey (legal), Abridge (medical scribe), Sierra (customer support) ที่ growth curve ใกล้เคียง; ทฤษฎีว่า "AI-native ERP" มี moat จาก workflow lock-in + data volume.
**ผู้เชี่ยวชาญด้าน AI:** ยังไม่มี model breakthrough ในข่าวนี้ แต่ที่น่าสังเกตคือ Rillet ใช้ **continuous data ingestion** จาก source system (Salesforce, Brex) แทน batch-import แบบ ERP เดิม; นี่คือ pattern **event-driven AI ledger** ที่ต่างจาก SAP/NetSuite เชิงสถาปัตยกรรมพื้นฐาน; auditability ยังเป็น open question — ถ้า AI post-adjustment เข้า ledger, ต้องมี explanation trace ที่ audit firm ยอมรับ.
**โปรแกรมเมอร์มืออาชีพ:** ถ้าเขียน integration ให้ finance stack, cost-basis สำหรับ competitor ของ Rillet ทะยานขึ้น — funding round ระดับ $100M แปลว่า **enterprise sales ขยายไปหา F500** และ integration standard จะถูก Rillet setup ก่อน; startup ที่จะ compete ควรเน้น **niche vertical** (SaaS revenue recognition, e-commerce inventory accounting, non-profit fund accounting) แทนแข่ง general ledger head-on; ทีมภายในบริษัทที่ evaluate ERP tool ควร pilot Rillet + incumbent ให้ 2 quarters ก่อนตัดสินใจ.
