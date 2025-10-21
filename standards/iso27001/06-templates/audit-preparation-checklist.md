# ISO 27001:2022 Audit Preparation Checklist
# รายการตรวจสอบการเตรียมตัวสำหรับการตรวจประเมิน ISO 27001:2022

## Document Information | ข้อมูลเอกสาร

**Organization** | **องค์กร**: Certogo Co., Ltd.
**Audit Type** | **ประเภทการตรวจสอบ**: Stage 1 & Stage 2 Certification Audit
**Standard** | **มาตรฐาน**: ISO/IEC 27001:2022
**Version** | **เวอร์ชัน**: 1.0
**Date** | **วันที่**: 2025-01-20

---

## Table of Contents | สารบัญ

1. [Pre-Audit Preparation (8-12 Weeks Before)](#1-pre-audit-preparation-8-12-weeks-before)
2. [Document Preparation Checklist](#2-document-preparation-checklist)
3. [Evidence Collection by Control](#3-evidence-collection-by-control)
4. [E-KYC Provider Documentation](#4-e-kyc-provider-documentation-)
5. [Interview Preparation](#5-interview-preparation)
6. [Facility Preparation](#6-facility-preparation)
7. [Day-of-Audit Checklist](#7-day-of-audit-checklist)
8. [Post-Audit Actions](#8-post-audit-actions)

---

## 1. Pre-Audit Preparation (8-12 Weeks Before)
## การเตรียมการก่อนการตรวจสอบ (8-12 สัปดาห์ก่อน)

### Week -12 to -10 | สัปดาห์ที่ -12 ถึง -10

#### Management Commitment | ความมุ่งมั่นของฝ่ายบริหาร

- [ ] **CEO approval** of Information Security Policy
  - **การอนุมัติจาก CEO** สำหรับนโยบายความมั่นคงปลอดภัยสารสนเทศ
  - File: `/evidence/policies/information-security-policy.pdf`
  - Signed and dated within last 12 months

- [ ] **Management Review** meeting conducted
  - **การประชุมทบทวนฝ่ายบริหาร** ดำเนินการแล้ว
  - File: `/evidence/records/management-review-minutes-[YYYY-MM].pdf`
  - Required attendees: CEO, CISO, CTO, DPO

- [ ] **ISMS Scope** defined and approved
  - **ขอบเขต ISMS** กำหนดและอนุมัติแล้ว
  - File: `/01-context-of-organization/isms-scope.pdf`
  - Must include: Certogo LMS + Appman E-KYC integration

- [ ] **Information Security Committee** established
  - **คณะกรรมการความมั่นคงปลอดภัยสารสนเทศ** จัดตั้งแล้ว
  - File: `/evidence/records/committee-charter.pdf`

#### Internal Audit | การตรวจสอบภายใน

- [ ] **Internal audit** completed (within 12 months)
  - **การตรวจสอบภายใน** เสร็จสมบูรณ์ (ภายใน 12 เดือน)
  - File: `/evidence/audit-reports/internal-audit-report-[YYYY-MM].pdf`
  - Must cover: All clauses (4-10) and applicable Annex A controls

- [ ] **Internal auditor competency** verified
  - **ความสามารถของผู้ตรวจสอบภายใน** ตรวจสอบแล้ว
  - File: `/evidence/records/auditor-certifications/`
  - Required: ISO 27001 Lead Auditor or equivalent

- [ ] **Non-conformities from internal audit** closed
  - **ข้อบกพร่องจากการตรวจสอบภายใน** ปิดแล้ว
  - File: `/evidence/records/corrective-actions/`
  - All major NCs must be closed before certification audit

### Week -8 to -6 | สัปดาห์ที่ -8 ถึง -6

#### Risk Management | การจัดการความเสี่ยง

- [ ] **Risk Assessment** completed and current
  - **การประเมินความเสี่ยง** เสร็จสมบูรณ์และเป็นปัจจุบัน
  - File: `/03-planning/risk-assessment-[YYYY].xlsx`
  - Updated within last 12 months
  - Must include: E-KYC provider risks 🔴

- [ ] **Risk Treatment Plan** approved
  - **แผนการจัดการความเสี่ยง** อนุมัติแล้ว
  - File: `/03-planning/risk-treatment-plan-[YYYY].pdf`
  - All high/critical risks must have mitigation plans

- [ ] **Statement of Applicability (SoA)** finalized
  - **แถลงการณ์การประยุกต์ใช้ (SoA)** สำเร็จแล้ว
  - File: `/annex-a-controls/statement-of-applicability.md`
  - All 93 Annex A controls addressed
  - Justifications for "Not Applicable" controls provided
  - 🔴 E-KYC provider change considerations included

#### Asset Management | การจัดการทรัพย์สิน

- [ ] **Asset inventory** complete and current
  - **บัญชีทรัพย์สิน** สมบูรณ์และเป็นปัจจุบัน
  - File: `/evidence/records/asset-inventory.xlsx`
  - Includes: Hardware, software, data, cloud services
  - Classified by: Public, Internal, Confidential, Highly Confidential

- [ ] **Data classification** labels applied
  - **ป้ายกำกับการจัดชั้นความลับข้อมูล** ถูกนำไปใช้
  - Biometric data marked as "Highly Confidential" 🔴
  - Evidence: Screenshots of classified documents/systems

### Week -4 to -2 | สัปดาห์ที่ -4 ถึง -2

#### Documentation Review | การทบทวนเอกสาร

- [ ] **All mandatory documents** reviewed and up-to-date
  - **เอกสารบังคับทั้งหมด** ทบทวนและเป็นปัจจุบัน
  - See: [Section 2: Document Preparation Checklist](#2-document-preparation-checklist)

- [ ] **Document version control** verified
  - **การควบคุมเวอร์ชันเอกสาร** ตรวจสอบแล้ว
  - All documents have: Version number, date, approval signature
  - Superseded documents archived (not deleted)

- [ ] **Bilingual documentation** prepared
  - **เอกสารสองภาษา** เตรียมพร้อม
  - Thai for local auditors, English keywords for CB auditors
  - Both versions consistent

#### E-KYC Provider Preparation 🔴

- [ ] **Appman ISO 27001 certificate** obtained and valid
  - **ใบรับรอง ISO 27001 ของ Appman** ได้รับและยังใช้ได้
  - File: `/evidence/records/appman-iso27001-certificate.pdf`
  - Expiry date: [DATE] - must be valid during audit

- [ ] **Appman PDPA compliance** documented
  - **การปฏิบัติตาม PDPA ของ Appman** จัดทำเอกสารแล้ว
  - File: `/evidence/records/appman-pdpa-compliance.pdf`

- [ ] **Data Processing Agreement (DPA)** with Appman signed
  - **ข้อตกลงการประมวลผลข้อมูล (DPA)** กับ Appman ลงนามแล้ว
  - File: `/evidence/contracts/appman-dpa.pdf`

- [ ] **Supplier security assessment** for Appman completed
  - **การประเมินความปลอดภัยของซัพพลายเออร์** สำหรับ Appman เสร็จสมบูรณ์
  - File: `/evidence/records/supplier-security-assessment/appman-assessment-[YYYY].pdf`

- [ ] **Quarterly security reports** from Appman available
  - **รายงานความปลอดภัยรายไตรมาส** จาก Appman พร้อมให้
  - File: `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/`
  - Last 4 quarters minimum

### Week -1 | สัปดาห์ที่ -1

#### Final Preparations | การเตรียมการขั้นสุดท้าย

- [ ] **Mock audit** conducted (optional but recommended)
  - **การตรวจสอบจำลอง** ดำเนินการ (เลือกได้แต่แนะนำ)
  - Identify any last-minute gaps

- [ ] **Auditor logistics** confirmed
  - **ลอจิสติกส์ของผู้ตรวจสอบ** ยืนยันแล้ว
  - Meeting room booked
  - Wi-Fi access for auditors
  - Parking arrangements
  - Lunch/refreshments arranged

- [ ] **Interviewees** notified and scheduled
  - **ผู้ถูกสัมภาษณ์** แจ้งเตือนและกำหนดเวลาแล้ว
  - See: [Section 5: Interview Preparation](#5-interview-preparation)

- [ ] **Audit agenda** received from CB
  - **วาระการตรวจสอบ** ได้รับจาก CB
  - Review and prepare accordingly

---

## 2. Document Preparation Checklist
## รายการตรวจสอบการเตรียมเอกสาร

### Mandatory Documents (ISO 27001:2022 Clauses 4-10)
### เอกสารบังคับ (ข้อ 4-10 ของ ISO 27001:2022)

#### Clause 4: Context of the Organization | ข้อ 4: บริบทขององค์กร

- [ ] **4.1 Understanding the organization and its context**
  - [ ] Business context document | เอกสารบริบทธุรกิจ
  - File: `/01-context-of-organization/business-context.pdf`
  - Includes: Certogo LMS services, E-KYC integration, market position

- [ ] **4.2 Understanding the needs and expectations of interested parties**
  - [ ] Stakeholder register | ทะเบียนผู้มีส่วนได้ส่วนเสีย
  - File: `/01-context-of-organization/stakeholder-register.xlsx`
  - Includes: Customers, employees, regulators, E-KYC provider

- [ ] **4.3 Determining the scope of the ISMS**
  - [ ] ISMS Scope document | เอกสารขอบเขต ISMS
  - File: `/01-context-of-organization/isms-scope.pdf`
  - **CRITICAL**: Must clearly state "Certogo LMS + Appman E-KYC integration"

#### Clause 5: Leadership | ข้อ 5: ภาวะผู้นำ

- [ ] **5.1 Leadership and commitment**
  - [ ] Management commitment statement | แถลงการณ์ความมุ่งมั่นของฝ่ายบริหาร
  - File: `/02-leadership/management-commitment.pdf`

- [ ] **5.2 Policy**
  - [ ] Information Security Policy 🔴 **MANDATORY**
  - File: `/evidence/policies/information-security-policy.pdf`
  - Must be: Signed by CEO, dated within 12 months, available to all employees

- [ ] **5.3 Organizational roles, responsibilities and authorities**
  - [ ] RACI matrix for security roles | เมทริกซ์ RACI สำหรับบทบาทด้านความปลอดภัย
  - File: `/evidence/policies/roles-and-responsibilities-matrix.xlsx`
  - Must include: CISO, CTO, DPO, Supplier Management Team

#### Clause 6: Planning | ข้อ 6: การวางแผน

- [ ] **6.1.2 Information security risk assessment** 🔴 **MANDATORY**
  - [ ] Risk assessment methodology | วิธีการประเมินความเสี่ยง
  - File: `/03-planning/risk-assessment-methodology.pdf`
  - [ ] Risk assessment results | ผลการประเมินความเสี่ยง
  - File: `/03-planning/risk-assessment-[YYYY].xlsx`
  - **Must include**: E-KYC provider risks (data breach, provider change, vendor lock-in)

- [ ] **6.1.3 Information security risk treatment** 🔴 **MANDATORY**
  - [ ] Risk treatment plan | แผนการจัดการความเสี่ยง
  - File: `/03-planning/risk-treatment-plan-[YYYY].pdf`

- [ ] **6.2 Information security objectives**
  - [ ] Security objectives document | เอกสารวัตถุประสงค์ด้านความปลอดภัย
  - File: `/03-planning/security-objectives-[YYYY].pdf`
  - Must be: Measurable, monitored, communicated

- [ ] **6.3 Planning of changes**
  - [ ] Change management procedure | ขั้นตอนการจัดการการเปลี่ยนแปลง
  - File: `/evidence/procedures/change-management-procedure.pdf`
  - 🔴 Must include: E-KYC provider change procedure (A.5.22)

#### Clause 7: Support | ข้อ 7: การสนับสนุน

- [ ] **7.2 Competence**
  - [ ] Job descriptions with security responsibilities
  - File: `/evidence/records/job-descriptions/`
  - [ ] Training records | บันทึกการฝึกอบรม
  - File: `/evidence/records/training-records.xlsx`
  - All employees must have: Security awareness training (annual)

- [ ] **7.3 Awareness**
  - [ ] Security awareness program | โปรแกรมความตระหนักรู้ด้านความปลอดภัย
  - File: `/04-support/security-awareness-program.pdf`
  - [ ] Evidence of delivery (attendance sheets, completion certificates)
  - File: `/evidence/records/awareness-training-attendance/`

- [ ] **7.4 Communication**
  - [ ] Internal communication plan | แผนการสื่อสารภายใน
  - File: `/04-support/communication-plan.pdf`
  - [ ] Evidence: Email announcements, intranet posts

- [ ] **7.5 Documented information** 🔴 **MANDATORY**
  - [ ] Document control procedure | ขั้นตอนการควบคุมเอกสาร
  - File: `/evidence/procedures/document-control-procedure.pdf`
  - Must cover: Creation, review, approval, distribution, retention, disposal

#### Clause 8: Operation | ข้อ 8: การดำเนินการ

- [ ] **8.1 Operational planning and control**
  - [ ] ISMS operational plan | แผนการดำเนินงาน ISMS
  - File: `/05-operation/isms-operational-plan.pdf`

- [ ] **8.2 Information security risk assessment** (ongoing)
  - [ ] Evidence of regular risk reviews | หลักฐานการทบทวนความเสี่ยงสม่ำเสมอ
  - File: `/evidence/records/risk-review-log.xlsx`
  - Frequency: At least annually, or when significant changes occur

- [ ] **8.3 Information security risk treatment** (ongoing)
  - [ ] Evidence of risk treatment implementation
  - File: `/evidence/records/risk-treatment-evidence/`

#### Clause 9: Performance Evaluation | ข้อ 9: การประเมินผลการปฏิบัติงาน

- [ ] **9.1 Monitoring, measurement, analysis and evaluation**
  - [ ] Security metrics and KPIs | ตัวชี้วัดและ KPI ด้านความปลอดภัย
  - File: `/06-performance-evaluation/security-metrics.xlsx`
  - Examples: Incident count, patch compliance %, uptime %

- [ ] **9.2 Internal audit** 🔴 **MANDATORY**
  - [ ] Internal audit program | โปรแกรมการตรวจสอบภายใน
  - File: `/evidence/procedures/internal-audit-program.pdf`
  - [ ] Internal audit report (within 12 months) | รายงานการตรวจสอบภายใน (ภายใน 12 เดือน)
  - File: `/evidence/audit-reports/internal-audit-report-[YYYY-MM].pdf`
  - [ ] Audit findings and corrective actions
  - File: `/evidence/records/corrective-actions/`

- [ ] **9.3 Management review** 🔴 **MANDATORY**
  - [ ] Management review procedure | ขั้นตอนการทบทวนฝ่ายบริหาร
  - File: `/evidence/procedures/management-review-procedure.pdf`
  - [ ] Management review minutes (within 12 months) | รายงานการประชุมทบทวนฝ่ายบริหาร (ภายใน 12 เดือน)
  - File: `/evidence/records/management-review-minutes-[YYYY-MM].pdf`
  - Must cover: Audit results, performance, risks, improvement opportunities

#### Clause 10: Improvement | ข้อ 10: การปรับปรุง

- [ ] **10.1 Continual improvement**
  - [ ] Improvement initiatives log | บันทึกการริเริ่มการปรับปรุง
  - File: `/07-improvement/improvement-initiatives.xlsx`

- [ ] **10.2 Nonconformity and corrective action**
  - [ ] Corrective action procedure | ขั้นตอนการแก้ไขข้อบกพร่อง
  - File: `/evidence/procedures/corrective-action-procedure.pdf`
  - [ ] Corrective action log | บันทึกการแก้ไขข้อบกพร่อง
  - File: `/evidence/records/corrective-actions/corrective-action-log.xlsx`
  - All major NCs from internal audit must be closed

---

### Supporting Policies and Procedures | นโยบายและขั้นตอนสนับสนุน

#### General Policies | นโยบายทั่วไป

- [ ] **Access Control Policy** | นโยบายการควบคุมการเข้าถึง
  - File: `/evidence/policies/access-control-policy.pdf`

- [ ] **Acceptable Use Policy (AUP)** | นโยบายการใช้งานที่ยอมรับได้
  - File: `/evidence/policies/acceptable-use-policy.pdf`

- [ ] **Data Classification Policy** | นโยบายการจัดชั้นความลับข้อมูล
  - File: `/evidence/policies/data-classification-policy.pdf`

- [ ] **Incident Response Policy** | นโยบายการตอบสนองต่อเหตุการณ์
  - File: `/evidence/policies/incident-response-policy.pdf`

- [ ] **Business Continuity Policy** | นโยบายความต่อเนื่องทางธุรกิจ
  - File: `/evidence/policies/business-continuity-policy.pdf`

- [ ] **PDPA Compliance Policy** 🔴 | นโยบายการปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล
  - File: `/evidence/policies/pdpa-compliance-policy.pdf`

- [ ] **Supplier Security Policy** 🔴 | นโยบายความปลอดภัยของซัพพลายเออร์
  - File: `/evidence/policies/supplier-security-policy.pdf`

#### Technical Procedures | ขั้นตอนทางเทคนิค

- [ ] **Backup and Recovery Procedure** | ขั้นตอนการสำรองและกู้คืนข้อมูล
  - File: `/evidence/procedures/backup-recovery-procedure.pdf`

- [ ] **Patch Management Procedure** | ขั้นตอนการจัดการแพตช์
  - File: `/evidence/procedures/patch-management-procedure.pdf`

- [ ] **Vulnerability Management Procedure** | ขั้นตอนการจัดการช่องโหว่
  - File: `/evidence/procedures/vulnerability-management-procedure.pdf`

- [ ] **Access Control Procedure** | ขั้นตอนการควบคุมการเข้าถึง
  - File: `/evidence/procedures/access-control-procedure.pdf`

- [ ] **Encryption Procedure** | ขั้นตอนการเข้ารหัส
  - File: `/evidence/procedures/encryption-procedure.pdf`

- [ ] **Log Management Procedure** | ขั้นตอนการจัดการบันทึก
  - File: `/evidence/procedures/log-management-procedure.pdf`

---

## 3. Evidence Collection by Control
## การรวบรวมหลักฐานตามมาตรการควบคุม

### Annex A.5: Organizational Controls | มาตรการควบคุมระดับองค์กร

#### A.5.1 Policies for Information Security

- [ ] Information Security Policy (signed by CEO)
- [ ] Policy distribution records (email confirmations, acknowledgments)
- [ ] Policy review meeting minutes

#### A.5.9 Inventory of Information and Other Associated Assets

- [ ] Complete asset inventory | บัญชีทรัพย์สินที่สมบูรณ์
  - File: `/evidence/records/asset-inventory.xlsx`
  - Include: Servers, workstations, cloud services, databases, applications
  - Each asset must have: Owner, classification, location

#### A.5.12 Classification of Information

- [ ] Data classification policy | นโยบายการจัดชั้นความลับข้อมูล
- [ ] Examples of classified data:
  - Public: Marketing materials
  - Internal: Employee handbook
  - Confidential: Customer contracts
  - 🔴 **Highly Confidential**: Biometric data, ID card images

#### A.5.15 Access Control

- [ ] Access control matrix | เมทริกซ์การควบคุมการเข้าถึง
  - File: `/evidence/records/access-control-matrix.xlsx`
  - Shows: Who has access to what systems/data

- [ ] Evidence of least privilege implementation
  - Screenshots of user permissions
  - Role-based access control (RBAC) configuration

#### A.5.19 Information Security in Supplier Relationships 🔴

- [ ] **Supplier registry** | **ทะเบียนซัพพลายเออร์**
  - File: `/evidence/records/supplier-registry.xlsx`
  - Appman must be listed with Tier 1 classification

- [ ] **Appman security assessment** | **การประเมินความปลอดภัยของ Appman**
  - File: `/evidence/records/supplier-security-assessment/appman-assessment-[YYYY].pdf`

- [ ] **Appman ISO 27001 certificate** | **ใบรับรอง ISO 27001 ของ Appman**
  - File: `/evidence/records/appman-iso27001-certificate.pdf`

- [ ] **Appman PDPA compliance documentation**
  - File: `/evidence/records/appman-pdpa-compliance.pdf`

#### A.5.20 Addressing Information Security within Supplier Agreements 🔴

- [ ] **Appman service agreement** | **สัญญาการให้บริการของ Appman**
  - File: `/evidence/contracts/appman-service-agreement.pdf`
  - Must include: Security requirements, SLA, penalties

- [ ] **Appman Data Processing Agreement (DPA)** 🔴 **CRITICAL**
  - File: `/evidence/contracts/appman-dpa.pdf`
  - Must specify:
    - Data types processed (biometric data, ID cards)
    - Purpose limitation
    - Data retention (30 days for biometric data)
    - Data deletion procedures
    - Sub-processor requirements

#### A.5.22 Monitoring, Review and Change Management of Supplier Services 🔴

- [ ] **Quarterly security reports from Appman** | **รายงานความปลอดภัยรายไตรมาสจาก Appman**
  - File: `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/`
  - Last 4 quarters minimum

- [ ] **Monthly performance scorecards** | **ใบคะแนนประสิทธิภาพรายเดือน**
  - File: `/evidence/records/supplier-monitoring/ekyc-monthly-reports/`

- [ ] **Supplier change management procedure** | **ขั้นตอนการจัดการการเปลี่ยนแปลงซัพพลายเออร์**
  - File: `/evidence/procedures/supplier-change-management-procedure.pdf`

### Annex A.6: People Controls | มาตรการควบคุมด้านบุคลากร

#### A.6.1 Screening

- [ ] **Background check procedure** | **ขั้นตอนการตรวจสอบประวัติ**
  - File: `/evidence/procedures/background-check-procedure.pdf`

- [ ] **Evidence of background checks** (sample)
  - File: `/evidence/records/hr-records/` (anonymized for privacy)

#### A.6.2 Terms and Conditions of Employment

- [ ] **Employment contracts** with security clauses (sample)
  - File: `/evidence/records/hr-records/employment-contract-template.pdf`
  - Must include: NDA, acceptable use, data protection obligations

#### A.6.3 Information Security Awareness, Education and Training

- [ ] **Security awareness training program** | **โปรแกรมการฝึกอบรมความตระหนักรู้ด้านความปลอดภัย**
  - File: `/04-support/security-awareness-program.pdf`

- [ ] **Training records** | **บันทึกการฝึกอบรม**
  - File: `/evidence/records/training-records.xlsx`
  - Show: Employee name, training date, completion status
  - 🔴 Must include: PDPA training, E-KYC data handling training

- [ ] **Training materials** | **เอกสารการฝึกอบรม**
  - File: `/evidence/records/training-materials/`

#### A.6.4 Disciplinary Process

- [ ] **Disciplinary procedure** | **ขั้นตอนการลงโทษทางวินัย**
  - File: `/evidence/procedures/disciplinary-procedure.pdf`
  - Includes: Security policy violations

### Annex A.7: Physical Controls | มาตรการควบคุมทางกายภาพ

#### A.7.1 Physical Security Perimeters

- [ ] **Physical security policy** | **นโยบายความปลอดภัยทางกายภาพ**
  - File: `/evidence/policies/physical-security-policy.pdf`

- [ ] **Office access control records** | **บันทึกการควบคุมการเข้าถึงสำนักงาน**
  - File: `/evidence/records/access-logs/` (sample)
  - Key card access logs, visitor logs

#### A.7.2 Physical Entry

- [ ] **Visitor management procedure** | **ขั้นตอนการจัดการผู้เยี่ยมชม**
  - File: `/evidence/procedures/visitor-management-procedure.pdf`

- [ ] **Visitor logs** (sample) | **บันทึกผู้เยี่ยมชม** (ตัวอย่าง)
  - File: `/evidence/records/visitor-logs/`

#### A.7.4 Physical Security Monitoring

- [ ] **CCTV coverage map** | **แผนผังการติดตั้งกล้องวงจรปิด**
  - File: `/evidence/records/cctv-coverage-map.pdf`

- [ ] **Security monitoring logs** (sample)
  - File: `/evidence/records/security-monitoring-logs/`

### Annex A.8: Technological Controls | มาตรการควบคุมทางเทคโนโลยี

#### A.8.1 User Endpoint Devices

- [ ] **Endpoint security policy** | **นโยบายความปลอดภัยของอุปกรณ์ปลายทาง**
  - File: `/evidence/policies/endpoint-security-policy.pdf`

- [ ] **Antivirus deployment evidence** | **หลักฐานการติดตั้งซอฟต์แวร์ป้องกันไวรัส**
  - Screenshots of antivirus console showing coverage

#### A.8.2 Privileged Access Rights

- [ ] **Privileged access management procedure** | **ขั้นตอนการจัดการการเข้าถึงระดับสูง**
  - File: `/evidence/procedures/privileged-access-management.pdf`

- [ ] **List of privileged users** | **รายชื่อผู้ใช้ที่มีสิทธิ์ระดับสูง**
  - File: `/evidence/records/privileged-users-list.xlsx`

#### A.8.3 Information Access Restriction

- [ ] **Access control lists (ACLs)** | **รายการควบคุมการเข้าถึง**
  - File: `/evidence/records/access-control-lists/`

- [ ] **Database access logs** (sample)
  - File: `/evidence/records/database-access-logs/`

#### A.8.8 Management of Technical Vulnerabilities

- [ ] **Vulnerability management procedure** | **ขั้นตอนการจัดการช่องโหว่**
  - File: `/evidence/procedures/vulnerability-management-procedure.pdf`

- [ ] **Vulnerability scan reports** (last 3 months) | **รายงานการสแกนช่องโหว่** (3 เดือนล่าสุด)
  - File: `/evidence/records/vulnerability-scans/`

- [ ] **Patch management records** | **บันทึกการจัดการแพตช์**
  - File: `/evidence/records/patch-management-log.xlsx`

#### A.8.9 Configuration Management

- [ ] **Configuration management procedure** | **ขั้นตอนการจัดการการกำหนดค่า**
  - File: `/evidence/procedures/configuration-management-procedure.pdf`

- [ ] **Server baseline configurations** | **การกำหนดค่าพื้นฐานของเซิร์ฟเวอร์**
  - File: `/evidence/records/server-baseline-configs/`

#### A.8.10 Information Deletion 🔴

- [ ] **Data deletion procedure** | **ขั้นตอนการลบข้อมูล**
  - File: `/evidence/procedures/data-deletion-procedure.pdf`
  - 🔴 Must include: Biometric data 30-day auto-deletion

- [ ] **Evidence of data deletion** | **หลักฐานการลบข้อมูล**
  - File: `/evidence/records/data-deletion-log.xlsx`
  - Automated deletion logs for biometric data

- [ ] **Appman data deletion certificate** (if provider changed)
  - File: `/evidence/records/supplier-change-management/appman-data-deletion-certificate.pdf`

#### A.8.16 Monitoring Activities

- [ ] **Security monitoring procedure** | **ขั้นตอนการตรวจสอบความปลอดภัย**
  - File: `/evidence/procedures/security-monitoring-procedure.pdf`

- [ ] **SIEM deployment evidence** | **หลักฐานการใช้งาน SIEM**
  - Screenshots of SIEM dashboard

- [ ] **Alert configuration** | **การกำหนดค่าการแจ้งเตือน**
  - File: `/evidence/records/siem-alert-rules.pdf`

#### A.8.23 Web Filtering

- [ ] **Web filtering policy** | **นโยบายการกรองเว็บ**
  - File: `/evidence/policies/web-filtering-policy.pdf`

- [ ] **Web filtering configuration** | **การกำหนดค่าการกรองเว็บ**
  - Screenshots of web filter settings

#### A.8.24 Use of Cryptography

- [ ] **Cryptography policy** | **นโยบายการเข้ารหัส**
  - File: `/evidence/policies/cryptography-policy.pdf`
  - Must specify: Algorithms (AES-256, RSA-2048+), key management

- [ ] **Evidence of encryption implementation**:
  - Database encryption: Screenshots or configuration files
  - 🔴 **Biometric data encryption (at rest and in transit)**
  - TLS 1.3 for API connections (certificate configuration)

#### A.8.25 Secure Development Life Cycle

- [ ] **Secure SDLC procedure** | **ขั้นตอน Secure SDLC**
  - File: `/evidence/procedures/secure-sdlc-procedure.pdf`

- [ ] **Code review records** (sample) | **บันทึกการทบทวนโค้ด** (ตัวอย่าง)
  - File: `/evidence/records/code-review-log.xlsx`

- [ ] **Security testing reports** (penetration test, SAST, DAST)
  - File: `/evidence/records/security-testing/`

#### A.8.26 Application Security Requirements

- [ ] **Application security standards** | **มาตรฐานความปลอดภัยของแอปพลิเคชัน**
  - File: `/evidence/policies/application-security-standards.pdf`
  - Include: OWASP Top 10 mitigation

- [ ] **WAF (Web Application Firewall) deployment**
  - Screenshots of WAF dashboard

#### A.8.28 Secure Coding

- [ ] **Secure coding guidelines** | **แนวทางการเขียนโค้ดที่ปลอดภัย**
  - File: `/evidence/procedures/secure-coding-guidelines.pdf`

- [ ] **Developer training on secure coding** | **การฝึกอบรมนักพัฒนาเกี่ยวกับการเขียนโค้ดที่ปลอดภัย**
  - File: `/evidence/records/training-records.xlsx` (filter by "Secure Coding")

---

## 4. E-KYC Provider Documentation 🔴
## เอกสารผู้ให้บริการ E-KYC

**CRITICAL FOR AUDIT** | **สำคัญสำหรับการตรวจสอบ**

### Supplier Management Evidence | หลักฐานการจัดการซัพพลายเออร์

- [ ] **Supplier Security Assessment for Appman** 🔴
  - File: `/evidence/records/supplier-security-assessment/appman-assessment-[YYYY].pdf`
  - Must include: Security questionnaire (100+ questions), risk assessment

- [ ] **Appman ISO 27001 Certificate** 🔴
  - File: `/evidence/records/appman-iso27001-certificate.pdf`
  - Ensure: Valid and not expired during audit

- [ ] **Appman PDPA Compliance Documentation** 🔴
  - File: `/evidence/records/appman-pdpa-compliance.pdf`

- [ ] **Appman Penetration Testing Report**
  - File: `/evidence/records/appman-penetration-test-[YYYY].pdf`
  - Within last 12 months

### Contractual Documentation | เอกสารสัญญา

- [ ] **Service Agreement with Appman** 🔴
  - File: `/evidence/contracts/appman-service-agreement.pdf`
  - Must include: Security requirements, SLA (99.9% uptime), penalties

- [ ] **Data Processing Agreement (DPA)** 🔴 **MOST CRITICAL**
  - File: `/evidence/contracts/appman-dpa.pdf`
  - Auditor will review closely for:
    - Purpose limitation (identity verification only)
    - Data retention (30 days for biometric data)
    - Data localization (Thailand)
    - Sub-processor approval requirements
    - Data deletion upon termination

- [ ] **Service Level Agreement (SLA)** 🔴
  - File: `/evidence/contracts/appman-sla.pdf`
  - Must specify: Uptime %, response time, incident notification timelines

### Monitoring and Performance Evidence | หลักฐานการติดตามและประสิทธิภาพ

- [ ] **Quarterly Security Reports from Appman** 🔴
  - File: `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/`
  - **Required**: Last 4 quarters (Q1, Q2, Q3, Q4 of previous year)
  - Each report must include:
    - Security incidents summary
    - Performance metrics (uptime, latency)
    - Compliance status (ISO 27001, PDPA)
    - Changes to security controls

- [ ] **Monthly Performance Scorecards** 🔴
  - File: `/evidence/records/supplier-monitoring/ekyc-monthly-reports/`
  - Last 12 months
  - Show: Availability %, accuracy %, incident count

- [ ] **API Monitoring Dashboards** (screenshots)
  - File: `/evidence/records/supplier-monitoring/ekyc-api-monitoring-screenshots/`
  - Real-time availability, response time, error rate

- [ ] **Incident Log (E-KYC Related)**
  - File: `/evidence/records/supplier-monitoring/ekyc-incident-log.xlsx`
  - All incidents related to Appman E-KYC service

### Change Management Evidence | หลักฐานการจัดการการเปลี่ยนแปลง

- [ ] **E-KYC Provider Change Procedure** 🔴
  - File: `/evidence/procedures/ekyc-provider-change-procedure.pdf`
  - **CRITICAL**: Auditor will verify you have a plan for provider migration
  - Must cover: Assessment, migration, data deletion, documentation updates

- [ ] **Supplier Change Request Log** (if any changes occurred)
  - File: `/evidence/records/supplier-change-management/change-request-log.xlsx`
  - Examples: API version upgrades, feature additions

### Data Protection Evidence | หลักฐานการคุ้มครองข้อมูล

- [ ] **Biometric Data Retention Policy** 🔴
  - File: `/evidence/policies/biometric-data-retention-policy.pdf`
  - Must specify: 30-day maximum retention

- [ ] **Automated Deletion Logs** 🔴
  - File: `/evidence/records/data-deletion-log.xlsx`
  - Proof of automated deletion of biometric data after 30 days

- [ ] **Data Subject Rights Handling**
  - File: `/evidence/records/data-subject-requests/` (sample)
  - Examples: Access requests, deletion requests handled

### Integration Security Evidence | หลักฐานความปลอดภัยการเชื่อมต่อ

- [ ] **E-KYC API Security Architecture** 🔴
  - File: `/evidence/technical-documentation/ekyc-api-security-architecture.pdf`
  - Must show:
    - TLS 1.3 encryption
    - OAuth 2.0 + JWT authentication
    - Rate limiting
    - API key management
    - Network segmentation

- [ ] **API Access Logs** (sample)
  - File: `/evidence/records/api-access-logs/` (last 3 months)

- [ ] **Encryption Configuration** 🔴
  - File: `/evidence/records/encryption-configuration.pdf`
  - Proof of:
    - Data in transit: TLS 1.3
    - Data at rest: AES-256
    - Key rotation schedule (every 90 days)

---

## 5. Interview Preparation
## การเตรียมตัวสัมภาษณ์

### Key Personnel to Prepare | บุคลากรหลักที่ต้องเตรียมตัว

#### CEO / Top Management | ประธานเจ้าหน้าที่บริหาร / ฝ่ายบริหารสูงสุด

**Topics to Prepare** | **หัวข้อที่ต้องเตรียม**:
- ISMS scope and objectives | ขอบเขตและวัตถุประสงค์ของ ISMS
- Management commitment to information security | ความมุ่งมั่นของฝ่ายบริหารต่อความมั่นคงปลอดภัยสารสนเทศ
- Resource allocation for ISMS | การจัดสรรทรัพยากรสำหรับ ISMS
- Management review participation | การมีส่วนร่วมในการทบทวนฝ่ายบริหาร

**Sample Questions** | **คำถามตัวอย่าง**:
- Q: How does information security support business objectives?
  - A: Protects customer data (especially biometric data), maintains trust, ensures compliance with PDPA
- Q: What is your role in ISMS?
  - A: Approve policies, allocate resources, review ISMS performance quarterly

#### CISO (Chief Information Security Officer) | หัวหน้าเจ้าหน้าที่ความมั่นคงปลอดภัยสารสนเทศ

**Topics to Prepare** | **หัวข้อที่ต้องเตรียม**:
- Overall ISMS implementation and operation | การนำ ISMS ไปใช้และดำเนินการโดยรวม
- Risk management process | กระบวนการจัดการความเสี่ยง
- 🔴 **E-KYC provider security assessment and monitoring** | **การประเมินและติดตามความปลอดภัยของผู้ให้บริการ E-KYC**
- Incident management | การจัดการเหตุการณ์
- Security metrics and KPIs | ตัวชี้วัดและ KPI ด้านความปลอดภัย

**Sample Questions** | **คำถามตัวอย่าง**:
- Q: How do you manage risks associated with the E-KYC provider (Appman)?
  - A: Annual security assessment, quarterly reviews, contract with security SLAs, monitoring of performance metrics
- Q: What happens if Appman has a data breach?
  - A: Incident notification within 4 hours (per contract), joint incident response, customer notification (if applicable), review of provider relationship
- Q: How do you ensure biometric data is deleted after 30 days?
  - A: Automated deletion scripts, monitoring logs, quarterly verification with Appman

#### CTO (Chief Technology Officer) | หัวหน้าเจ้าหน้าที่เทคโนโลยี

**Topics to Prepare** | **หัวข้อที่ต้องเตรียม**:
- Infrastructure security (cloud, network, systems) | ความปลอดภัยของโครงสร้างพื้นฐาน
- 🔴 **E-KYC API integration security** | **ความปลอดภัยการเชื่อมต่อ API ของ E-KYC**
- Backup and disaster recovery | การสำรองและกู้คืนข้อมูล
- Patch and vulnerability management | การจัดการแพตช์และช่องโหว่

**Sample Questions** | **คำถามตัวอย่าง**:
- Q: How is the E-KYC API secured?
  - A: TLS 1.3 encryption, OAuth 2.0 + JWT authentication, rate limiting, API gateway with monitoring
- Q: Where is biometric data stored?
  - A: At Appman's Thailand data center (per DPA requirement), not stored on Certogo servers
- Q: What is your RTO and RPO?
  - A: RTO < 4 hours, RPO < 1 hour (per BCP)

#### DPO (Data Protection Officer) | เจ้าหน้าที่คุ้มครองข้อมูลส่วนบุคคล

**Topics to Prepare** | **หัวข้อที่ต้องเตรียม**:
- PDPA compliance | การปฏิบัติตาม PDPA
- 🔴 **Biometric data protection** | **การคุ้มครองข้อมูลชีวมิติ**
- Data subject rights (access, deletion, portability) | สิทธิ์ของเจ้าของข้อมูล
- Privacy by design in LMS and E-KYC integration | ความเป็นส่วนตัวตามการออกแบบใน LMS และการเชื่อมต่อ E-KYC

**Sample Questions** | **คำถามตัวอย่าง**:
- Q: How do you protect biometric data?
  - A: Encryption (AES-256), access control (RBAC), 30-day retention, consent management, DPA with Appman
- Q: How do you handle data subject access requests?
  - A: Verified request within 30 days, coordinate with Appman for E-KYC data, provide data in machine-readable format
- Q: What is the legal basis for processing biometric data?
  - A: Explicit consent from users, necessary for identity verification service

#### Supplier Management Team Lead | หัวหน้าทีมบริหารซัพพลายเออร์

**Topics to Prepare** | **หัวข้อที่ต้องเตรียม**:
- 🔴 **Appman security assessment process** | **กระบวนการประเมินความปลอดภัยของ Appman**
- 🔴 **Supplier monitoring and performance tracking** | **การติดตามและติดตามประสิทธิภาพของซัพพลายเออร์**
- Contract management | การจัดการสัญญา
- 🔴 **E-KYC provider change procedure** | **ขั้นตอนการเปลี่ยนผู้ให้บริการ E-KYC**

**Sample Questions** | **คำถามตัวอย่าง**:
- Q: How often do you assess Appman's security?
  - A: Full assessment annually, quarterly reviews, monthly performance scorecards
- Q: What are the key risks with Appman?
  - A: Data breach, service availability, vendor lock-in, regulatory non-compliance
- Q: If you need to change E-KYC providers, what is the process?
  - A: (Refer to A.5.22 procedure) Security assessment, parallel testing, gradual migration, data deletion verification

#### Security Operations Team | ทีมปฏิบัติการความปลอดภัย

**Topics to Prepare** | **หัวข้อที่ต้องเตรียม**:
- 24/7 security monitoring | การตรวจสอบความปลอดภัยตลอด 24 ชั่วโมง
- Incident detection and response | การตรวจจับและตอบสนองเหตุการณ์
- SIEM and log analysis | SIEM และการวิเคราะห์บันทึก
- Vulnerability management | การจัดการช่องโหว่

**Sample Questions** | **คำถามตัวอย่าง**:
- Q: How do you monitor the E-KYC API?
  - A: Real-time monitoring dashboard, alerts for downtime/latency, log analysis in SIEM
- Q: What was the last security incident?
  - A: [Provide specific example, resolution, lessons learned]

#### Development Team Lead | หัวหน้าทีมพัฒนา

**Topics to Prepare** | **หัวข้อที่ต้องเตรียม**:
- Secure SDLC | Secure SDLC
- Code review and security testing | การทบทวนโค้ดและการทดสอบความปลอดภัย
- 🔴 **E-KYC integration code security** | **ความปลอดภัยของโค้ดเชื่อมต่อ E-KYC**

**Sample Questions** | **คำถามตัวอย่าง**:
- Q: How do you ensure E-KYC integration code is secure?
  - A: Code review, security testing (SAST/DAST), penetration testing, secure API key management

---

### Interview Scheduling | การกำหนดเวลาสัมภาษณ์

**Recommended Schedule** | **ตารางเวลาที่แนะนำ**:

**Day 1** (Stage 1 Audit):
- 09:00 - 10:00: Opening meeting | ประชุมเปิด
- 10:00 - 11:00: CEO / Top Management
- 11:00 - 12:00: CISO
- 12:00 - 13:00: Lunch break
- 13:00 - 14:00: DPO
- 14:00 - 15:00: Document review
- 15:00 - 16:00: Facility tour (if on-site)
- 16:00 - 17:00: Closing meeting Day 1

**Day 2** (Stage 2 Audit):
- 09:00 - 10:00: Opening meeting Day 2
- 10:00 - 11:00: CTO
- 11:00 - 12:00: Supplier Management Team Lead 🔴
- 12:00 - 13:00: Lunch break
- 13:00 - 14:00: Security Operations Team
- 14:00 - 15:00: Development Team Lead
- 15:00 - 16:30: Evidence review and verification
- 16:30 - 17:30: Closing meeting and findings

---

## 6. Facility Preparation
## การเตรียมสถานที่

### Meeting Room Setup | การจัดห้องประชุม

- [ ] **Auditor workspace** prepared
  - Table, chairs, power outlets
  - Wi-Fi access (guest network, isolated from production)
  - Whiteboard/flip chart for discussions

- [ ] **Projector/screen** available for presentations

- [ ] **Privacy** ensured
  - Room is soundproof or private
  - No confidential materials visible (whiteboards, papers)

### Document Access | การเข้าถึงเอกสาร

- [ ] **Document repository** accessible to auditor
  - Options: Shared folder, SharePoint, USB drive
  - All files organized by control number (A.5.1, A.5.2, etc.)

- [ ] **Electronic documents** preferred over paper
  - Faster for auditor to search and verify

- [ ] **Backup copies** of all documents
  - In case of technical issues

### System Access | การเข้าถึงระบบ

- [ ] **Read-only access** for auditor (if needed)
  - SIEM dashboard
  - Monitoring dashboards
  - Configuration management system

- [ ] **Screen sharing** capability
  - For demonstrating systems/configurations

### Refreshments | เครื่องดื่มและอาหารว่าง

- [ ] **Water, coffee, tea** available in meeting room

- [ ] **Lunch arrangements** confirmed
  - On-site catering or nearby restaurant reservations

---

## 7. Day-of-Audit Checklist
## รายการตรวจสอบในวันตรวจสอบ

### Before Auditor Arrival | ก่อนผู้ตรวจสอบมาถึง

- [ ] **Meeting room** set up and clean
- [ ] **Attendees** notified and confirmed
- [ ] **Documents** ready and accessible
- [ ] **Demonstration systems** tested and working
- [ ] **Emergency contact list** available (IT support, facility management)

### During Opening Meeting | ระหว่างการประชุมเปิด

- [ ] **Welcome auditor** and introductions
- [ ] **Confirm audit agenda** and schedule
- [ ] **Provide facility tour** (if requested)
- [ ] **Clarify scope** and any changes since application
- [ ] **Assign liaison** (typically CISO or ISMS Coordinator)

### During Audit | ระหว่างการตรวจสอบ

- [ ] **Be honest and transparent**
  - If you don't know, say "I don't know, let me find out"
  - Don't guess or make up answers

- [ ] **Provide evidence promptly**
  - Have documents ready in organized folders
  - If evidence is missing, acknowledge and commit to providing it

- [ ] **Take notes** of auditor questions and observations
  - For corrective action planning

- [ ] **Escort auditor** if they need to access server rooms or restricted areas

- [ ] **Avoid defensive behavior**
  - Welcome findings as opportunities for improvement

### During Closing Meeting | ระหว่างการประชุมปิด

- [ ] **Listen carefully** to auditor findings
- [ ] **Take notes** of all non-conformities (NCs)
- [ ] **Ask for clarification** if any NC is unclear
- [ ] **Acknowledge findings** professionally
- [ ] **Commit to corrective actions** (with realistic timelines)
- [ ] **Thank auditor** for their time and feedback

---

## 8. Post-Audit Actions
## การดำเนินการหลังการตรวจสอบ

### Immediate Actions (Within 24 Hours) | การดำเนินการทันที (ภายใน 24 ชั่วโมง)

- [ ] **Debrief with team**
  - Review auditor findings
  - Discuss overall performance
  - Identify lessons learned

- [ ] **Document findings**
  - Create NC register
  - Assign owners for each NC

### Short-Term Actions (Within 30-90 Days) | การดำเนินการระยะสั้น (ภายใน 30-90 วัน)

- [ ] **Develop Corrective Action Plans (CAPs)** for all NCs
  - Root cause analysis
  - Corrective actions
  - Preventive actions
  - Timeline for completion
  - Responsible person

- [ ] **Implement corrective actions**
  - Address root causes, not just symptoms
  - Document evidence of implementation

- [ ] **Submit CAPs to CB**
  - Within required timeframe (typically 30-90 days)
  - Include: NC description, root cause, corrective action, evidence

### Long-Term Actions | การดำเนินการระยะยาว

- [ ] **CB reviews CAPs**
  - May request additional evidence or clarification

- [ ] **Certificate issuance** (if successful)
  - Celebrate! 🎉
  - Communicate to stakeholders

- [ ] **Surveillance audits** (annual)
  - Maintain ISMS throughout the year
  - Prepare for annual surveillance audits

---

## Critical Success Factors | ปัจจัยสำคัญต่อความสำเร็จ

### Top 10 Things Auditors Will Look For 🔴

1. **Management Commitment**
   - CEO signature on Information Security Policy
   - Active participation in Management Review

2. **ISMS Scope Clarity**
   - Clear definition: "Certogo LMS + Appman E-KYC integration"
   - Boundaries well-defined

3. **Risk Assessment Quality**
   - Comprehensive, including E-KYC provider risks
   - Current (within 12 months)
   - Treatment plans for high risks

4. **Statement of Applicability (SoA) Completeness**
   - All 93 Annex A controls addressed
   - Justifications for N/A controls
   - Implementation status accurate

5. **Internal Audit Evidence**
   - Conducted within 12 months
   - Covered all ISMS clauses and applicable controls
   - NCs closed or with CAPs

6. **Management Review Evidence**
   - Conducted within 12 months
   - CEO/top management attended
   - Covered: ISMS performance, risks, improvement

7. **E-KYC Provider Management** 🔴 **MOST CRITICAL FOR CERTOGO**
   - Security assessment of Appman
   - DPA with data retention and deletion clauses
   - Monitoring evidence (quarterly reports)
   - Change management procedure

8. **Biometric Data Protection** 🔴
   - Encryption (AES-256)
   - 30-day retention with automated deletion
   - Access control (who can access biometric data)
   - PDPA compliance

9. **Documented Procedures**
   - Backup, incident response, access control, change management
   - Evidence of use (not just shelf-ware)

10. **Continual Improvement**
    - Evidence of learning from incidents, audits, reviews
    - ISMS evolving, not static

---

## Common Pitfalls to Avoid | ข้อผิดพลาดที่พบบ่อยและต้องหลีกเลี่ยง

### ❌ Don't:

1. **Don't hide issues**
   - Auditors appreciate honesty and transparency

2. **Don't rely on "we plan to..."**
   - Auditors want evidence of implementation, not plans

3. **Don't have shelf-ware policies**
   - Policies must be implemented and used

4. **Don't ignore E-KYC provider security**
   - It's a critical dependency; auditors will scrutinize it

5. **Don't assume verbal agreements are enough**
   - Everything with Appman must be in writing (contracts, DPA)

6. **Don't forget about data deletion**
   - Biometric data retention is highly sensitive; auditors will verify

7. **Don't neglect training records**
   - All employees must have security awareness training

8. **Don't have outdated documents**
   - Policies, risk assessments must be current

9. **Don't lack evidence**
   - "Trust me" doesn't work; show proof

10. **Don't panic during audit**
    - Stay calm, professional, and cooperative

### ✅ Do:

1. **Be honest** about gaps and improvement plans
2. **Show evidence** of implementation (logs, screenshots, reports)
3. **Demonstrate maturity** of ISMS (not just compliance checkboxes)
4. **Highlight E-KYC provider management** as a strength
5. **Prepare thoroughly** using this checklist
6. **Involve the team** (not just CISO)
7. **Welcome feedback** as improvement opportunities
8. **Document everything** before, during, and after audit
9. **Follow up promptly** on corrective actions
10. **Celebrate success** when certified!

---

## Pre-Audit Self-Assessment Score | คะแนนการประเมินตนเองก่อนการตรวจสอบ

Use this to gauge readiness. **Target: ≥ 90% before scheduling certification audit.**

ใช้เพื่อวัดความพร้อม **เป้าหมาย: ≥ 90% ก่อนกำหนดเวลาการตรวจสอบเพื่อการรับรอง**

| Category | Items | Completed | Score |
|----------|-------|-----------|-------|
| Mandatory Documents (Clauses 4-10) | 30 | __ / 30 | __% |
| Annex A Evidence | 93 | __ / 93 | __% |
| E-KYC Provider Documentation 🔴 | 15 | __ / 15 | __% |
| Interview Preparation | 7 | __ / 7 | __% |
| Facility Preparation | 8 | __ / 8 | __% |
| **TOTAL** | **153** | **__ / 153** | **__%** |

**Scoring Guide** | **คู่มือการให้คะแนน**:
- **90-100%**: Ready for certification audit | พร้อมสำหรับการตรวจสอบเพื่อการรับรอง ✅
- **80-89%**: Minor gaps, address before audit | ช่องว่างเล็กน้อย แก้ไขก่อนการตรวจสอบ ⚠️
- **< 80%**: Significant gaps, postpone audit | ช่องว่างที่สำคัญ เลื่อนการตรวจสอบ ❌

---

## Contact Information | ข้อมูลติดต่อ

**During Audit** | **ระหว่างการตรวจสอบ**:

| Role | Name | Phone | Email |
|------|------|-------|-------|
| ISMS Coordinator | [TBD] | [TBD] | [TBD] |
| CISO | [TBD] | [TBD] | [TBD] |
| CTO | [TBD] | [TBD] | [TBD] |
| DPO | [TBD] | [TBD] | [TBD] |
| Facility Manager | [TBD] | [TBD] | [TBD] |
| IT Support | [TBD] | [TBD] | [TBD] |

**Certification Body (CB)** | **หน่วยรับรอง**:
- CB Name: [TBD]
- Lead Auditor: [TBD]
- CB Contact: [TBD]

---

## Final Checklist Summary | สรุปรายการตรวจสอบขั้นสุดท้าย

**One Week Before Audit** | **หนึ่งสัปดาห์ก่อนการตรวจสอบ**:
- [ ] All mandatory documents prepared and reviewed
- [ ] All evidence organized and accessible
- [ ] 🔴 E-KYC provider documentation complete (Appman certificates, DPA, reports)
- [ ] Interview participants confirmed and prepared
- [ ] Meeting room and facilities ready
- [ ] Internal audit NCs closed
- [ ] Management review completed
- [ ] Self-assessment score ≥ 90%

**Day Before Audit** | **วันก่อนการตรวจสอบ**:
- [ ] Final document check
- [ ] Test all demonstration systems
- [ ] Confirm attendees
- [ ] Print audit schedule
- [ ] Prepare emergency contact list
- [ ] Get good night's sleep! 😴

**Audit Day** | **วันตรวจสอบ**:
- [ ] Arrive early
- [ ] Set up meeting room
- [ ] Be professional, honest, and cooperative
- [ ] Take notes
- [ ] Stay calm and confident

**Post-Audit** | **หลังการตรวจสอบ**:
- [ ] Debrief with team
- [ ] Develop CAPs for NCs (if any)
- [ ] Submit CAPs to CB within required timeframe
- [ ] Implement corrective actions
- [ ] Await certificate! 🏆

---

**Good luck with your ISO 27001:2022 certification audit!**

**ขอให้โชคดีกับการตรวจสอบเพื่อการรับรอง ISO 27001:2022!**

---

**Document Version** | **เวอร์ชันเอกสาร**: 1.0
**Last Updated** | **อัปเดตล่าสุด**: 2025-01-20
**Prepared By** | **จัดทำโดย**: ISMS Coordination Team

**Approval** | **การอนุมัติ**:
- [ ] CISO
- [ ] Internal Auditor
