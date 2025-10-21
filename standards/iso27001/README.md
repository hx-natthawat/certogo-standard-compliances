# ISO 27001:2022 Compliance Documentation for Certogo
# เอกสารการปฏิบัติตามมาตรฐาน ISO 27001:2022 สำหรับ Certogo

## Overview | ภาพรวม

This directory contains all documentation required for ISO 27001:2022 certification for Certogo's Learning Management System (LMS) and Appman E-KYC solution.

ไดเรกทอรีนี้ประกอบด้วยเอกสารทั้งหมดที่จำเป็นสำหรับการรับรองมาตรฐาน ISO 27001:2022 สำหรับระบบ Learning Management System (LMS) ของ Certogo และระบบ E-KYC ของ Appman

## Platform Scope | ขอบเขตของแพลตฟอร์ม

### Certogo Services | บริการของ Certogo
- **B2B/B2C SaaS Platform** | แพลตฟอร์ม SaaS แบบ B2B/B2C
- **Compliance & Non-Compliance LMS** | ระบบ LMS สำหรับการอบรมด้านการปฏิบัติตามกฎระเบียบและทั่วไป
- **Certificate Management** | การจัดการใบรับรอง
- **User Training Tracking** | การติดตามการอบรมผู้ใช้งาน

### Appman E-KYC Services | บริการ E-KYC ของ Appman
- **Digital Identity Verification** | การยืนยันตัวตนดิจิทัล
- **OCR Document Recognition** | การรู้จำเอกสารด้วย OCR
- **Facial Recognition & Liveness Detection** | การจดจำใบหน้าและตรวจสอบความเป็นมนุษย์
- **Multi-Document Support** | รองรับเอกสารหลายประเภท (บัตรประชาชน, พาสปอร์ต, ใบขับขี่)

## Current Certifications | การรับรองที่มีอยู่แล้ว

✅ **ISO 27001** - Information Security Management
✅ **CSA-STAR Level 2** - Cloud Security Alliance
✅ **ISO/IEC 27001** - ISMS Thailand Best Practice Level 1

## Directory Structure | โครงสร้างไดเรกทอรี

```
standards/iso27001/
├── 01-context-of-organization/          # ข้อ 4: บริบทขององค์กร
├── 02-leadership/                       # ข้อ 5: ภาวะผู้นำ
├── 03-planning/                         # ข้อ 6: การวางแผน
├── 04-support/                          # ข้อ 7: การสนับสนุน
├── 05-operation/                        # ข้อ 8: การดำเนินการ
├── 06-performance-evaluation/           # ข้อ 9: การประเมินผลการปฏิบัติงาน
├── 07-improvement/                      # ข้อ 10: การปรับปรุง
├── annex-a-controls/                    # ภาคผนวก A: มาตรการควบคุม
├── evidence/                            # หลักฐานการปฏิบัติตาม
├── templates/                           # แม่แบบเอกสาร
└── ciso-assistant-integration/          # การเชื่อมต่อกับ CISO Assistant
```

## Document Language | ภาษาของเอกสาร

All documents are provided in **bilingual format** (Thai/English):
- **Thai** (ไทย): Primary language for local auditors and stakeholders
- **English** (อังกฤษ): International terminology and keywords for CB auditors

เอกสารทั้งหมดจัดทำเป็น **สองภาษา** (ไทย/อังกฤษ):
- **ไทย**: ภาษาหลักสำหรับผู้ตรวจสอบและผู้มีส่วนได้ส่วนเสียในประเทศ
- **อังกฤษ**: คำศัพท์และคีย์เวิร์ดสากลสำหรับผู้ตรวจสอบจาก CB

## Quick Start Guide | คู่มือเริ่มต้นใช้งาน

### For Auditors | สำหรับผู้ตรวจสอบ

1. **Start with Statement of Applicability** | เริ่มต้นด้วยแถลงการณ์การประยุกต์ใช้
   - See: `annex-a-controls/statement-of-applicability.md`

2. **Review Mandatory Documents** | ตรวจสอบเอกสารบังคับ
   - Information Security Policy | นโยบายความมั่นคงปลอดภัยสารสนเทศ
   - Risk Assessment | การประเมินความเสี่ยง
   - Risk Treatment Plan | แผนการจัดการความเสี่ยง

3. **Check Evidence Records** | ตรวจสอบหลักฐาน
   - See: `evidence/` directory

### For Implementation Team | สำหรับทีมดำเนินการ

1. **Use CISO Assistant** for tracking compliance
   - See: `ciso-assistant-integration/setup-guide.md`

2. **Follow Templates** for creating new documentation
   - See: `templates/` directory

## Audit Preparation Checklist | รายการตรวจสอบการเตรียมตัวตรวจประเมิน

See: `templates/audit-preparation-checklist.md`

## Key Contacts | ผู้ติดต่อหลัก

- **Information Security Officer** | เจ้าหน้าที่ความมั่นคงปลอดภัยสารสนเทศ: [TBD]
- **ISMS Coordinator** | ผู้ประสานงาน ISMS: [TBD]
- **Internal Auditor** | ผู้ตรวจสอบภายใน: [TBD]

## References | เอกสารอ้างอิง

- ISO/IEC 27001:2022 - Information security, cybersecurity and privacy protection
- ISO/IEC 27002:2022 - Information security controls
- CISO Assistant Community: https://github.com/intuitem/ciso-assistant-community

---

**Document Version** | เวอร์ชันเอกสาร: 1.0
**Last Updated** | อัปเดตล่าสุด: 2025-01-20
**Status** | สถานะ: Initial Draft | ร่างเอกสารเบื้องต้น
