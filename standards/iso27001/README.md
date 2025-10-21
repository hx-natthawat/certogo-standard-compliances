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
- **Biometric Data Processing** 🔴 | การประมวลผลข้อมูลไบโอเมตริกซ์

⚠️ **IMPORTANT**: Appman's E-KYC service may be changed in the future. All documentation accounts for provider changeability.

## Current Certifications | การรับรองที่มีอยู่แล้ว

### Appman (E-KYC Provider)
✅ **ISO 27001** - Information Security Management
✅ **CSA-STAR Level 2** - Cloud Security Alliance
✅ **ISO/IEC 27001** - ISMS Thailand Best Practice Level 1

### Certogo (Target)
🎯 **ISO 27001:2022** - In Progress (Target: 6-12 months)

## Directory Structure | โครงสร้างไดเรกทอรี

```
standards/iso27001/
│
├── 01-context/                          # ISO 27001 Clause 4 - ข้อ 4: บริบทขององค์กร
│   ├── scope-statement.md               # ISMS scope definition
│   ├── internal-external-issues.md      # Internal/external context
│   └── interested-parties.md            # Stakeholder requirements
│
├── 02-policies/                         # ISO 27001 Clause 5.2 - ข้อ 5.2: นโยบาย
│   ├── information-security-policy.md   # 🔴 MANDATORY - Main ISMS policy
│   ├── supplier-security-policy.md      # 🔴 CRITICAL for E-KYC provider
│   ├── pdpa-compliance-policy.md        # 🔴 CRITICAL for biometric data
│   ├── access-control-policy.md         # (To be created)
│   ├── incident-response-policy.md      # (To be created)
│   └── [other policies...]
│
├── 03-planning/                         # ISO 27001 Clause 6 - ข้อ 6: การวางแผน
│   ├── risk-assessment-template.md      # Risk identification and analysis
│   ├── risk-treatment-plan.md           # (To be created)
│   └── security-objectives.md           # (To be created)
│
├── 04-procedures/                       # ISO 27001 Clause 8 - ข้อ 8: การดำเนินการ
│   ├── data-deletion-procedure.md       # 🔴 CRITICAL for biometric data
│   ├── ekyc-provider-change-procedure.md # 🔴 20-week migration process
│   ├── incident-response-procedure.md   # (To be created)
│   ├── backup-recovery-procedure.md     # (To be created)
│   └── [other procedures...]
│
├── 05-annex-a-controls/                 # ISO 27001 Annex A - ภาคผนวก A: มาตรการควบคุม
│   ├── statement-of-applicability.md    # 🔴 MANDATORY - All 93 controls
│   ├── A.5-organizational-controls.md   # 23 controls (includes E-KYC provider mgmt)
│   ├── A.6-people-controls.md           # 8 controls (includes PDPA training)
│   ├── A.7-physical-controls.md         # (To be created) 14 controls
│   └── A.8-technological-controls.md    # (To be created) 34 controls
│
├── 06-templates/                        # Supporting templates - แม่แบบเอกสาร
│   ├── audit-preparation-checklist.md   # 153-item checklist
│   ├── dpia-template.md                 # (To be created) Data Protection Impact Assessment
│   └── [other templates...]
│
├── 07-ciso-assistant-integration/       # CISO Assistant GRC tool - เครื่องมือ GRC
│   ├── setup-guide.md                   # Installation and configuration
│   └── risk-tracking-guide.md           # (To be created)
│
└── README.md                            # This file - ไฟล์นี้
```

## Evidence Directory (Separate) | ไดเรกทอรีหลักฐาน

Evidence of compliance is maintained separately at `/evidence/`:

```
/evidence/
│
├── policies/                            # Signed policies (PDF with CEO signature)
│   ├── POL-001-information-security-policy-signed.pdf
│   ├── POL-003-pdpa-compliance-policy-signed.pdf
│   ├── POL-004-supplier-security-policy-signed.pdf
│   └── [other signed policies...]
│
├── procedures/                          # Approved procedures (signed)
│   ├── PROC-001-data-deletion-signed.pdf
│   ├── PROC-002-ekyc-provider-change-signed.pdf
│   └── [other procedures...]
│
├── records/                             # Operational evidence - หลักฐานการดำเนินงาน
│   ├── risk-assessment-2024.xlsx        # Annual risk assessment
│   ├── management-review-2024-Q1.pdf    # Management review minutes
│   ├── internal-audit-2024.pdf          # Internal audit reports
│   ├── supplier-register.xlsx           # All suppliers with security classification
│   ├── supplier-monitoring/             # Supplier reviews and reports
│   │   └── ekyc-quarterly-reviews/      # 🔴 Quarterly Appman reviews
│   ├── data-subject-requests.xlsx       # PDPA rights requests tracking
│   ├── ropa.xlsx                        # Record of Processing Activities (PDPA)
│   ├── dpia/                            # 🔴 Data Protection Impact Assessments
│   └── incident-logs/                   # Security incident records
│
├── contracts/                           # Third-party contracts - สัญญา
│   ├── appman-dpa-signed.pdf            # 🔴 Data Processing Agreement with Appman
│   ├── appman-sla.pdf                   # Service Level Agreement
│   ├── appman-iso27001-certificate.pdf  # 🔴 Appman's ISO 27001 cert
│   └── [other contracts...]
│
└── training-records/                    # Training completion - บันทึกการฝึกอบรม
    ├── security-awareness-2024.xlsx     # All employee training
    ├── pdpa-training-2024.xlsx          # 🔴 PDPA & biometric data handling
    └── training-certificates/           # Individual certificates
```

## Document Status Legend | สถานะเอกสาร

| Symbol | Status | Thai |
|--------|--------|------|
| ✅ | Complete | เสร็จสมบูรณ์ |
| 🔄 | In Progress | กำลังดำเนินการ |
| ⏳ | Planned | วางแผนไว้ |
| 🔴 | Critical Priority | สำคัญสูงสุด |
| 🟠 | High Priority | สำคัญสูง |
| 🟡 | Medium Priority | สำคัญปานกลาง |

## Quick Start Guide | คู่มือเริ่มต้นใช้งาน

### For Auditors (CB Certification) | สำหรับผู้ตรวจสอบจาก CB

**Day 1: Document Review**
1. ✅ Read `/standards/iso27001/05-annex-a-controls/statement-of-applicability.md` (All 93 controls)
2. ✅ Review policies: `/standards/iso27001/02-policies/` (3 policies completed)
3. ✅ Check `/standards/iso27001/03-planning/risk-assessment-template.md` (6 E-KYC risks documented)

**Day 2: Evidence Review**
4. ⏳ Review signed policies: `/evidence/policies/` (To be signed by CEO)
5. ⏳ Review E-KYC provider documentation:
   - `/evidence/contracts/appman-dpa-signed.pdf` 🔴
   - `/evidence/contracts/appman-iso27001-certificate.pdf` 🔴
   - `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/` 🔴
6. ⏳ Review PDPA compliance:
   - `/evidence/records/ropa.xlsx` (Record of Processing Activities)
   - `/evidence/records/dpia/ekyc-biometric-dpia.pdf` 🔴

**Day 3: Interviews & Testing**
7. Interview CISO, DPO, CTO (see `/standards/iso27001/06-templates/audit-preparation-checklist.md`)
8. Test data deletion procedure (request certificate from Appman)
9. Test data subject rights process (submit sample request)

### For Implementation Team | สำหรับทีมดำเนินการ

**Phase 1: Documentation (✅ COMPLETE)**
1. ✅ All policies created (3/3)
2. ✅ Statement of Applicability created (93 controls)
3. ✅ Risk assessment template created
4. ✅ Audit preparation checklist created

**Phase 2: Evidence Collection (🔄 IN PROGRESS - 20%)**
Next steps:
1. 🔴 Contact Appman for ISO 27001 certificate and DPA
2. 🔴 Create and sign policies (CEO signature required)
3. 🔴 Conduct risk assessment (use template)
4. 🟠 Conduct internal audit
5. 🟡 Collect training records

See `/TODO.md` for complete task list.

**Phase 3: Tool Setup (Optional but Recommended)**
- Install CISO Assistant: See `/standards/iso27001/07-ciso-assistant-integration/setup-guide.md`
- Benefits: Track compliance, manage risks, evidence collection

## Document Language | ภาษาของเอกสาร

All documents are provided in **bilingual format** (Thai/English):
- **Thai** (ไทย): Primary language for local auditors and stakeholders
- **English** (อังกฤษ): International terminology and keywords for CB auditors

เอกสารทั้งหมดจัดทำเป็น **สองภาษา** (ไทย/อังกฤษ):
- **ไทย**: ภาษาหลักสำหรับผู้ตรวจสอบและผู้มีส่วนได้ส่วนเสียในประเทศ
- **อังกฤษ**: คำศัพท์และคีย์เวิร์ดสากลสำหรับผู้ตรวจสอบจาก CB

## Critical E-KYC Provider Considerations | ข้อพิจารณาสำคัญเกี่ยวกับผู้ให้บริการ E-KYC 🔴

⚠️ **IMPORTANT**: Appman's E-KYC service may be changed in the future.

All documentation addresses provider changeability through:

1. **Prominent Warnings**: Every document notes that E-KYC provider is changeable
2. **20-Week Migration Procedure**: See `/standards/iso27001/04-procedures/ekyc-provider-change-procedure.md` (references A.5.22)
3. **6 E-KYC Specific Risks**: Documented in risk assessment (R-001 to R-012)
4. **Contractual Protections**: DPA with 30-day biometric data deletion requirement
5. **Supplier Assessment Framework**: 100+ question security questionnaire for any E-KYC provider
6. **Quarterly Monitoring**: Regular reviews of current provider (Appman)
7. **Documentation Update Triggers**: When provider changes, update SoA, policies, risk assessment

**Migration Readiness**: Certogo can switch E-KYC providers with 14-22 weeks notice while maintaining ISO 27001 compliance.

## Compliance Progress | ความคืบหน้าการปฏิบัติตาม

### Overall Readiness: 40% 📊

| Area | Status | Completion |
|------|--------|-----------|
| **Documentation** | ✅ Complete | 100% |
| **Policies** | ✅ Complete (3/3 created) | 100% |
| **Control Documentation** | ✅ Complete (93/93 controls) | 100% |
| **Evidence Collection** | 🔄 In Progress | 20% |
| **Risk Assessment** | 🔄 Template ready, execution pending | 50% |
| **Implementation** | 🔄 In Progress | 30% |
| **Training** | ⏳ Planned | 0% |
| **Internal Audit** | ⏳ Planned | 0% |

**Estimated Time to Certification**: 6-12 months

## Key Contacts | ผู้ติดต่อหลัก

- **Chief Executive Officer (CEO)**: [Name] - Ultimate ISMS accountability
- **Chief Information Security Officer (CISO)**: [Name] - ISMS owner, contact: security@certogo.com
- **Data Protection Officer (DPO)**: [Name] - PDPA compliance, contact: privacy@certogo.com
- **Chief Technology Officer (CTO)**: [Name] - Technical security implementation

## References | เอกสารอ้างอิง

### Standards
- ISO/IEC 27001:2022 - Information security, cybersecurity and privacy protection
- ISO/IEC 27002:2022 - Information security controls
- ISO/IEC 27005:2022 - Information security risk management
- ISO 19011:2018 - Guidelines for auditing management systems

### Regulations
- Thailand Personal Data Protection Act B.E. 2562 (2019) - PDPA

### Tools
- CISO Assistant Community: https://github.com/intuitem/ciso-assistant-community

### Appman E-KYC
- Appman User Manual: See `/docs/appman-user-manual.pdf`
- Appman E-KYC Manual: See `/docs/e-kyc-manual.pdf`

---

**Document Version** | เวอร์ชันเอกสาร: 2.0
**Last Updated** | อัปเดตล่าสุด: 2025-01-22
**Status** | สถานะ: Phase 1 Complete - Documentation Ready | เฟส 1 เสร็จสมบูรณ์ - เอกสารพร้อม
**Next Phase** | เฟสถัดไป: Evidence Collection & Implementation | การรวบรวมหลักฐานและการดำเนินการ
