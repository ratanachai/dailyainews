# Perspectives — 2026-08-10

## 1. China Bets on AI Stocks as It Races Against US for Chip Dominance (Bloomberg)

**อาจารย์ (มหาวิทยาลัย):** ให้นักศึกษาเปรียบเทียบ CXMT กับ TSMC / SK Hynix / Samsung — market cap อาจสูงลิบเพราะ *scarcity premium* จากการที่จีนต้อง self-sufficient ในสภาวะ export control ไม่ใช่เพราะ fundamentals เหนือกว่า; ใช้สอน bubble-vs-fundamental analysis + geoeconomics ของ semi supply chain.
**ผู้เชี่ยวชาญด้าน AI:** memory bandwidth คือ bottleneck ตัวจริงของ inference สมัยใหม่ (HBM สำหรับ frontier model); การที่ CXMT พุ่งแรงสะท้อนว่า capital market ให้ราคา "compute-adjacent" มากกว่า model layer แล้ว — จับตา DRAM/HBM pricing และผลต่อ inference cost per token ในครึ่งหลังของปี.
**โปรแกรมเมอร์มืออาชีพ:** ถ้า supply chip จีนใช้ในประเทศเป็นหลัก inference cost บน US cloud อาจไม่ลด — แต่ถ้าคุณ deploy ในเอเชียหรือใช้ Chinese vendor (Alibaba, Tencent, DeepSeek) จะเห็น token price ลงเร็วกว่า; วางแผน multi-region เตรียมย้ายบางส่วน workload ตาม cost curve.

## 2. Moore Threads Plans Hong Kong Listing (Bloomberg)

**อาจารย์ (มหาวิทยาลัย):** case study ของ dual-listing strategy — Shanghai (A-share) เก็บ retail-heavy domestic demand, Hong Kong (H-share) เปิดประตู foreign capital + คน; ให้ผู้เรียนวิเคราะห์ว่าทำไม H1 revenue โต 147% แต่ยังขาดทุน 11.6 ล้านหยวน — cost of scaling ในธุรกิจชิปคือของจริง.
**ผู้เชี่ยวชาญด้าน AI:** Moore Threads เป็นหนึ่งใน "Chinese Nvidia-alternative" น้อยรายที่มี GPU stack ครบชั้น (compiler / driver / library) — การรัดกุมเข้า HK ช่วย hire talent ต่างชาติซึ่งเป็น bottleneck ของทีม chip จีนทุกราย; ถ้า Moore Threads ปิด gap ด้าน CUDA-equivalent stack ได้ ตลาด GPU sub-frontier ในเอเชียจะเปลี่ยนโครงสร้าง.
**โปรแกรมเมอร์มืออาชีพ:** อย่ารีบพอร์ต CUDA code ไป MT stack — ecosystem ยังบาง; แต่ควรออกแบบ inference layer ให้ vendor-agnostic (PyTorch + ONNX + TensorRT/Triton แบบ swap-able) เพื่อไม่ผูก Nvidia ตลอดไป; สำหรับทีมในไทยที่มี latency-sensitive workload — จับตา MT/Cambricon/Huawei Ascend เป็น option ในปี 2027.

## 3. McKinsey CFO Warns on AI Costs (Bloomberg)

**อาจารย์ (มหาวิทยาลัย):** เอาคำว่า "shiniest thing" มาสอน hype cycle vs. mature adoption — ปี 2023-2024 องค์กรซื้อทุกอย่างที่มีคำว่า AI, ปี 2026 CFO เริ่มถาม unit economics; นี่คือช่วง trough of disillusionment ที่ Gartner ทำนายไว้ กำลังเกิดกับ enterprise AI budget จริง.
**ผู้เชี่ยวชาญด้าน AI:** สัญญาณสำคัญ — McKinsey (บริษัทที่ *ขาย* AI advisory) บอกลูกค้าเองว่า "หยุดไล่ของใหม่"; ความหมายคือ ROI ของ AI project ในองค์กรกำลังถูกเข้มงวดขึ้น, และ token cost management (context caching, prompt compression, model routing) กลายเป็น first-class discipline ไม่ใช่ nice-to-have.
**โปรแกรมเมอร์มืออาชีพ:** เตรียมโดน CFO ถาม cost-per-request ของทุก AI feature; ติดตั้ง observability สำหรับ token spend ต่อ user / ต่อ endpoint / ต่อ team ตั้งแต่วันนี้ (LangSmith, Helicone, Langfuse หรือ home-grown); ใช้ smaller/cheaper model สำหรับ routing แล้วเรียก frontier model เฉพาะ hard case — pattern นี้ลด cost ได้ 60-80% โดยไม่กระทบ user experience.

## 4. Zoox Robotaxi Charges from Aug 10 + Uber AV Empire (TechCrunch)

**อาจารย์ (มหาวิทยาลัย):** ใช้เป็น case study ของ "regulatory sandbox" — NHTSA ให้ exemption กับ Zoox เพราะรถไม่มี pedal/steering wheel; ให้เปรียบเทียบกับกรอบกฎหมายรถอัตโนมัติในไทย/สิงคโปร์/สหภาพยุโรป และวิเคราะห์ว่ากติกาแบบไหนทำให้ real-world AI ทดสอบได้ (US = exemption per case) vs. ล่าช้า (EU = prescriptive rules).
**ผู้เชี่ยวชาญด้าน AI:** paid ride คือ inflection point จริง — AV ไม่ใช่ demo แล้ว, กลายเป็น production system ที่มี SLA และ liability; จับ Waymo/Zoox/Uber-Cruise-Motional เป็น living dataset ของ real-world AI safety — incident rate ต่อล้านไมล์จะกลายเป็น benchmark ที่ regulator ใช้ตัดสินใจการขยายเมืองอื่นและประเทศอื่น.
**โปรแกรมเมอร์มืออาชีพ:** สำหรับทีม ML/perception ในไทย — ecosystem ที่โตขึ้นแปลว่า tooling (simulation, HD map, edge deployment framework) จะเป็น open-source / commodified มากขึ้นในอีก 1-2 ปี; ถ้าอยากเข้าสาย AV/robotics ตอนนี้คือช่วงเรียนรู้ ROS 2 + Foundation Pose Models + occupancy networks ก่อน barrier to entry จะสูงกว่านี้เมื่อ regulation ตามทัน.

## 5. Anthropic ตั้งทีมออกแบบชิปคัสตอมสำหรับ Claude (Blognone)

**อาจารย์ (มหาวิทยาลัย):** case study ที่สมบูรณ์แบบของ "vertical integration ในยุค AI" — เหมือน Apple ที่ทำชิป M-series เอง เพื่อคุม performance / cost / supply; ใช้สอนว่าทำไม frontier lab ทุกเจ้า (OpenAI + Broadcom, Google TPU, Meta MTIA, Anthropic) เดินสายเดียวกัน — เพราะ dependency บน Nvidia คือ business risk เชิงยุทธศาสตร์ไม่ใช่แค่ต้นทุน.
**ผู้เชี่ยวชาญด้าน AI:** signal สำคัญคือ Anthropic *เพิ่งเริ่มรับ engineer* ตอนนี้ — แปลว่าชิปแรกอาจใช้เวลา 2-3 ปีถึงจะ tape out; ในระหว่างนั้น Anthropic ยังพึ่ง TPU + Trainium + H100/Blackwell; ถามที่ต้องจับตาคือ software stack — Anthropic จะออกแบบชิปที่ optimize สำหรับ Claude architecture เฉพาะ (แบบ TPU สำหรับ Transformer) หรือ general-purpose accelerator?
**โปรแกรมเมอร์มืออาชีพ:** ถ้าคุณเป็น chip designer / silicon engineer / compiler engineer ที่มี ML background — ตลาดงานร้อนที่สุดในรอบทศวรรษ; ถ้าเป็น application dev ที่ใช้ Claude API — ผลลัพธ์อาจเห็นใน 2028-2029 เป็นราคาถูกลงและ latency ต่ำลง แต่วันนี้ไม่ต้องเปลี่ยนอะไรใน stack; ทีม infra ที่ประเมิน vendor lock-in ต้อง update model — Anthropic กำลังเดิน route คล้าย Google ที่ผูก compute แนบแน่นกับ model ของตัวเอง.
