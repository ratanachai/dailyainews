# Perspectives — 2026-08-06

## 1. Jeff Dean + Google veterans leave to launch Discovery Loop

**อาจารย์ (มหาวิทยาลัย):** เคสนี้เป็น pivot point ของประวัติศาสตร์ Google Research — CS legend ที่อยู่ 27 ปี (คนที่วางรากฐาน MapReduce, TensorFlow, Google Brain) เลือกออกในจังหวะที่ Alphabet ยังเป็น founding investor พร้อม compute — บ่งชี้ว่า "org gravity" ของบริษัทใหญ่บีบให้ deep research ต้องแยกร่างเป็น public benefit corp จึงจะเดินหน้าเร็วได้
**ผู้เชี่ยวชาญด้าน AI:** thesis "automating scientific discovery" คือ AI-for-science ระลอกใหม่ที่ต่อยอด AlphaFold — Discovery Loop วางแผนรัน "high-octane algorithms" ยิงการทดลองพันๆ ตัวขนานกัน ตั้งเป้า ML research + hardware design + drug discovery + clean energy; ที่ต้องจับตาคือ Vinyals (จาก DeepMind) นำ RL/sequence expertise + Le นำ AutoML lineage
**โปรแกรมเมอร์มืออาชีพ:** ผลกระทบระยะสั้นต่อ engineer ส่วนใหญ่คือ "ไม่มีอะไรเปลี่ยน" — Google APIs/Gemini/TensorFlow เดินต่อ; แต่ระยะกลางถ้า Discovery Loop ปล่อย tool อัตโนมัติ ML experiment ที่ใช้งานได้จริง ก็จะกระทบ MLOps stack ที่เราวางกันทุกวันนี้อย่างมีนัย — เก็บชื่อบริษัทไว้ในเรดาร์

## 2. Anthropic builds custom silicon team

**อาจารย์ (มหาวิทยาลัย):** เคสนี้สอนวิชา vertical integration ในยุค AI ได้ชัดเจน — Anthropic เดินตาม playbook Google TPU / Apple Silicon / Tesla Dojo คือ "ถ้าจ่ายให้ Nvidia ปีละหมื่นล้าน คุณเริ่มมี business case สร้างเองแล้ว"; นักศึกษาควรเข้าใจว่า co-design hardware + model เป็น multi-year commitment ที่ทดแทน off-the-shelf ไม่ได้ง่ายๆ ระยะ 2-3 ปีแรก
**ผู้เชี่ยวชาญด้าน AI:** เป้า 50% inference cost reduction คือ frontier-lab economic threshold ที่ทำให้ chip project คุ้ม — Clive Chan มาจาก Tesla Dojo + OpenAI chip team บ่งชี้ว่า Anthropic ต้องการ full-stack expert ที่รู้ทั้ง compiler และ NoC; การประกาศไม่ตัด Nvidia/AMD/AWS/Google ทิ้งคือ signal ว่าเป็น additive strategy ไม่ใช่ replacement play
**โปรแกรมเมอร์มืออาชีพ:** ถ้าคุณ build บน Claude API ระยะ 12-18 เดือนแรกไม่กระทบ (custom chip โครงการแบบนี้ใช้เวลา 3+ ปีถึง production); ระยะ 2-3 ปีข้างหน้าถ้า inference cost ลง 50% จริง price/token น่าจะปรับลงตาม + rate limit น่าจะผ่อน — วางสถาปัตยกรรมให้ portable ระหว่าง provider ไว้ อย่า lock ตัวเองกับ backend เดียว

## 3. Meta ships Muse Code (beta) — coding agent สู้ Claude Code + Codex

**อาจารย์ (มหาวิทยาลัย):** เคสนี้เห็น architecture pattern "sub-agent fan-out in isolated worktrees" ที่ค่อยๆ กลายเป็น standard สำหรับ agent เขียนโค้ดขนาดใหญ่ — เป็นตัวอย่างที่ดีสำหรับนักศึกษาวิชา distributed systems + concurrent programming ว่า agent ก็ต้องแก้ปัญหา partitioning, isolation, merge conflict เหมือน CI pipeline
**ผู้เชี่ยวชาญด้าน AI:** Muse Code ขับด้วย Muse Spark 1.2 (in-house model) + event log สำหรับ resume-after-crash — แสดงว่า Meta ตั้งใจให้เป็น production-grade agent ไม่ใช่ demo; ที่ค้างคือ **ยังไม่ประกาศ benchmark เทียบกับ Claude Code/Codex** ในทาง SWE-bench หรือ Aider polyglot — ต้องรอผลจริงก่อนสรุปประสิทธิภาพ
**โปรแกรมเมอร์มืออาชีพ:** อีก terminal agent หนึ่งใน macOS/Linux (ไม่มี GUI เฉพาะ) — install ด้วย command เดียว ลองได้ทันที; ก่อน commit เปลี่ยน workflow ให้ทีม รอสัก 4-6 สัปดาห์ให้ community เทียบ real-world quality กับ Claude Code + Codex + Cursor Agent; sub-agent-in-worktree pattern ที่ Muse Code ใช้ = แนวเดียวกับที่ agent framework ปัจจุบันเริ่มมาตรฐาน ทำให้ mental model โยกได้

## 4. OpenAI + Statsig ยอม DOJ ในคดี PERM/green-card — จ่าย $3.2M + oversight 3 ปี

**อาจารย์ (มหาวิทยาลัย):** เคสนี้เข้าใน syllabus employment law + immigration policy ได้เลย — DOJ ตีความ Immigration and Nationality Act ว่า PERM process ที่ปิดกั้น US applicant (ผ่านการโฆษณา late-night radio, บังคับ paper application) = discrimination; เป็น warning shot ว่ารัฐบาลกำลัง scrutiny tech company ที่ pipe ผู้ชำนาญต่างชาติเข้ามาแบบ opaque
**ผู้เชี่ยวชาญด้าน AI:** signal ทาง policy คือ frontier lab กำลังกลายเป็น target compliance ที่ regulator หลายฝ่าย (DOJ, FTC, state AGs) มอง — settlement นี้ตั้ง **oversight เชิงระบบ 3 ปี** พร้อม semiannual report (จำนวน application, จำนวน US citizen ที่ interview ฯลฯ) ซึ่งจะ leak ข้อมูล internal hiring pattern เข้าสู่ public record ทางอ้อม
**โปรแกรมเมอร์มืออาชีพ:** ถ้าคุณเป็น engineer ต่างชาติที่วางแผนไป frontier lab US — timeline PERM อาจช้าลงเพราะ lab ต้อง comply กับ transparent posting + electronic-only apply; ถ้าคุณเป็น US-based engineer — PERM job ในบริษัทเหล่านี้จะ visible บน career site ให้สมัครได้จริง; ทั้งสองฝ่ายควรอ่าน settlement condition ก่อนตัดสินใจ

## 5. MacPaw + Liquid AI — on-device inference stack สำหรับ Mac (LFMs + Elix + Mnemos)

**อาจารย์ (มหาวิทยาลัย):** ใช้เคสนี้สอน trade-off privacy vs. capability — on-device inference ให้ privacy + offline + latency ดี แต่แลกกับ context window เล็ก + model ขนาดจำกัดโดย SoC; MacPaw + Liquid AI เดินตาม vision "personal AI runs on personal computer" ที่ Apple Intelligence เปิดทางไว้แล้ว
**ผู้เชี่ยวชาญด้าน AI:** Liquid Foundation Models (LFMs) — architecture ที่ Liquid AI พูดว่าเบาและ efficient กว่า transformer แบบเดิม — ถูกออกแบบเฉพาะ macOS runtime; ประเด็นน่าสนใจคือ Elix (inference) + Mnemos (memory) ของ MacPaw ต้อง integrate กับ Apple's Neural Engine + Metal อย่างไร ใน environment ที่ Apple ไม่เปิด low-level API มากนัก
**โปรแกรมเมอร์มืออาชีพ:** dev ที่ build บน Setapp / macOS app store ควรจับตา SDK ที่ MacPaw จะ expose — ถ้า architecture ล็อกได้ปีนี้ dev คนอื่นจะเข้าถึง local inference โดยไม่ต้อง bundle model เอง; use case ที่ชนะกว่า cloud คือ: personal data workflow (email, note, calendar) + offline-first tool + low-latency assistant — ควรระวังเทียบผล quality กับ cloud model ก่อน ship
