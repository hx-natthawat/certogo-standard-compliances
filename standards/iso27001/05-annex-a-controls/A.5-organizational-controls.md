# A.5 Organizational Controls | มาตรการควบคุมระดับองค์กร
# ISO 27001:2022 Implementation Guide for Certogo

## Document Information | ข้อมูลเอกสาร

**Organization** | **องค์กร**: Certogo Co., Ltd.
**Scope** | **ขอบเขต**: Certogo LMS Platform + Appman E-KYC Integration
**Standard** | **มาตรฐาน**: ISO/IEC 27001:2022
**Version** | **เวอร์ชัน**: 1.0
**Date** | **วันที่**: 2025-01-20
**Status** | **สถานะ**: Initial Draft | ร่างเอกสารเบื้องต้น

---

## ⚠️ Important Notice for E-KYC Integration | ประกาศสำคัญสำหรับการเชื่อมต่อ E-KYC

**Current E-KYC Provider** | **ผู้ให้บริการ E-KYC ปัจจุบัน**: Appman Co., Ltd.

🔴 **Critical Controls** marked with this symbol are **MANDATORY** when changing E-KYC providers.

Controls marked with 🔄 indicate **Shared Responsibility** between Certogo and the E-KYC provider.

---

## Table of Contents | สารบัญ

1. [A.5.1 Policies for Information Security](#a51-policies-for-information-security)
2. [A.5.2 Information Security Roles and Responsibilities](#a52-information-security-roles-and-responsibilities)
3. [A.5.3 Segregation of Duties](#a53-segregation-of-duties)
4. [A.5.4 Management Responsibilities](#a54-management-responsibilities)
5. [A.5.5 Contact with Authorities](#a55-contact-with-authorities)
6. [A.5.6 Contact with Special Interest Groups](#a56-contact-with-special-interest-groups)
7. [A.5.7 Threat Intelligence](#a57-threat-intelligence)
8. [A.5.8 Information Security in Project Management](#a58-information-security-in-project-management)
9. [A.5.9 Inventory of Information and Other Associated Assets](#a59-inventory-of-information-and-other-associated-assets)
10. [A.5.10 Acceptable Use of Information and Other Associated Assets](#a510-acceptable-use-of-information-and-other-associated-assets)
11. [A.5.11 Return of Assets](#a511-return-of-assets)
12. [A.5.12 Classification of Information](#a512-classification-of-information)
13. [A.5.13 Labelling of Information](#a513-labelling-of-information)
14. [A.5.14 Information Transfer](#a514-information-transfer)
15. [A.5.15 Access Control](#a515-access-control)
16. [A.5.16 Identity Management](#a516-identity-management)
17. [A.5.17 Authentication Information](#a517-authentication-information)
18. [A.5.18 Access Rights](#a518-access-rights)
19. [A.5.19 Information Security in Supplier Relationships 🔴](#a519-information-security-in-supplier-relationships-)
20. [A.5.20 Addressing Information Security within Supplier Agreements 🔴](#a520-addressing-information-security-within-supplier-agreements-)
21. [A.5.21 Managing Information Security in the ICT Supply Chain 🔄](#a521-managing-information-security-in-the-ict-supply-chain-)
22. [A.5.22 Monitoring, Review and Change Management of Supplier Services 🔴](#a522-monitoring-review-and-change-management-of-supplier-services-)
23. [A.5.23 Information Security for Use of Cloud Services 🔄](#a523-information-security-for-use-of-cloud-services-)

---

## A.5.1 Policies for Information Security
## นโยบายความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้**

### Control Objective | วัตถุประสงค์
To provide management direction and support for information security in accordance with business requirements and relevant laws and regulations.

เพื่อให้คำแนะนำและการสนับสนุนจากฝ่ายบริหารสำหรับความมั่นคงปลอดภัยสารสนเทศตามความต้องการทางธุรกิจและกฎหมายที่เกี่ยวข้อง

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Information Security Policy Structure | โครงสร้างนโยบาย

**Top-Level Policy** | **นโยบายระดับบนสุด**:
- **Information Security Policy** (ISP) | **นโยบายความมั่นคงปลอดภัยสารสนเทศ**
  - Approved by CEO | อนุมัติโดยประธานเจ้าหน้าที่บริหาร
  - Reviewed annually | ทบทวนทุกปี
  - Covers both LMS and E-KYC integration | ครอบคลุมทั้ง LMS และการเชื่อมต่อ E-KYC

**Supporting Policies** | **นโยบายสนับสนุน**:
1. **Access Control Policy** | นโยบายการควบคุมการเข้าถึง
2. **Data Classification Policy** | นโยบายการจัดชั้นความลับข้อมูล
3. **Acceptable Use Policy** (AUP) | นโยบายการใช้งานที่ยอมรับได้
4. **Supplier Security Policy** 🔴 | นโยบายความปลอดภัยของซัพพลายเออร์
5. **Incident Response Policy** | นโยบายการตอบสนองต่อเหตุการณ์
6. **Business Continuity Policy** | นโยบายความต่อเนื่องทางธุรกิจ
7. **PDPA Compliance Policy** | นโยบายการปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล

#### 2. E-KYC Integration Specific Policies | นโยบายเฉพาะการเชื่อมต่อ E-KYC

🔴 **Third-Party Service Integration Policy** | **นโยบายการเชื่อมต่อบริการบุคคลที่สาม**:

**Key Requirements** | **ข้อกำหนดหลัก**:
- All E-KYC providers must be ISO 27001 certified or equivalent
  - ผู้ให้บริการ E-KYC ทุกรายต้องได้รับการรับรอง ISO 27001 หรือเทียบเท่า
- Data Processing Agreement (DPA) mandatory before integration
  - ต้องมีสัญญาการประมวลผลข้อมูล (DPA) ก่อนการเชื่อมต่อ
- Biometric data retention limited to 30 days maximum
  - การเก็บรักษาข้อมูลชีวมิติไม่เกิน 30 วัน
- Provider must comply with Thai PDPA
  - ผู้ให้บริการต้องปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล

#### 3. Policy Communication | การสื่อสารนโยบาย

**Internal Communication** | **การสื่อสารภายใน**:
- All employees receive ISP during onboarding
  - พนักงานทุกคนได้รับนโยบายระหว่างการปฐมนิเทศ
- Annual security awareness training includes policy review
  - การอบรมความตระหนักรู้ประจำปีรวมถึงการทบทวนนโยบาย
- Policy updates communicated via email and intranet
  - การอัปเดตนโยบายสื่อสารผ่านอีเมลและอินทราเน็ต

**External Communication** | **การสื่อสารภายนอก**:
- Customers: Privacy Policy and Terms of Service
  - ลูกค้า: นโยบายความเป็นส่วนตัวและข้อกำหนดการให้บริการ
- Suppliers: Security requirements in contracts (including E-KYC providers)
  - ซัพพลายเออร์: ข้อกำหนดความปลอดภัยในสัญญา (รวมผู้ให้บริการ E-KYC)

#### 4. Policy Review and Updates | การทบทวนและปรับปรุงนโยบาย

**Regular Review** | **การทบทวนปกติ**:
- Annual review cycle | รอบการทบทวนประจำปี
- Management review approval | การอนุมัติจากการทบทวนของฝ่ายบริหาร

**Trigger-Based Review** | **การทบทวนตามเหตุการณ์**:
- Major security incidents | เหตุการณ์ด้านความปลอดภัยที่สำคัญ
- Regulatory changes | การเปลี่ยนแปลงกฎระเบียบ
- 🔴 **E-KYC provider change** | **การเปลี่ยนผู้ให้บริการ E-KYC**
- New service offerings | การเสนอบริการใหม่

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/policies/information-security-policy.pdf` - Main ISP document
- `/evidence/policies/supplier-security-policy.pdf` - Supplier security requirements
- `/evidence/policies/pdpa-compliance-policy.pdf` - PDPA compliance
- `/evidence/records/policy-approval-minutes.pdf` - Management approval records
- `/evidence/records/policy-communication-log.xlsx` - Policy distribution tracking

### Compliance References | การอ้างอิงการปฏิบัติตาม

- **ISO 27001:2022** Clause 5.2 - Policy
- **Thai PDPA** Section 25 - Data controller obligations
- **CSA-STAR** DSI-01 - Data Security & Information Lifecycle Management

---

## A.5.2 Information Security Roles and Responsibilities
## บทบาทและความรับผิดชอบด้านความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้**

### Control Objective | วัตถุประสงค์
To ensure that information security responsibilities are defined and assigned.

เพื่อให้แน่ใจว่าความรับผิดชอบด้านความมั่นคงปลอดภัยสารสนเทศได้รับการกำหนดและมอบหมาย

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Information Security Governance Structure | โครงสร้างการกำกับดูแล

```
Board of Directors | คณะกรรมการบริษัท
         ↓
Chief Executive Officer (CEO) | ประธานเจ้าหน้าที่บริหาร
         ↓
Information Security Committee | คณะกรรมการความมั่นคงปลอดภัยสารสนเทศ
    ↓           ↓           ↓
CISO        CTO         Legal/Compliance
    ↓
Security Team | ทีมความปลอดภัย
```

#### 2. Key Roles and Responsibilities | บทบาทและความรับผิดชอบหลัก

**Chief Information Security Officer (CISO)** | **ห้าหน้าที่ความมั่นคงปลอดภัยสารสนเทศหลัก**:
- Overall ISMS responsibility | ความรับผิดชอบ ISMS โดยรวม
- 🔴 **Approve security assessments for new E-KYC providers** | **อนุมัติการประเมินความปลอดภัยสำหรับผู้ให้บริการ E-KYC ใหม่**
- Manage security risk register | จัดการทะเบียนความเสี่ยงด้านความปลอดภัย
- Report to management on security posture | รายงานต่อฝ่ายบริหารเกี่ยวกับสถานะความปลอดภัย

**Chief Technology Officer (CTO)** | **หัวหน้าเจ้าหน้าที่เทคโนโลยี**:
- Infrastructure security | ความปลอดภัยของโครงสร้างพื้นฐาน
- 🔄 **E-KYC API integration security** | **ความปลอดภัยการเชื่อมต่อ API ของ E-KYC**
- Cloud security management | การจัดการความปลอดภัยคลาวด์
- Technical security controls implementation | การนำมาตรการควบคุมด้านเทคนิคไปใช้

**Data Protection Officer (DPO)** | **เจ้าหน้าที่คุ้มครองข้อมูลส่วนบุคคล**:
- PDPA compliance oversight | การกำกับดูแลการปฏิบัติตาม PDPA
- 🔴 **Biometric data protection monitoring** | **การติดตามการคุ้มครองข้อมูลชีวมิติ**
- Privacy impact assessments | การประเมินผลกระทบด้านความเป็นส่วนตัว
- Data subject rights management | การจัดการสิทธิของเจ้าของข้อมูล

**Security Operations Team** | **ทีมปฏิบัติการความปลอดภัย**:
- 24/7 security monitoring | การตรวจสอบความปลอดภัยตลอด 24 ชั่วโมง
- Incident response | การตอบสนองต่อเหตุการณ์
- Vulnerability management | การจัดการช่องโหว่
- Log analysis and SIEM | การวิเคราะห์บันทึกและ SIEM

**Development Team** | **ทีมพัฒนา**:
- Secure coding practices | แนวทางการเขียนโค้ดที่ปลอดภัย
- Security testing before deployment | การทดสอบความปลอดภัยก่อนการใช้งานจริง
- 🔄 **E-KYC integration code security** | **ความปลอดภัยของโค้ดเชื่อมต่อ E-KYC**

**Supplier Management Team** 🔴 | **ทีมบริหารซัพพลายเออร์** 🔴:
- **E-KYC provider security assessment** | **การประเมินความปลอดภัยของผู้ให้บริการ E-KYC**
- **Supplier performance monitoring** | **การติดตามประสิทธิภาพของซัพพลายเออร์**
- **Contract compliance verification** | **การตรวจสอบการปฏิบัติตามสัญญา**

#### 3. RACI Matrix for E-KYC Security | เมทริกซ์ RACI สำหรับความปลอดภัย E-KYC

| Activity | CISO | CTO | DPO | Supplier Mgmt | Dev Team |
|----------|------|-----|-----|---------------|----------|
| E-KYC provider security assessment | **A** | **C** | **C** | **R** | **I** |
| API integration security review | **A** | **R** | **I** | **C** | **C** |
| Biometric data protection | **A** | **C** | **R** | **I** | **C** |
| Provider change approval | **A** | **C** | **C** | **R** | **I** |
| Incident response (E-KYC) | **R** | **C** | **C** | **I** | **C** |

**Legend**: R = Responsible, A = Accountable, C = Consulted, I = Informed

#### 4. Third-Party Responsibilities | ความรับผิดชอบของบุคคลที่สาม

🔄 **E-KYC Provider (Appman)** | **ผู้ให้บริการ E-KYC (Appman)**:
- Maintain ISO 27001 certification | รักษาการรับรอง ISO 27001
- Protect biometric data | ปกป้องข้อมูลชีวมิติ
- Incident notification within 24 hours | แจ้งเหตุการณ์ภายใน 24 ชั่วโมง
- Quarterly security reports to Certogo | รายงานความปลอดภัยรายไตรมาสให้ Certogo
- Data deletion compliance | การปฏิบัติตามการลบข้อมูล

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/policies/roles-and-responsibilities-matrix.xlsx` - RACI matrix
- `/evidence/records/job-descriptions/` - Security role job descriptions
- `/evidence/records/delegation-of-authority.pdf` - Formal delegation documents
- `/evidence/records/supplier-responsibilities-agreement.pdf` - E-KYC provider SLA

---

## A.5.19 Information Security in Supplier Relationships 🔴
## ความมั่นคงปลอดภัยสารสนเทศในความสัมพันธ์กับซัพพลายเออร์

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้** 🔴 **CRITICAL FOR E-KYC**

### Control Objective | วัตถุประสงค์
To ensure protection of the organization's assets that are accessible by suppliers.

เพื่อให้แน่ใจว่าทรัพย์สินขององค์กรที่ซัพพลายเออร์สามารถเข้าถึงได้มีการปกป้อง

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. E-KYC Provider Security Assessment Process 🔴
#### กระบวนการประเมินความปลอดภัยของผู้ให้บริการ E-KYC

**MANDATORY for all E-KYC providers** (Current: Appman, Future: Any new provider)

**บังคับสำหรับผู้ให้บริการ E-KYC ทุกราย** (ปัจจุบัน: Appman, อนาคต: ผู้ให้บริการใหม่ใดๆ)

##### Phase 1: Initial Screening | การคัดกรองเบื้องต้น

**Minimum Requirements** | **ข้อกำหนดขั้นต่ำ**:
- [ ] ISO 27001 certification (or equivalent SOC 2 Type II) | การรับรอง ISO 27001 (หรือเทียบเท่า SOC 2 Type II)
- [ ] PDPA compliance demonstration | การแสดงการปฏิบัติตาม PDPA
- [ ] Biometric data handling experience | ประสบการณ์การจัดการข้อมูลชีวมิติ
- [ ] Thailand data residency capability | ความสามารถในการจัดเก็บข้อมูลในประเทศไทย
- [ ] 99.9% SLA uptime guarantee | การรับประกัน SLA uptime 99.9%
- [ ] 24/7 incident response capability | ความสามารถในการตอบสนองเหตุการณ์ 24/7

**Scoring Criteria** | **เกณฑ์การให้คะแนน**:
- Pass: ≥ 90% of mandatory requirements met
- Fail: < 90% (cannot proceed to Phase 2)

##### Phase 2: Detailed Security Assessment | การประเมินความปลอดภัยโดยละเอียด

**Security Questionnaire** | **แบบสอบถามความปลอดภัย** (100+ questions):

1. **Data Protection** | **การป้องกันข้อมูล**:
   - Biometric data encryption at rest (AES-256 minimum)
   - Encryption in transit (TLS 1.3 minimum)
   - Key management procedures
   - Data deletion procedures and timelines
   - Backup and recovery procedures

2. **Access Control** | **การควบคุมการเข้าถึง**:
   - Multi-factor authentication (MFA) for all admin access
   - Principle of least privilege implementation
   - Access review frequency
   - Privileged access management

3. **Infrastructure Security** | **ความปลอดภัยโครงสร้างพื้นฐาน**:
   - Cloud provider (AWS/Azure/GCP)
   - Network segmentation
   - Firewall and IDS/IPS
   - DDoS protection
   - Vulnerability management program

4. **Compliance & Certifications** | **การปฏิบัติตามและการรับรอง**:
   - ISO 27001 certificate (valid copy required)
   - PDPA compliance documentation
   - Penetration testing reports (within last 12 months)
   - External audit reports

5. **Incident Management** | **การจัดการเหตุการณ์**:
   - Incident response plan
   - Notification procedures and timelines
   - Historical incident records
   - Lessons learned process

6. **Business Continuity** | **ความต่อเนื่องทางธุรกิจ**:
   - Disaster recovery plan
   - RTO (Recovery Time Objective): < 4 hours
   - RPO (Recovery Point Objective): < 1 hour
   - Backup procedures and testing

##### Phase 3: On-Site/Virtual Audit | การตรวจสอบแบบ On-Site/Virtual

**Audit Scope** | **ขอบเขตการตรวจสอบ**:
- Data center tour (physical or virtual)
- Review of security controls
- Interview with security team
- Review of access logs
- Penetration testing reports review

**Audit Duration** | **ระยะเวลาการตรวจสอบ**: 2-3 days

##### Phase 4: Risk Assessment | การประเมินความเสี่ยง

**Risk Categories** | **หมวดความเสี่ยง**:
- Data breach risk | ความเสี่ยงการรั่วไหลของข้อมูล
- Service availability risk | ความเสี่ยงด้านความพร้อมใช้งานของบริการ
- Compliance risk | ความเสี่ยงด้านการปฏิบัติตาม
- Vendor lock-in risk | ความเสี่ยงการผูกติดกับผู้ให้บริการ
- Financial stability risk | ความเสี่ยงด้านเสถียรภาพทางการเงิน

**Risk Scoring** | **การให้คะแนนความเสี่ยง**:
- Low: 1-3 | ต่ำ
- Medium: 4-6 | กลาง
- High: 7-9 | สูง
- Critical: 10 | วิกฤต

**Acceptance Criteria** | **เกณฑ์การยอมรับ**:
- No Critical risks | ไม่มีความเสี่ยงวิกฤต
- High risks must have mitigation plans | ความเสี่ยงสูงต้องมีแผนลดความเสี่ยง

##### Phase 5: Contract Negotiation | การเจรจาสัญญา

See Control A.5.20 for contract requirements.

#### 2. Supplier Classification | การจัดประเภทซัพพลายเออร์

**Tier 1 - Critical Suppliers** 🔴 | **ซัพพลายเออร์วิกฤต**:
- **E-KYC providers** (Appman) | ผู้ให้บริการ E-KYC
- Cloud infrastructure providers (AWS/Azure/GCP)
- **Assessment**: Full assessment every 12 months
- **Monitoring**: Quarterly security reports required

**Tier 2 - Important Suppliers** | **ซัพพลายเออร์สำคัญ**:
- Email service providers
- Payment gateways
- **Assessment**: Every 24 months
- **Monitoring**: Annual reports

**Tier 3 - Standard Suppliers** | **ซัพพลายเออร์มาตรฐาน**:
- Office software vendors
- Marketing tools
- **Assessment**: Risk-based
- **Monitoring**: Self-attestation

#### 3. Supplier Registry | ทะเบียนซัพพลายเออร์

**Mandatory Information** | **ข้อมูลบังคับ**:
- Supplier name and contact | ชื่อและข้อมูลติดต่อ
- Service provided | บริการที่ให้
- Data access level | ระดับการเข้าถึงข้อมูล
- Classification tier | ระดับการจัดประเภท
- Last assessment date | วันที่ประเมินล่าสุด
- Next assessment due | วันที่ต้องประเมินครั้งต่อไป
- Security certification status | สถานะการรับรองด้านความปลอดภัย
- Contract expiry date | วันหมดอายุสัญญา

**Current E-KYC Provider Record** | **บันทึกผู้ให้บริการ E-KYC ปัจจุบัน**:

```yaml
Supplier Name: Appman Co., Ltd. | บริษัท แอพแมน จำกัด
Service: E-KYC Identity Verification
Tier: Tier 1 - Critical 🔴
Data Access: Biometric data, ID card data, facial images
ISO 27001: Valid until [DATE]
PDPA Compliant: Yes
Last Assessment: [DATE]
Next Assessment: [DATE]
Contract Expiry: [DATE]
Performance Score: [SCORE]/100
```

#### 4. E-KYC Provider Change Procedure 🔴
#### ขั้นตอนการเปลี่ยนผู้ให้บริการ E-KYC

**When to Trigger** | **เมื่อไรควรดำเนินการ**:
- Contract expiry | สัญญาหมดอายุ
- Performance issues | ปัญหาด้านประสิทธิภาพ
- Security incidents | เหตุการณ์ด้านความปลอดภัย
- Compliance failures | ความล้มเหลวในการปฏิบัติตาม
- Cost optimization | การปรับปรุงต้นทุน

**Change Process** | **กระบวนการเปลี่ยน**:

**Step 1**: New provider assessment (Phase 1-5 above) - 8-12 weeks
**Step 2**: Parallel testing - 4 weeks
**Step 3**: Gradual migration - 2-4 weeks
**Step 4**: Old provider data deletion - 30 days
**Step 5**: Post-migration review - 2 weeks

**Total Duration** | **ระยะเวลารวม**: 14-22 weeks

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/records/supplier-security-assessment/appman-assessment-2025.pdf`
- `/evidence/records/supplier-registry.xlsx`
- `/evidence/policies/supplier-security-policy.pdf`
- `/evidence/records/appman-iso27001-certificate.pdf`
- `/evidence/records/appman-pdpa-compliance.pdf`
- `/evidence/procedures/supplier-assessment-checklist.xlsx`

### Compliance References | การอ้างอิงการปฏิบัติตาม

- **ISO 27001:2022** A.5.19
- **ISO 27002:2022** Section 5.19
- **Thai PDPA** Section 26 - Data processor requirements

---

## A.5.20 Addressing Information Security within Supplier Agreements 🔴
## การจัดการความมั่นคงปลอดภัยสารสนเทศในข้อตกลงกับซัพพลายเออร์

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้** 🔴 **CRITICAL FOR E-KYC**

### Control Objective | วัตถุประสงค์
To establish and agree on information security requirements with each supplier.

เพื่อจัดทำและตกลงในข้อกำหนดความมั่นคงปลอดภัยสารสนเทศกับซัพพลายเออร์แต่ละราย

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. E-KYC Provider Contract Requirements 🔴
#### ข้อกำหนดสัญญาผู้ให้บริการ E-KYC

**MANDATORY Contract Clauses for E-KYC Providers**:

##### A. Data Protection Agreement (DPA) | ข้อตกลงการคุ้มครองข้อมูล

**Required Clauses** | **ข้อบังคับ**:

1. **Data Processing Scope** | **ขอบเขตการประมวลผลข้อมูล**:
   ```
   Supplier shall process the following personal data on behalf of Certogo:
   ซัพพลายเออร์จะประมวลผลข้อมูลส่วนบุคคลต่อไปนี้ในนามของ Certogo:

   - Biometric data (facial images) | ข้อมูลชีวมิติ (ภาพใบหน้า)
   - Thai National ID card data | ข้อมูลบัตรประชาชน
   - Passport data | ข้อมูลหนังสือเดินทาง
   - Driver's license data | ข้อมูลใบขับขี่
   - Liveness detection results | ผลการตรวจสอบความเป็นมนุษย์
   ```

2. **Purpose Limitation** | **การจำกัดวัตถุประสงค์**:
   ```
   Data shall be processed solely for identity verification purposes.
   ข้อมูลจะถูกประมวลผลเพื่อวัตถุประสงค์การยืนยันตัวตนเท่านั้น

   Supplier SHALL NOT:
   ซัพพลายเออร์ห้าม:
   - Use data for marketing | ใช้ข้อมูลเพื่อการตลาด
   - Share data with third parties | แบ่งปันข้อมูลกับบุคคลที่สาม
   - Train AI models using customer data | ฝึกโมเดล AI โดยใช้ข้อมูลลูกค้า
   - Retain data beyond agreed period | เก็บรักษาข้อมูลเกินกว่าระยะเวลาที่ตกลง
   ```

3. **Data Retention and Deletion** 🔴 | **การเก็บรักษาและลบข้อมูล**:
   ```
   Biometric Data Retention:
   การเก็บรักษาข้อมูลชีวมิติ:
   - Verification result data: 90 days | ข้อมูลผลการตรวจสอบ: 90 วัน
   - Raw facial images: 30 days maximum | ภาพใบหน้าดิบ: ไม่เกิน 30 วัน
   - Liveness detection images: 30 days maximum | ภาพตรวจสอบความเป็นมนุษย์: ไม่เกิน 30 วัน

   Automatic deletion after retention period.
   ลบอัตโนมัติหลังจากระยะเวลาเก็บรักษา

   Upon contract termination:
   เมื่อสัญญาสิ้นสุด:
   - All data deleted within 30 days | ข้อมูลทั้งหมดถูกลบภายใน 30 วัน
   - Certificate of deletion provided | ออกใบรับรองการลบข้อมูล
   - Deletion verification audit allowed | อนุญาตให้ตรวจสอบการลบข้อมูล
   ```

4. **Data Localization** | **การจัดเก็บข้อมูลในประเทศ**:
   ```
   All biometric data must be stored within Thailand data centers.
   ข้อมูลชีวมิติทั้งหมดต้องจัดเก็บภายในศูนย์ข้อมูลในประเทศไทย

   Cross-border transfer prohibited without written consent.
   ห้ามถ่ายโอนข้อมูลข้ามพรมแดนโดยไม่ได้รับความยินยอมเป็นลายลักษณ์อักษร
   ```

5. **Sub-processing** | **การประมวลผลโดยผู้รับช่วง**:
   ```
   Supplier must obtain prior written approval for any sub-processors.
   ซัพพลายเออร์ต้องได้รับการอนุมัติเป็นลายลักษณ์อักษรล่วงหน้าสำหรับผู้ประมวลผลช่วงใดๆ

   Sub-processors must meet same security requirements.
   ผู้ประมวลผลช่วงต้องมีข้อกำหนดความปลอดภัยเท่าเทียมกัน
   ```

##### B. Security Requirements | ข้อกำหนดความปลอดภัย

1. **Encryption** | **การเข้ารหัส**:
   ```
   - Data at rest: AES-256 minimum | ข้อมูลแบบคงที่: AES-256 อย่างน้อย
   - Data in transit: TLS 1.3 minimum | ข้อมูลระหว่างส่ง: TLS 1.3 อย่างน้อย
   - API authentication: OAuth 2.0 + JWT | การยืนยันตัวตน API: OAuth 2.0 + JWT
   - Key rotation: Every 90 days | การหมุนเวียนกุญแจ: ทุก 90 วัน
   ```

2. **Access Control** | **การควบคุมการเข้าถึง**:
   ```
   - MFA mandatory for all administrative access | บังคับ MFA สำหรับการเข้าถึงระดับผู้ดูแลระบบทั้งหมด
   - Role-based access control (RBAC) | การควบคุมการเข้าถึงตามบทบาท
   - Access review quarterly | ทบทวนการเข้าถึงทุกไตรมาส
   - Immediate revocation upon employee termination | เพิกถอนการเข้าถึงทันทีเมื่อพนักงานออก
   ```

3. **Monitoring and Logging** | **การตรวจสอบและบันทึก**:
   ```
   - 24/7 security monitoring | การตรวจสอบความปลอดภัยตลอด 24/7
   - Log retention: 12 months minimum | เก็บบันทึก: ขั้นต่ำ 12 เดือน
   - Real-time alerting for security events | การแจ้งเตือนแบบเรียลไทม์สำหรับเหตุการณ์ความปลอดภัย
   - API access logs available to Certogo | บันทึกการเข้าถึง API พร้อมให้ Certogo เข้าถึง
   ```

##### C. Incident Management | การจัดการเหตุการณ์

1. **Incident Notification** 🔴 | **การแจ้งเตือนเหตุการณ์**:
   ```
   Notification Timeline:
   ระยะเวลาแจ้งเตือน:

   - Data breach involving biometric data: 4 hours | การรั่วไหลของข้อมูลชีวมิติ: 4 ชั่วโมง
   - Security incident: 24 hours | เหตุการณ์ความปลอดภัย: 24 ชั่วโมง
   - Service outage: 2 hours | บริการขัดข้อง: 2 ชั่วโมง
   - Compliance violation: 24 hours | การละเมิดการปฏิบัติตาม: 24 ชั่วโมง
   ```

2. **Incident Response** | **การตอบสนองเหตุการณ์**:
   ```
   - Joint incident response team | ทีมตอบสนองเหตุการณ์ร่วม
   - Root cause analysis within 72 hours | การวิเคราะห์สาเหตุภายใน 72 ชั่วโมง
   - Remediation plan within 5 business days | แผนแก้ไขภายใน 5 วันทำการ
   - Lessons learned documentation | เอกสารบทเรียนที่ได้เรียนรู้
   ```

##### D. Compliance and Audit Rights | การปฏิบัติตามและสิทธิ์การตรวจสอบ

1. **Certifications** | **การรับรอง**:
   ```
   Supplier must maintain:
   ซัพพลายเออร์ต้องรักษา:

   - ISO 27001 certification (or SOC 2 Type II) | การรับรอง ISO 27001 (หรือ SOC 2 Type II)
   - PDPA compliance | การปฏิบัติตาม PDPA
   - Annual penetration testing | การทดสอบเจาะระบบประจำปี

   Certogo has the right to review all certificates.
   Certogo มีสิทธิ์ตรวจสอบใบรับรองทั้งหมด
   ```

2. **Audit Rights** | **สิทธิ์การตรวจสอบ**:
   ```
   Certogo reserves the right to:
   Certogo สงวนสิทธิ์ในการ:

   - Annual on-site/virtual audit | ตรวจสอบแบบ on-site/virtual ประจำปี
   - Request security documentation | ขอเอกสารความปลอดภัย
   - Review access logs | ตรวจสอบบันทึกการเข้าถึง
   - Conduct data deletion verification | ตรวจสอบการลบข้อมูล
   - Third-party audit at Certogo's expense | ตรวจสอบโดยบุคคลที่สามโดย Certogo เป็นผู้รับผิดชอบค่าใช้จ่าย
   ```

3. **Reporting** | **การรายงาน**:
   ```
   Quarterly Security Reports:
   รายงานความปลอดภัยรายไตรมาส:

   - Security incidents summary | สรุปเหตุการณ์ความปลอดภัย
   - Performance metrics (uptime, latency) | ตัวชี้วัดประสิทธิภาพ (uptime, latency)
   - Compliance status | สถานะการปฏิบัติตาม
   - Changes to security controls | การเปลี่ยนแปลงมาตรการควบคุมความปลอดภัย
   ```

##### E. Service Level Agreement (SLA) | ข้อตกลงระดับบริการ

1. **Availability** | **ความพร้อมใช้งาน**:
   ```
   - Uptime: 99.9% monthly | Uptime: 99.9% ต่อเดือน
   - Planned maintenance window: Max 4 hours/month | หน้าต่างบำรุงรักษาที่วางแผน: สูงสุด 4 ชั่วโมง/เดือน
   - Advance notice: 7 days for maintenance | แจ้งล่วงหน้า: 7 วันสำหรับการบำรุงรักษา
   ```

2. **Performance** | **ประสิทธิภาพ**:
   ```
   - API response time: < 500ms (95th percentile) | เวลาตอบสนอง API: < 500ms (95th percentile)
   - Verification accuracy: > 98% | ความแม่นยำในการตรวจสอบ: > 98%
   - False positive rate: < 1% | อัตราผลบวกเท็จ: < 1%
   ```

3. **Penalties** | **ค่าปรับ**:
   ```
   - Uptime < 99.9%: 10% monthly fee credit | Uptime < 99.9%: คืนเงิน 10% ของค่าบริการรายเดือน
   - Data breach: Up to 100% annual contract value | การรั่วไหลของข้อมูล: สูงสุด 100% ของมูลค่าสัญญาต่อปี
   - Late incident notification: 5% per day late | แจ้งเตือนเหตุการณ์ล่าช้า: 5% ต่อวันที่ล่าช้า
   ```

##### F. Contract Termination | การสิ้นสุดสัญญา

1. **Termination Notice** | **การแจ้งเตือนการสิ้นสุด**:
   ```
   - Standard notice: 90 days | แจ้งเตือนมาตรฐาน: 90 วัน
   - Immediate termination for cause:
     การสิ้นสุดทันทีเนื่องจาก:
     - Material breach | การละเมิดสาระสำคัญ
     - Data breach | การรั่วไหลของข้อมูล
     - Insolvency | การล้มละลาย
     - Loss of critical certifications | การสูญเสียการรับรองที่สำคัญ
   ```

2. **Transition Support** 🔴 | **การสนับสนุนการเปลี่ยนผ่าน**:
   ```
   Upon termination, Supplier must:
   เมื่อสัญญาสิ้นสุด ซัพพลายเออร์ต้อง:

   - Continue service during transition period (30-90 days)
     ให้บริการต่อระหว่างระยะเปลี่ยนผ่าน (30-90 วัน)
   - Provide API documentation and integration support
     จัดเตรียมเอกสาร API และการสนับสนุนการเชื่อมต่อ
   - Return all data in agreed format
     ส่งคืนข้อมูลทั้งหมดในรูปแบบที่ตกลง
   - Delete all retained data within 30 days
     ลบข้อมูลที่เก็บรักษาทั้งหมดภายใน 30 วัน
   - Provide certificate of deletion
     ออกใบรับรองการลบข้อมูล
   - Revoke all API access credentials
     เพิกถอนข้อมูลประจำตัวการเข้าถึง API ทั้งหมด
   ```

#### 2. Contract Review Process | กระบวนการทบทวนสัญญา

**Annual Contract Review** | **การทบทวนสัญญาประจำปี**:
- Legal team review | ทีมกฎหมายทบทวน
- Security team review | ทีมความปลอดภัยทบทวน
- DPO review for data protection clauses | DPO ทบทวนข้อกำหนดการคุ้มครองข้อมูล
- Finance review for pricing | ทีมการเงินทบทวนราคา

**Amendment Triggers** | **การกระตุ้นให้แก้ไข**:
- Regulatory changes (e.g., new PDPA requirements)
- Security incidents
- Service performance issues
- New services or features

#### 3. Template Contracts | แม่แบบสัญญา

**E-KYC Provider Service Agreement Template** 🔴:
- Location: `/templates/contracts/ekyc-service-agreement-template.docx`
- Includes all clauses above
- Legal review stamp required
- CISO approval required

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/contracts/appman-service-agreement.pdf` - Current E-KYC provider contract
- `/evidence/contracts/appman-dpa.pdf` - Data Processing Agreement
- `/evidence/records/contract-review-log.xlsx` - Contract review records
- `/templates/contracts/ekyc-service-agreement-template.docx` - Template for new providers
- `/evidence/records/appman-sla-compliance-reports/` - Quarterly SLA reports

### Compliance References | การอ้างอิงการปฏิบัติตาม

- **ISO 27001:2022** A.5.20
- **ISO 27002:2022** Section 5.20
- **Thai PDPA** Section 26 - Data processor agreements
- **Thai PDPA** Section 27 - Consent requirements for cross-border transfer

---

## A.5.22 Monitoring, Review and Change Management of Supplier Services 🔴
## การตรวจสอบ ทบทวน และการจัดการการเปลี่ยนแปลงของบริการซัพพลายเออร์

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้** 🔴 **CRITICAL FOR E-KYC PROVIDER CHANGES**

### Control Objective | วัตถุประสงค์
To ensure that the agreed service delivery by suppliers is maintained, and that changes to service delivery are managed.

เพื่อให้แน่ใจว่าการส่งมอบบริการที่ตกลงกับซัพพลายเออร์ได้รับการรักษาไว้ และการเปลี่ยนแปลงการส่งมอบบริการได้รับการจัดการ

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. E-KYC Provider Monitoring Program 🔴
#### โปรแกรมติดตามผู้ให้บริการ E-KYC

##### A. Continuous Monitoring | การติดตามอย่างต่อเนื่อง

**Real-Time Monitoring** | **การติดตามแบบเรียลไทม์**:
```
Metrics Monitored 24/7:
ตัวชี้วัดที่ติดตามตลอด 24/7:

- API availability | ความพร้อมใช้งาน API
- Response time (target: < 500ms) | เวลาตอบสนอง (เป้าหมาย: < 500ms)
- Error rate (target: < 0.1%) | อัตราข้อผิดพลาด (เป้าหมาย: < 0.1%)
- Verification accuracy | ความแม่นยำในการตรวจสอบ
- Rate limiting compliance | การปฏิบัติตามการจำกัดอัตรา
```

**Dashboard URL**: `https://monitoring.certogo.com/suppliers/ekyc`

**Alert Thresholds** | **เกณฑ์การแจ้งเตือน**:
- API downtime > 5 minutes → Immediate alert to on-call engineer
- Response time > 1 second → Warning to security team
- Error rate > 1% → Escalate to CISO
- Accuracy drop > 2% → Escalate to CTO

##### B. Periodic Reviews | การทบทวนตามระยะเวลา

**Monthly Performance Review** | **การทบทวนประสิทธิภาพรายเดือน**:
- SLA compliance check | การตรวจสอบการปฏิบัติตาม SLA
- Performance trends analysis | การวิเคราะห์แนวโน้มประสิทธิภาพ
- Incident summary | สรุปเหตุการณ์
- Cost analysis | การวิเคราะห์ต้นทุน

**Quarterly Security Review** 🔴 | **การทบทวนความปลอดภัยรายไตรมาส**:

**Agenda** | **วาระ**:
1. Security incidents review | ทบทวนเหตุการณ์ความปลอดภัย
2. Certificate expiry check (ISO 27001, SSL) | ตรวจสอบวันหมดอายุใบรับรอง
3. Access rights review | ทบทวนสิทธิ์การเข้าถึง
4. Compliance status (PDPA, ISO 27001) | สถานะการปฏิบัติตาม
5. Vulnerability disclosures | การเปิดเผยช่องโหว่
6. Penetration testing results | ผลการทดสอบเจาะระบบ
7. Changes to security controls | การเปลี่ยนแปลงมาตรการควบคุมความปลอดภัย

**Required Documents from Supplier** | **เอกสารที่ต้องการจากซัพพลายเออร์**:
- Quarterly security report | รายงานความปลอดภัยรายไตรมาส
- Updated risk assessment | การประเมินความเสี่ยงที่อัปเดต
- Incident log | บันทึกเหตุการณ์
- Change log | บันทึกการเปลี่ยนแปลง

**Annual Audit** | **การตรวจสอบประจำปี**:
- Full security assessment (as per A.5.19) | การประเมินความปลอดภัยแบบเต็มรูปแบบ (ตาม A.5.19)
- Contract compliance review | การทบทวนการปฏิบัติตามสัญญา
- Financial stability check | การตรวจสอบเสถียรภาพทางการเงิน
- Alternative provider market research | การวิจัยตลาดผู้ให้บริการทางเลือก

#### 2. Change Management for E-KYC Services 🔴
#### การจัดการการเปลี่ยนแปลงสำหรับบริการ E-KYC

##### A. Supplier-Initiated Changes | การเปลี่ยนแปลงที่ซัพพลายเออร์เริ่ม

**Types of Changes Requiring Notification** | **ประเภทการเปลี่ยนแปลงที่ต้องแจ้งเตือน**:

🔴 **Critical Changes** (30-day advance notice required):
- API breaking changes | การเปลี่ยนแปลง API ที่ทำให้เกิดความไม่เข้ากัน
- Data storage location changes | การเปลี่ยนแปลงสถานที่จัดเก็บข้อมูล
- Sub-processor additions | การเพิ่มผู้ประมวลผลช่วง
- Security control changes | การเปลี่ยนแปลงมาตรการควบคุมความปลอดภัย
- Ownership or merger/acquisition | การเปลี่ยนแปลงความเป็นเจ้าของหรือการควบรวมกิจการ

**Medium Changes** (14-day advance notice):
- API version updates (backwards compatible) | การอัปเดตเวอร์ชัน API (เข้ากันได้แบบย้อนหลัง)
- Feature additions | การเพิ่มคุณสมบัติ
- Pricing changes | การเปลี่ยนแปลงราคา
- Support contact changes | การเปลี่ยนแปลงช่องทางติดต่อสนับสนุน

**Low Changes** (7-day notice):
- Documentation updates | การอัปเดตเอกสาร
- Minor bug fixes | การแก้ไขข้อบกพร่องเล็กน้อย
- Performance improvements | การปรับปรุงประสิทธิภาพ

**Change Approval Process** | **กระบวนการอนุมัติการเปลี่ยนแปลง**:

```
1. Supplier submits change request
   ซัพพลายเออร์ส่งคำขอเปลี่ยนแปลง
   ↓
2. CTO reviews technical impact
   CTO ทบทวนผลกระทบทางเทคนิค
   ↓
3. CISO reviews security impact (for critical changes)
   CISO ทบทวนผลกระทบด้านความปลอดภัย (สำหรับการเปลี่ยนแปลงที่สำคัญ)
   ↓
4. DPO reviews data protection impact
   DPO ทบทวนผลกระทบด้านการคุ้มครองข้อมูล
   ↓
5. Testing in staging environment
   ทดสอบในสภาพแวดล้อม staging
   ↓
6. Approval or rejection
   อนุมัติหรือปฏิเสธ
   ↓
7. Implementation with rollback plan
   การดำเนินการพร้อมแผนย้อนกลับ
```

##### B. Certogo-Initiated Change: E-KYC Provider Migration 🔴
##### การเปลี่ยนแปลงที่ Certogo เริ่ม: การโยกย้ายผู้ให้บริการ E-KYC

**FULL PROCEDURE FOR CHANGING E-KYC PROVIDER**

This is the **CRITICAL** procedure when Certogo decides to change from one E-KYC provider (e.g., Appman) to another.

นี่คือขั้นตอน **สำคัญยิ่ง** เมื่อ Certogo ตัดสินใจเปลี่ยนจากผู้ให้บริการ E-KYC รายหนึ่ง (เช่น Appman) ไปอีกรายหนึ่ง

---

#### **PHASE 1: Pre-Change Planning** (Weeks 1-8)
#### **ระยะที่ 1: การวางแผนก่อนการเปลี่ยนแปลง** (สัปดาห์ที่ 1-8)

**Week 1-2: New Provider Selection** | **สัปดาห์ที่ 1-2: การเลือกผู้ให้บริการใหม่**

**Step 1.1**: Conduct market research for alternative E-KYC providers
**Step 1.2**: Perform initial screening (as per A.5.19 Phase 1)
**Step 1.3**: Request proposals from shortlisted providers (minimum 3)

**Evaluation Criteria** | **เกณฑ์การประเมิน**:
```
Technical Compatibility (30 points):
ความเข้ากันได้ทางเทคนิค (30 คะแนน):
- API similarity to current provider | ความคล้ายคลึง API กับผู้ให้บริการปัจจุบัน
- SDKs and integration support | SDKs และการสนับสนุนการเชื่อมต่อ
- Documentation quality | คุณภาพเอกสาร
- Migration support offered | การสนับสนุนการโยกย้ายที่เสนอ

Security & Compliance (30 points):
ความปลอดภัยและการปฏิบัติตาม (30 คะแนน):
- ISO 27001 certified | ได้รับการรับรอง ISO 27001
- PDPA compliance | การปฏิบัติตาม PDPA
- Data localization (Thailand) | การจัดเก็บข้อมูลในประเทศไทย
- Penetration testing results | ผลการทดสอบเจาะระบบ

Performance (20 points):
ประสิทธิภาพ (20 คะแนน):
- Verification accuracy | ความแม่นยำในการตรวจสอบ
- Response time | เวลาตอบสนอง
- Uptime SLA | SLA ความพร้อมใช้งาน

Cost (10 points):
ต้นทุน (10 คะแนน):
- Per-transaction pricing | ราคาต่อธุรกรรม
- Setup fees | ค่าติดตั้ง
- Migration support costs | ค่าใช้จ่ายสนับสนุนการโยกย้าย

Support (10 points):
การสนับสนุน (10 คะแนน):
- 24/7 support availability | ความพร้อมให้บริการ 24/7
- Thai language support | การสนับสนุนภาษาไทย
- Escalation procedures | ขั้นตอนการส่งต่อปัญหา
```

**Step 1.4**: Select finalist (score ≥ 80/100 required)

---

**Week 3-6: Security Assessment** | **สัปดาห์ที่ 3-6: การประเมินความปลอดภัย**

**Step 2.1**: Conduct full security assessment (as per A.5.19 Phases 2-5)
**Step 2.2**: Review security questionnaire (100+ questions)
**Step 2.3**: Virtual/on-site audit
**Step 2.4**: Risk assessment
**Step 2.5**: Gap analysis vs. current provider

**Required Outputs** | **ผลลัพธ์ที่ต้องการ**:
- Security assessment report | รายงานการประเมินความปลอดภัย
- Risk register with mitigation plans | ทะเบียนความเสี่ยงพร้อมแผนลดความเสี่ยง
- Gap analysis document | เอกสารการวิเคราะห์ช่องว่าง
- CISO approval | การอนุมัติจาก CISO

---

**Week 7-8: Contract Negotiation** | **สัปดาห์ที่ 7-8: การเจรจาสัญญา**

**Step 3.1**: Draft service agreement (use template from A.5.20)
**Step 3.2**: Negotiate Data Processing Agreement (DPA)
**Step 3.3**: Define SLA terms
**Step 3.4**: Agree on transition support terms

**Critical Contract Clauses** | **ข้อกำหนดสัญญาที่สำคัญ**:
- [ ] Biometric data retention: 30 days max | การเก็บรักษาข้อมูลชีวมิติ: สูงสุด 30 วัน
- [ ] Data localization in Thailand | การจัดเก็บข้อมูลในประเทศไทย
- [ ] 99.9% uptime SLA
- [ ] 4-hour incident notification for data breaches | แจ้งเหตุการณ์ภายใน 4 ชั่วโมงกรณีข้อมูลรั่วไหล
- [ ] Migration support for 90 days | การสนับสนุนการโยกย้ายเป็นเวลา 90 วัน
- [ ] No data sharing with third parties | ไม่แชร์ข้อมูลกับบุคคลที่สาม
- [ ] Annual security audit rights | สิทธิ์ตรวจสอบความปลอดภัยประจำปี

**Step 3.5**: Legal review
**Step 3.6**: Sign contracts

---

#### **PHASE 2: Technical Integration** (Weeks 9-14)
#### **ระยะที่ 2: การเชื่อมต่อทางเทคนิค** (สัปดาห์ที่ 9-14)

**Week 9-10: API Integration Development** | **สัปดาห์ที่ 9-10: การพัฒนาการเชื่อมต่อ API**

**Step 4.1**: Set up staging environment for new provider
**Step 4.2**: Develop API integration code
**Step 4.3**: Implement error handling and fallback mechanisms
**Step 4.4**: Code review (security focus)

**Integration Architecture** | **สถาปัตยกรรมการเชื่อมต่อ**:
```
Certogo LMS
    ↓
API Gateway (Rate limiting, authentication)
    ↓
    ├─→ Old Provider (Appman) [90% traffic initially]
    │
    └─→ New Provider [10% traffic for testing]
```

**Step 4.5**: Set up monitoring and logging for new provider
**Step 4.6**: Configure alerts for new provider

---

**Week 11-12: Testing** | **สัปดาห์ที่ 11-12: การทดสอบ**

**Testing Checklist** | **รายการทดสอบ**:

**Functional Testing** | **การทดสอบการทำงาน**:
- [ ] Thai National ID card verification | การตรวจสอบบัตรประชาชนไทย
- [ ] Passport verification | การตรวจสอบหนังสือเดินทาง
- [ ] Driver's license verification | การตรวจสอบใบขับขี่
- [ ] Facial recognition accuracy | ความแม่นยำการจดจำใบหน้า
- [ ] Liveness detection | การตรวจสอบความเป็นมนุษย์
- [ ] Error handling | การจัดการข้อผิดพลาด
- [ ] Edge cases (damaged cards, poor lighting) | กรณีขอบเขต (บัตรเสียหาย, แสงไม่เพียงพอ)

**Performance Testing** | **การทดสอบประสิทธิภาพ**:
- [ ] Load testing (1000 concurrent requests) | การทดสอบโหลด (1000 คำขอพร้อมกัน)
- [ ] Stress testing | การทดสอบความเครียด
- [ ] Response time validation (< 500ms) | การตรวจสอบเวลาตอบสนอง (< 500ms)
- [ ] Throughput testing | การทดสอบปริมาณงาน

**Security Testing** | **การทดสอบความปลอดภัย**:
- [ ] Data encryption verification (TLS 1.3) | การตรวจสอบการเข้ารหัสข้อมูล (TLS 1.3)
- [ ] API authentication testing (OAuth 2.0) | การทดสอบการยืนยันตัวตน API (OAuth 2.0)
- [ ] Rate limiting validation | การตรวจสอบการจำกัดอัตรา
- [ ] Injection attack testing | การทดสอบการโจมตีแบบ injection
- [ ] Data leakage testing | การทดสอบการรั่วไหลของข้อมูล

**Compliance Testing** | **การทดสอบการปฏิบัติตาม**:
- [ ] Data retention (30-day auto-delete) | การเก็บรักษาข้อมูล (ลบอัตโนมัติ 30 วัน)
- [ ] Data localization (Thailand only) | การจัดเก็บข้อมูลในประเทศ (เฉพาะประเทศไทย)
- [ ] PDPA consent workflow | เวิร์กโฟลว์การยินยอม PDPA
- [ ] Data subject rights (access, deletion) | สิทธิ์ของเจ้าของข้อมูล (เข้าถึง, ลบ)

**Step 4.7**: Document test results
**Step 4.8**: Fix any issues found
**Step 4.9**: Regression testing
**Step 4.10**: CTO approval to proceed

---

**Week 13-14: Parallel Run Preparation** | **สัปดาห์ที่ 13-14: การเตรียมการทำงานแบบคู่ขนาน**

**Step 5.1**: Set up traffic routing rules (10% new, 90% old initially)
**Step 5.2**: Configure monitoring dashboards for comparison
**Step 5.3**: Prepare rollback procedures
**Step 5.4**: Train support team on new provider
**Step 5.5**: Prepare customer communication

---

#### **PHASE 3: Parallel Run & Migration** (Weeks 15-18)
#### **ระยะที่ 3: การทำงานแบบคู่ขนานและการโยกย้าย** (สัปดาห์ที่ 15-18)

**Week 15: Initial Parallel Run (10% traffic)** | **สัปดาห์ที่ 15: การทำงานคู่ขนานเริ่มต้น (10% ทราฟฟิก)**

**Step 6.1**: Route 10% of production traffic to new provider
**Step 6.2**: Monitor both providers side-by-side

**Metrics to Compare** | **ตัวชี้วัดที่ต้องเปรียบเทียบ**:
```
| Metric | Old (Appman) | New Provider | Target |
|--------|--------------|--------------|--------|
| Uptime | 99.95% | ? | ≥99.9% |
| Response Time (p95) | 300ms | ? | <500ms |
| Accuracy | 98.5% | ? | ≥98% |
| Error Rate | 0.05% | ? | <0.1% |
| False Positive | 0.8% | ? | <1% |
```

**Step 6.3**: Daily review of metrics
**Step 6.4**: Address any issues immediately

**Go/No-Go Decision** | **การตัดสินใจดำเนินการต่อหรือไม่**:
- [ ] New provider meets all targets | ผู้ให้บริการใหม่บรรลุเป้าหมายทั้งหมด
- [ ] No critical incidents | ไม่มีเหตุการณ์วิกฤต
- [ ] Customer satisfaction maintained | ความพึงพอใจของลูกค้าคงที่
- [ ] Support team comfortable | ทีมสนับสนุนมั่นใจ

---

**Week 16: Increase Traffic (50%)** | **สัปดาห์ที่ 16: เพิ่มทราฟฟิก (50%)**

**Step 7.1**: Increase traffic to 50% new, 50% old
**Step 7.2**: Continue monitoring
**Step 7.3**: Compare costs (actual vs. projected)

**Rollback Criteria** | **เกณฑ์การย้อนกลับ**:
- New provider downtime > 1 hour | ผู้ให้บริการใหม่ downtime > 1 ชั่วโมง
- Accuracy drop > 5% | ความแม่นยำลดลง > 5%
- Critical security incident | เหตุการณ์ความปลอดภัยวิกฤต
- Data breach | ข้อมูลรั่วไหล

If rollback needed: Immediate revert to 100% old provider

---

**Week 17: Full Migration (100%)** | **สัปดาห์ที่ 17: การโยกย้ายเต็มรูปแบบ (100%)**

**Step 8.1**: Route 100% traffic to new provider
**Step 8.2**: Keep old provider on standby (24-48 hours)
**Step 8.3**: Monitor closely

**Migration Checklist** | **รายการโยกย้าย**:
- [ ] All traffic routed to new provider | ทราฟฟิกทั้งหมดถูกส่งไปยังผู้ให้บริการใหม่
- [ ] Old provider still accessible (standby) | ผู้ให้บริการเก่ายังเข้าถึงได้ (สแตนด์บาย)
- [ ] Monitoring shows stable performance | การตรวจสอบแสดงประสิทธิภาพที่เสถียร
- [ ] Support team has escalation path | ทีมสนับสนุนมีเส้นทางการส่งต่อปัญหา
- [ ] Customers notified (if necessary) | แจ้งลูกค้า (หากจำเป็น)

**Step 8.4**: After 48 hours of stable operation → Declare migration successful

---

**Week 18: Old Provider Decommissioning** | **สัปดาห์ที่ 18: การปิดระบบผู้ให้บริการเก่า**

**Step 9.1**: Notify old provider of termination (as per contract)
**Step 9.2**: Request data deletion from old provider

**Data Deletion Verification** 🔴 | **การตรวจสอบการลบข้อมูล**:
```
Within 30 days of termination:
ภายใน 30 วันหลังจากสิ้นสุดสัญญา:

1. Old provider deletes ALL data:
   ผู้ให้บริการเก่าลบข้อมูลทั้งหมด:
   - Biometric data (facial images) | ข้อมูลชีวมิติ (ภาพใบหน้า)
   - ID card images | ภาพบัตรประชาชน
   - Verification results | ผลการตรวจสอบ
   - API logs containing PII | บันทึก API ที่มีข้อมูลส่วนบุคคล
   - Backup copies | สำเนาสำรอง

2. Provider certifies deletion:
   ผู้ให้บริการรับรองการลบ:
   - Written certificate of deletion | ใบรับรองการลบเป็นลายลักษณ์อักษร
   - Signed by authorized officer | ลงนามโดยเจ้าหน้าที่ที่ได้รับอนุญาต
   - Details of deletion method | รายละเอียดวิธีการลบ
   - Confirmation of no residual copies | ยืนยันว่าไม่มีสำเนาที่เหลืออยู่

3. Certogo verifies deletion:
   Certogo ตรวจสอบการลบ:
   - Review certificate | ตรวจสอบใบรับรอง
   - Attempt API access (should fail) | พยายามเข้าถึง API (ควรล้มเหลว)
   - Optional: Third-party audit | เลือกได้: ตรวจสอบโดยบุคคลที่สาม
```

**Step 9.3**: Revoke all API access credentials to old provider
**Step 9.4**: Remove old provider from supplier registry
**Step 9.5**: Archive old provider documentation

**Step 9.6**: 🔴 **Update ISO 27001 Documentation**:
- [ ] Update this Statement of Applicability (replace "Appman" with new provider name)
- [ ] Update A.5 Organizational Controls documentation
- [ ] Update supplier registry
- [ ] Update ISMS scope document
- [ ] Update privacy policy (customer-facing)
- [ ] Update data protection impact assessment (DPIA)

---

#### **PHASE 4: Post-Migration Review** (Week 19-20)
#### **ระยะที่ 4: การทบทวนหลังการโยกย้าย** (สัปดาห์ที่ 19-20)

**Step 10.1**: Conduct post-implementation review meeting

**Review Agenda** | **วาระการทบทวน**:
1. Migration success criteria achieved? | บรรลุเกณฑ์ความสำเร็จในการโยกย้ายหรือไม่?
2. Issues encountered and resolutions | ปัญหาที่พบและการแก้ไข
3. Lessons learned | บทเรียนที่ได้เรียนรู้
4. Cost analysis (actual vs. budget) | การวิเคราะห์ต้นทุน (จริงเทียบกับงบประมาณ)
5. Performance comparison (old vs. new) | การเปรียบเทียบประสิทธิภาพ (เก่าเทียบกับใหม่)
6. Customer impact assessment | การประเมินผลกระทบต่อลูกค้า
7. Documentation completeness | ความสมบูรณ์ของเอกสาร

**Step 10.2**: Document lessons learned
**Step 10.3**: Update migration procedure based on lessons
**Step 10.4**: Final report to management

---

#### **PHASE 5: Ongoing Management** (Week 21+)
#### **ระยะที่ 5: การจัดการอย่างต่อเนื่อง** (สัปดาห์ที่ 21 เป็นต้นไป)

**Step 11.1**: Resume quarterly security reviews with new provider
**Step 11.2**: Annual security assessment
**Step 11.3**: Contract renewal planning (12 months before expiry)

---

#### 3. Performance Metrics & Reporting | ตัวชี้วัดประสิทธิภาพและการรายงาน

**Monthly Supplier Scorecard** | **ใบคะแนนซัพพลายเออร์รายเดือน**:

```
E-KYC Provider Performance Report - [Month/Year]
รายงานประสิทธิภาพผู้ให้บริการ E-KYC - [เดือน/ปี]

Provider: [Appman / New Provider Name]

1. Availability | ความพร้อมใช้งาน:
   - Uptime: 99.95% ✅ (Target: 99.9%)
   - Downtime incidents: 1 (Total: 15 minutes)

2. Performance | ประสิทธิภาพ:
   - Avg response time: 285ms ✅ (Target: <500ms)
   - p95 response time: 420ms ✅
   - p99 response time: 680ms ⚠️ (Target: <1000ms)

3. Accuracy | ความแม่นยำ:
   - Verification accuracy: 98.7% ✅ (Target: >98%)
   - False positive rate: 0.7% ✅ (Target: <1%)
   - False negative rate: 0.6% ✅

4. Security | ความปลอดภัย:
   - Security incidents: 0 ✅
   - ISO 27001 valid: Yes ✅ (Expires: [DATE])
   - Penetration test: Completed Q1 ✅

5. Compliance | การปฏิบัติตาม:
   - SLA compliance: 100% ✅
   - Data deletion: Compliant ✅
   - PDPA compliance: Verified ✅
   - Incident notification: Within 4 hours ✅

6. Support | การสนับสนุน:
   - Support tickets: 3 (All resolved)
   - Avg resolution time: 2.5 hours ✅ (Target: <4 hours)
   - Escalations: 0 ✅

7. Cost | ต้นทุน:
   - Transactions: 15,230
   - Total cost: ฿122,450
   - Cost per transaction: ฿8.04 ✅ (Budget: ฿8.50)

Overall Score: 95/100 ✅ (Target: >85)
```

**Quarterly Business Review (QBR)** | **การทบทวนธุรกิจรายไตรมาส**:
- Hosted by Certogo with E-KYC provider
- Review of performance, incidents, roadmap
- Opportunity to discuss improvements
- Contract compliance verification

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/records/supplier-monitoring/ekyc-monthly-reports/` - Monthly scorecards
- `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/` - QBR minutes
- `/evidence/records/supplier-monitoring/ekyc-incident-log.xlsx` - Incident tracking
- `/evidence/records/supplier-change-management/provider-migration-plan.pdf` - Migration procedure
- `/evidence/records/supplier-change-management/lessons-learned.pdf` - Post-migration review
- `/evidence/records/supplier-monitoring/appman-data-deletion-certificate.pdf` - Data deletion proof
- `/evidence/procedures/ekyc-provider-change-checklist.xlsx` - Migration checklist

### Compliance References | การอ้างอิงการปฏิบัติตาม

- **ISO 27001:2022** A.5.22
- **ISO 27002:2022** Section 5.22
- **Thai PDPA** Section 32 - Data deletion requirements

---

## Summary | สรุป

This document provides detailed implementation guidance for **A.5 Organizational Controls** for Certogo's ISO 27001:2022 certification, with special emphasis on **E-KYC provider management**.

เอกสารนี้ให้คำแนะนำการนำไปใช้โดยละเอียดสำหรับ **มาตรการควบคุมระดับองค์กร A.5** สำหรับการรับรอง ISO 27001:2022 ของ Certogo โดยเน้นเป็นพิเศษที่ **การจัดการผู้ให้บริการ E-KYC**

**Critical Controls for E-KYC** 🔴:
- **A.5.19**: Supplier security assessment
- **A.5.20**: Contract requirements (DPA, SLA, data deletion)
- **A.5.22**: Monitoring and provider change management

**Key Takeaway** | **ประเด็นสำคัญ**:
Since Appman's E-KYC service may change in the future, Certogo has established **comprehensive procedures** for:
- Assessing new providers
- Managing migration with minimal disruption
- Ensuring data deletion from old providers
- Maintaining ISO 27001 compliance throughout the transition

เนื่องจากบริการ E-KYC ของ Appman อาจเปลี่ยนแปลงในอนาคต Certogo ได้จัดทำ **ขั้นตอนที่ครอบคลุม** สำหรับ:
- การประเมินผู้ให้บริการใหม่
- การจัดการการโยกย้ายโดยมีการรบกวนน้อยที่สุด
- การรับประกันการลบข้อมูลจากผู้ให้บริการเก่า
- การรักษาการปฏิบัติตาม ISO 27001 ตลอดการเปลี่ยนผ่าน

---

**Document Control** | **การควบคุมเอกสาร**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-01-20 | CISO | Initial draft with E-KYC focus |

**Next Review Date** | **วันที่ทบทวนครั้งต่อไป**: 2026-01-20 (or upon E-KYC provider change)

**Approval** | **การอนุมัติ**:
- [ ] CISO
- [ ] CTO
- [ ] DPO
- [ ] CEO
