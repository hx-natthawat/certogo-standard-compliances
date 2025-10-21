# ISO 27001:2022 Risk Assessment Template
# แม่แบบการประเมินความเสี่ยง ISO 27001:2022

## Document Information | ข้อมูลเอกสาร

**Organization** | **องค์กร**: Certogo Co., Ltd.
**Assessment Period** | **ระยะเวลาการประเมิน**: [Start Date] to [End Date]
**Standard** | **มาตรฐาน**: ISO/IEC 27001:2022
**Version** | **เวอร์ชัน**: 1.0
**Date** | **วันที่**: [YYYY-MM-DD]
**Status** | **สถานะ**: [Draft / Final]

---

## Table of Contents | สารบัญ

1. [Risk Assessment Methodology](#1-risk-assessment-methodology)
2. [Risk Criteria](#2-risk-criteria)
3. [Asset Identification](#3-asset-identification)
4. [Threat and Vulnerability Assessment](#4-threat-and-vulnerability-assessment)
5. [Risk Analysis](#5-risk-analysis)
6. [Risk Evaluation](#6-risk-evaluation)
7. [Risk Register](#7-risk-register)
8. [E-KYC Provider Specific Risks](#8-e-kyc-provider-specific-risks-)
9. [Risk Treatment Decisions](#9-risk-treatment-decisions)
10. [Approval and Review](#10-approval-and-review)

---

## 1. Risk Assessment Methodology
## วิธีการประเมินความเสี่ยง

### 1.1 Overview | ภาพรวม

This risk assessment follows the **ISO 27001:2022** and **ISO 27005:2022** frameworks to systematically identify, analyze, and evaluate information security risks affecting Certogo's LMS platform and E-KYC integration.

การประเมินความเสี่ยงนี้เป็นไปตามกรอบมาตรฐาน **ISO 27001:2022** และ **ISO 27005:2022** เพื่อระบุ วิเคราะห์ และประเมินความเสี่ยงด้านความมั่นคงปลอดภัยสารสนเทศที่มีผลกระทบต่อแพลตฟอร์ม LMS ของ Certogo และการเชื่อมต่อ E-KYC อย่างเป็นระบบ

### 1.2 Assessment Approach | แนวทางการประเมิน

**Qualitative Risk Assessment** | **การประเมินความเสี่ยงเชิงคุณภาพ**

We use a qualitative approach with defined scales for:
เราใช้แนวทางเชิงคุณภาพด้วยมาตราส่วนที่กำหนดสำหรับ:

- **Likelihood** (Probability of occurrence) | **ความเป็นไปได้** (ความน่าจะเป็นที่จะเกิดขึ้น)
- **Impact** (Consequence if occurred) | **ผลกระทบ** (ผลที่ตามมาหากเกิดขึ้น)
- **Risk Level** (Likelihood × Impact) | **ระดับความเสี่ยง** (ความเป็นไปได้ × ผลกระทบ)

### 1.3 Scope | ขอบเขต

**In Scope** | **อยู่ในขอบเขต**:
- Certogo LMS platform (web application, mobile apps, APIs)
- Certogo infrastructure (cloud servers, databases, networks)
- Customer data (PII, training records, certificates)
- 🔴 **E-KYC integration with Appman** (API, biometric data processing)
- Certogo employees and contractors
- Third-party suppliers (especially E-KYC provider)

**Out of Scope** | **นอกขอบเขต**:
- Appman's internal systems (covered by their ISO 27001)
- Customer's internal IT infrastructure
- Public internet infrastructure

### 1.4 Information Security Objectives | วัตถุประสงค์ด้านความมั่นคงปลอดภัยสารสนเทศ

**CIA Triad** | **หลักการ CIA**:

1. **Confidentiality** | **ความลับ**: Protect sensitive data from unauthorized disclosure
   - 🔴 **Highest priority**: Biometric data (facial images, ID card data)
   - High priority: Customer PII, training records

2. **Integrity** | **ความสมบูรณ์**: Ensure data accuracy and completeness
   - High priority: E-KYC verification results, certificates issued
   - Medium priority: Training records, course content

3. **Availability** | **ความพร้อมใช้งาน**: Ensure services are accessible when needed
   - High priority: LMS platform (99.9% uptime SLA)
   - 🔴 **Critical**: E-KYC verification service (99.9% uptime SLA)

### 1.5 Risk Assessment Team | ทีมประเมินความเสี่ยง

| Role | Name | Responsibility |
|------|------|----------------|
| **Risk Assessment Owner** | CISO | Overall accountability |
| **Risk Analyst** | Security Team Lead | Conduct assessment |
| **Technical SME** | CTO | Infrastructure and technical risks |
| **Data Protection SME** | DPO | PDPA and privacy risks |
| **Supplier Management SME** | Procurement Manager | Third-party risks (E-KYC) |
| **Business SME** | Product Manager | Business impact assessment |

---

## 2. Risk Criteria
## เกณฑ์ความเสี่ยง

### 2.1 Likelihood Scale | มาตราส่วนความเป็นไปได้

| Level | Rating | Description | Frequency |
|-------|--------|-------------|-----------|
| **Very Low** | 1 | Rare, highly unlikely | < 1% per year |
| **Low** | 2 | Unlikely, but possible | 1-10% per year |
| **Medium** | 3 | Possible, has occurred in industry | 10-25% per year |
| **High** | 4 | Likely, has occurred to us before | 25-50% per year |
| **Very High** | 5 | Almost certain, frequent occurrence | > 50% per year |

**Thai Descriptions** | **คำอธิบายภาษาไทย**:
- **Very Low**: หายาก, เกือบจะไม่เกิด
- **Low**: ไม่น่าจะเกิด แต่เป็นไปได้
- **Medium**: เป็นไปได้ เคยเกิดในอุตสาหกรรม
- **High**: น่าจะเกิด เคยเกิดกับเราแล้ว
- **Very High**: แน่นอนเกือบจะเกิด เกิดบ่อย

### 2.2 Impact Scale | มาตราส่วนผลกระทบ

Impact is assessed across multiple dimensions:
ผลกระทบได้รับการประเมินในหลายมิติ:

#### 2.2.1 Confidentiality Impact | ผลกระทบต่อความลับ

| Level | Rating | Description |
|-------|--------|-------------|
| **Negligible** | 1 | Public data exposed | ข้อมูลสาธารณะถูกเปิดเผย |
| **Low** | 2 | Internal data exposed (< 100 records) | ข้อมูลภายในถูกเปิดเผย (< 100 รายการ) |
| **Medium** | 3 | Confidential data exposed (< 1,000 records) | ข้อมูลลับถูกเปิดเผย (< 1,000 รายการ) |
| **High** | 4 | Highly confidential data (< 10,000 records) | ข้อมูลลับสูง (< 10,000 รายการ) |
| **Critical** | 5 | 🔴 **Biometric data breach** (any amount) or massive PII breach (> 10,000) | การรั่วไหลข้อมูลชีวมิติ (จำนวนใดก็ตาม) หรือ PII จำนวนมาก (> 10,000) |

#### 2.2.2 Integrity Impact | ผลกระทบต่อความสมบูรณ์

| Level | Rating | Description |
|-------|--------|-------------|
| **Negligible** | 1 | Minor data corruption, easily corrected | การเสียหายของข้อมูลเล็กน้อย แก้ไขได้ง่าย |
| **Low** | 2 | Some data corruption, manual correction needed | ข้อมูลเสียหายบางส่วน ต้องแก้ไขด้วยตนเอง |
| **Medium** | 3 | Significant data corruption, affects functionality | ข้อมูลเสียหายอย่างมาก ส่งผลกระทบต่อการทำงาน |
| **High** | 4 | Critical data corrupted (e.g., certificates, training records) | ข้อมูลสำคัญเสียหาย (เช่น ใบรับรอง บันทึกการฝึกอบรม) |
| **Critical** | 5 | 🔴 **E-KYC verification results corrupted**, compliance data lost | ผล E-KYC เสียหาย ข้อมูลการปฏิบัติตามสูญหาย |

#### 2.2.3 Availability Impact | ผลกระทบต่อความพร้อมใช้งาน

| Level | Rating | Description |
|-------|--------|-------------|
| **Negligible** | 1 | Downtime < 15 minutes, minimal users affected | Downtime < 15 นาที ผู้ใช้ได้รับผลกระทบเล็กน้อย |
| **Low** | 2 | Downtime 15-60 minutes, some users affected | Downtime 15-60 นาที ผู้ใช้บางส่วนได้รับผลกระทบ |
| **Medium** | 3 | Downtime 1-4 hours, many users affected | Downtime 1-4 ชั่วโมง ผู้ใช้จำนวนมากได้รับผลกระทบ |
| **High** | 4 | Downtime 4-24 hours, SLA breach | Downtime 4-24 ชั่วโมง ละเมิด SLA |
| **Critical** | 5 | 🔴 **Downtime > 24 hours** or **E-KYC service unavailable during peak** | Downtime > 24 ชั่วโมง หรือบริการ E-KYC ไม่พร้อมใช้งานในช่วงเวลาที่มีความต้องการสูง |

#### 2.2.4 Financial Impact | ผลกระทบทางการเงิน

| Level | Rating | Description |
|-------|--------|-------------|
| **Negligible** | 1 | < ฿10,000 |
| **Low** | 2 | ฿10,000 - ฿100,000 |
| **Medium** | 3 | ฿100,000 - ฿1,000,000 |
| **High** | 4 | ฿1,000,000 - ฿10,000,000 |
| **Critical** | 5 | > ฿10,000,000 (e.g., PDPA fines, class action) |

#### 2.2.5 Reputational Impact | ผลกระทบต่อชื่อเสียง

| Level | Rating | Description |
|-------|--------|-------------|
| **Negligible** | 1 | No public attention | ไม่มีความสนใจจากสาธารณะ |
| **Low** | 2 | Minor negative feedback (social media) | ความคิดเห็นเชิงลบเล็กน้อย |
| **Medium** | 3 | Local media coverage | สื่อท้องถิ่นรายงาน |
| **High** | 4 | National media coverage, customer churn | สื่อระดับชาติรายงาน ลูกค้าหนี |
| **Critical** | 5 | 🔴 **International media, regulatory action, loss of certifications** | สื่อสากล การดำเนินการของหน่วยงานกำกับ สูญเสียการรับรอง |

#### 2.2.6 Legal/Regulatory Impact | ผลกระทบทางกฎหมาย/กฎระเบียบ

| Level | Rating | Description |
|-------|--------|-------------|
| **Negligible** | 1 | No legal/regulatory impact | ไม่มีผลกระทบทางกฎหมาย/กฎระเบียบ |
| **Low** | 2 | Warning from regulator | คำเตือนจากหน่วยงานกำกับ |
| **Medium** | 3 | Minor fine (< ฿1M) | ค่าปรับเล็กน้อย (< ฿1M) |
| **High** | 4 | Significant fine (< ฿5M), corrective action order | ค่าปรับมาก (< ฿5M) คำสั่งแก้ไข |
| **Critical** | 5 | 🔴 **PDPA fine (up to 5% revenue), criminal liability** | ค่าปรับ PDPA (สูงสุด 5% รายได้) ความรับผิดทางอาญา |

### 2.3 Overall Impact Calculation | การคำนวณผลกระทบโดยรวม

**Overall Impact = Highest rating across all dimensions**

ผลกระทบโดยรวม = คะแนนสูงสุดในทุกมิติ

**Example** | **ตัวอย่าง**:
- Confidentiality: 5 (Critical - Biometric data breach)
- Integrity: 2 (Low)
- Availability: 3 (Medium)
- Financial: 4 (High)
- Reputational: 5 (Critical)
- Legal: 5 (Critical)

**Overall Impact = 5 (Critical)**

### 2.4 Risk Level Matrix | เมทริกซ์ระดับความเสี่ยง

|  | **Impact** | | | | |
|--|------------|--|--|--|--|
| **Likelihood** | **1 (Negligible)** | **2 (Low)** | **3 (Medium)** | **4 (High)** | **5 (Critical)** |
| **5 (Very High)** | 🟡 Medium (5) | 🟠 High (10) | 🔴 Critical (15) | 🔴 Critical (20) | 🔴 Critical (25) |
| **4 (High)** | 🟢 Low (4) | 🟡 Medium (8) | 🟠 High (12) | 🔴 Critical (16) | 🔴 Critical (20) |
| **3 (Medium)** | 🟢 Low (3) | 🟡 Medium (6) | 🟡 Medium (9) | 🟠 High (12) | 🔴 Critical (15) |
| **2 (Low)** | 🟢 Low (2) | 🟢 Low (4) | 🟡 Medium (6) | 🟡 Medium (8) | 🟠 High (10) |
| **1 (Very Low)** | 🟢 Low (1) | 🟢 Low (2) | 🟢 Low (3) | 🟡 Medium (4) | 🟡 Medium (5) |

**Risk Scoring** | **การให้คะแนนความเสี่ยง**:
- **Risk Score** = Likelihood × Impact
- **Risk Level**:
  - 🟢 **Low** (1-4): Acceptable, monitor
  - 🟡 **Medium** (5-9): Review and implement controls
  - 🟠 **High** (10-15): Priority action required
  - 🔴 **Critical** (16-25): Immediate action required

### 2.5 Risk Acceptance Criteria | เกณฑ์การยอมรับความเสี่ยง

| Risk Level | Action Required | Approval Authority |
|------------|-----------------|---------------------|
| 🟢 **Low** | Monitor and review annually | Security Team |
| 🟡 **Medium** | Implement controls within 6 months | CISO |
| 🟠 **High** | Implement controls within 3 months | CISO + CTO |
| 🔴 **Critical** | Immediate action (< 30 days) | CEO + CISO |

**Risk Acceptance** | **การยอมรับความเสี่ยง**:
- Residual risk ≤ Medium can be accepted | ความเสี่ยงที่เหลือ ≤ ปานกลาง สามารถยอมรับได้
- High/Critical risks require documented justification for acceptance
  - ความเสี่ยงสูง/วิกฤต ต้องมีเหตุผลเป็นลายลักษณ์อักษรสำหรับการยอมรับ

---

## 3. Asset Identification
## การระบุทรัพย์สิน

### 3.1 Asset Categories | หมวดทรัพย์สิน

| Category | Examples | Owner |
|----------|----------|-------|
| **Information Assets** | Customer PII, 🔴 biometric data, training records, certificates | DPO |
| **Application Assets** | LMS web app, mobile apps, admin portal, 🔴 E-KYC API integration | CTO |
| **Infrastructure Assets** | Cloud servers (AWS/Azure/GCP), databases, network | CTO |
| **Network Assets** | Firewalls, routers, VPN, 🔴 API Gateway | Network Team |
| **Human Assets** | Employees, contractors, 🔴 E-KYC provider personnel | CISO |
| **Physical Assets** | Offices, data centers (3rd party), laptops, servers | Facility Manager |
| **Services** | Cloud hosting, 🔴 **E-KYC service (Appman)**, email, payment gateway | Procurement |

### 3.2 Critical Assets for Certogo | ทรัพย์สินที่สำคัญสำหรับ Certogo

**Highest Value Assets** (Require strongest protection):

1. 🔴 **Biometric Data** (Facial images, ID card scans)
   - Classification: Highly Confidential
   - Storage: Appman E-KYC provider (Thailand data center)
   - Retention: 30 days maximum
   - Regulatory: PDPA sensitive personal data

2. **Customer PII** (Name, email, phone, address)
   - Classification: Confidential
   - Storage: Certogo databases (encrypted)
   - Retention: As long as customer account is active + 7 years
   - Regulatory: PDPA personal data

3. **Training Records and Certificates**
   - Classification: Confidential
   - Storage: Certogo databases
   - Integrity critical for compliance customers

4. **E-KYC Verification Results**
   - Classification: Confidential
   - Storage: Certogo databases
   - Integrity critical for trust and compliance

5. **LMS Application** (Source code, production systems)
   - Classification: Internal
   - Availability critical for business operations

6. **E-KYC API Integration**
   - Classification: Internal (code), Confidential (credentials)
   - Availability critical for onboarding

### 3.3 Asset Inventory | บัญชีทรัพย์สิน

Detailed asset inventory maintained in:
บัญชีทรัพย์สินโดยละเอียดเก็บไว้ที่:

`/evidence/records/asset-inventory.xlsx`

**Minimum Information for Each Asset**:
- Asset ID
- Asset Name
- Asset Type
- Owner
- Classification Level
- Location
- Value Rating (1-5)

---

## 4. Threat and Vulnerability Assessment
## การประเมินภัยคุกคามและช่องโหว่

### 4.1 Threat Sources | แหล่งภัยคุกคาม

| Threat Source | Description | Examples |
|---------------|-------------|----------|
| **External Attackers** | Malicious actors targeting systems for financial gain or data theft | Hackers, organized crime, nation-states |
| **Insiders** | Current or former employees with malicious intent | Disgruntled employee, contractor |
| **Accidental Actions** | Unintentional mistakes by users or administrators | Misconfiguration, accidental deletion |
| **Third-Party Suppliers** | 🔴 **Security failures by E-KYC provider or other vendors** | Appman data breach, cloud provider outage |
| **Natural Disasters** | Environmental events | Fire, flood, earthquake |
| **Technical Failures** | System or hardware failures | Server crash, network failure, software bug |

### 4.2 Common Threats to LMS and E-KYC | ภัยคุกคามทั่วไปต่อ LMS และ E-KYC

| Threat ID | Threat | Applicable To |
|-----------|--------|---------------|
| T-001 | SQL Injection | LMS database |
| T-002 | Cross-Site Scripting (XSS) | LMS web application |
| T-003 | Brute Force Attack on Login | LMS, Admin portal |
| T-004 | DDoS Attack | LMS, E-KYC API |
| T-005 | 🔴 **Biometric Data Breach at E-KYC Provider** | Appman E-KYC service |
| T-006 | 🔴 **Man-in-the-Middle Attack on E-KYC API** | E-KYC API integration |
| T-007 | Ransomware | Certogo servers, databases |
| T-008 | Insider Data Theft | Customer PII, biometric data access |
| T-009 | 🔴 **E-KYC Provider Service Outage** | Appman availability |
| T-010 | Phishing Attack on Employees | Email, credentials |
| T-011 | Misconfiguration of Cloud Services | AWS/Azure/GCP |
| T-012 | Unpatched Vulnerabilities | Servers, applications |
| T-013 | 🔴 **Unauthorized Sub-processor by E-KYC Provider** | Appman data processing |
| T-014 | Physical Theft of Laptops | Employee devices |
| T-015 | 🔴 **E-KYC Provider Loses ISO 27001 Certification** | Appman compliance |

### 4.3 Vulnerabilities | ช่องโหว่

| Vulnerability ID | Vulnerability | Related Assets |
|------------------|---------------|----------------|
| V-001 | Weak password policy | User accounts |
| V-002 | Lack of multi-factor authentication (MFA) | Admin accounts |
| V-003 | Outdated software versions | Web servers |
| V-004 | 🔴 **Insufficient monitoring of E-KYC API calls** | E-KYC integration |
| V-005 | Unencrypted data in transit | API connections |
| V-006 | 🔴 **No automated verification of biometric data deletion** | Appman compliance |
| V-007 | Single point of failure (no redundancy) | Database |
| V-008 | Inadequate access controls | Privileged accounts |
| V-009 | 🔴 **Lack of contractual penalties for E-KYC provider SLA breach** | Appman SLA |
| V-010 | No regular security training for developers | Development team |
| V-011 | 🔴 **No backup E-KYC provider** | E-KYC service continuity |

---

## 5. Risk Analysis
## การวิเคราะห์ความเสี่ยง

### 5.1 Risk Identification | การระบุความเสี่ยง

For each **Asset**, consider:
สำหรับแต่ละ **ทรัพย์สิน** พิจารณา:

- What **Threats** could exploit which **Vulnerabilities**?
- What is the **Likelihood** of this happening?
- What would be the **Impact** if it occurred?

**Formula**: Risk = Asset × Threat × Vulnerability

### 5.2 Risk Analysis Table | ตารางการวิเคราะห์ความเสี่ยง

**Use this format for each identified risk**:

| Field | Value |
|-------|-------|
| **Risk ID** | R-XXX |
| **Risk Title** | Short descriptive title |
| **Asset** | Which asset is at risk? |
| **Threat** | What could go wrong? |
| **Vulnerability** | What weakness could be exploited? |
| **Existing Controls** | What controls are already in place? |
| **Likelihood (Inherent)** | 1-5 (before controls) |
| **Impact** | 1-5 (consequences) |
| **Inherent Risk Score** | Likelihood × Impact |
| **Inherent Risk Level** | Low / Medium / High / Critical |
| **Likelihood (Residual)** | 1-5 (with controls) |
| **Residual Risk Score** | Likelihood × Impact |
| **Residual Risk Level** | Low / Medium / High / Critical |
| **Risk Owner** | Who is responsible? |
| **Risk Treatment** | Mitigate / Accept / Transfer / Avoid |

---

## 6. Risk Evaluation
## การประเมินความเสี่ยง

### 6.1 Risk Prioritization | การจัดลำดับความสำคัญของความเสี่ยง

Risks are prioritized based on **Residual Risk Level**:
ความเสี่ยงได้รับการจัดลำดับความสำคัญตามระดับความเสี่ยงที่เหลือ:

1. 🔴 **Critical** (Score 16-25): Immediate action required
2. 🟠 **High** (Score 10-15): Priority action within 3 months
3. 🟡 **Medium** (Score 5-9): Action within 6 months
4. 🟢 **Low** (Score 1-4): Monitor and review

### 6.2 Risk Treatment Options | ตัวเลือกการจัดการความเสี่ยง

| Treatment | Definition | When to Use | Example |
|-----------|------------|-------------|---------|
| **Mitigate** | Reduce likelihood or impact | Most common for Medium/High risks | Implement MFA, encryption |
| **Accept** | Accept the risk as-is | Low risks, cost of mitigation > benefit | Accept low risk of laptop theft with insurance |
| **Transfer** | Transfer risk to third party | Risks that can be insured or outsourced | 🔴 Cyber insurance for data breach |
| **Avoid** | Eliminate the risk by not performing the activity | Unacceptable risks | Don't store biometric data on Certogo servers (use Appman) |

---

## 7. Risk Register
## ทะเบียนความเสี่ยง

**Full risk register maintained in Excel**:
ทะเบียนความเสี่ยงแบบเต็มเก็บไว้ใน Excel:

`/03-planning/risk-assessment-[YYYY].xlsx`

**Summary of Key Risks** (Top 10):

### Risk Summary Table | ตารางสรุปความเสี่ยง

| Risk ID | Risk Title | Residual Risk | Owner | Status |
|---------|------------|---------------|-------|--------|
| R-001 | 🔴 Biometric data breach at E-KYC provider | Critical | CISO | Mitigating |
| R-002 | 🔴 E-KYC provider service outage | High | CTO | Mitigating |
| R-003 | SQL Injection attack on LMS database | High | CTO | Mitigating |
| R-004 | Ransomware attack on Certogo infrastructure | High | CISO | Mitigating |
| R-005 | 🔴 E-KYC provider loses ISO 27001 certification | Medium | Procurement | Monitoring |
| R-006 | DDoS attack on LMS platform | Medium | CTO | Mitigating |
| R-007 | Insider data theft | Medium | CISO | Mitigating |
| R-008 | Phishing attack leading to credential compromise | Medium | CISO | Mitigating |
| R-009 | 🔴 Unauthorized data processing by E-KYC sub-processor | Medium | DPO | Mitigating |
| R-010 | Cloud service misconfiguration | Medium | CTO | Mitigating |

---

## 8. E-KYC Provider Specific Risks 🔴
## ความเสี่ยงเฉพาะของผู้ให้บริการ E-KYC

**CRITICAL SECTION FOR CERTOGO**

This section details risks specifically related to the E-KYC integration with Appman, which is a critical third-party dependency.

ส่วนนี้รายละเอียดความเสี่ยงที่เกี่ยวข้องกับการเชื่อมต่อ E-KYC กับ Appman ซึ่งเป็นการพึ่งพาบุคคลที่สามที่สำคัญ

---

### **RISK R-001**: 🔴 Biometric Data Breach at E-KYC Provider

| Field | Value |
|-------|-------|
| **Risk ID** | R-001 |
| **Risk Title** | Biometric Data Breach at E-KYC Provider (Appman) |
| **Classification** | 🔴 **CRITICAL** |
| **Asset** | Biometric data (facial images, ID card scans) stored at Appman |
| **Threat** | External attacker breaches Appman's systems and exfiltrates biometric data |
| **Vulnerability** | - Certogo has no direct control over Appman's security<br>- Limited visibility into Appman's security posture |

**Impact Assessment**:
- **Confidentiality**: 5 (Critical) - Highly sensitive personal data under PDPA
- **Financial**: 5 (Critical) - PDPA fine up to 5% of revenue + compensation to data subjects
- **Reputational**: 5 (Critical) - Loss of customer trust, media coverage
- **Legal**: 5 (Critical) - PDPA Section 37 violations, potential criminal liability
- **Overall Impact**: **5 (Critical)**

**Likelihood Assessment**:
- **Inherent Likelihood** (without controls): 3 (Medium) - Data breaches occur in the industry
- **Residual Likelihood** (with controls): 2 (Low) - Appman is ISO 27001 certified

**Inherent Risk**: 3 × 5 = **15 (Critical)** 🔴
**Residual Risk**: 2 × 5 = **10 (High)** 🟠

**Existing Controls**:
1. ✅ Appman is ISO 27001 certified (verified annually)
2. ✅ Data Processing Agreement (DPA) with security requirements
3. ✅ Biometric data encrypted at rest (AES-256) and in transit (TLS 1.3)
4. ✅ Data retention limited to 30 days (reduces exposure window)
5. ✅ Quarterly security reports from Appman
6. ✅ Annual security assessment of Appman
7. ✅ Incident notification clause (4 hours for data breaches)
8. ✅ Cyber insurance covering third-party breaches

**Additional Controls Planned**:
1. 🔄 Request Appman's penetration test reports (annually)
2. 🔄 Conduct third-party security audit of Appman (every 2 years)
3. 🔄 Implement real-time monitoring of E-KYC API for anomalies
4. 🔄 Develop incident response plan specific to E-KYC provider breach

**Risk Treatment**: **Mitigate + Transfer** (Cyber insurance)

**Risk Owner**: CISO

**Review Frequency**: Quarterly

---

### **RISK R-002**: 🔴 E-KYC Provider Service Outage

| Field | Value |
|-------|-------|
| **Risk ID** | R-002 |
| **Risk Title** | E-KYC Service Outage (Appman Unavailable) |
| **Classification** | 🟠 **HIGH** |
| **Asset** | E-KYC verification service, customer onboarding process |
| **Threat** | Appman service outage due to technical failure, DDoS, or disaster |
| **Vulnerability** | - Single point of failure (no backup E-KYC provider)<br>- Vendor lock-in to Appman |

**Impact Assessment**:
- **Availability**: 5 (Critical) - Cannot onboard new customers requiring E-KYC
- **Financial**: 3 (Medium) - Lost revenue during outage (estimated ฿50k per hour)
- **Reputational**: 3 (Medium) - Customer dissatisfaction
- **Overall Impact**: **5 (Critical)**

**Likelihood Assessment**:
- **Inherent Likelihood**: 3 (Medium) - Service outages do occur
- **Residual Likelihood**: 2 (Low) - Appman has 99.9% SLA, multi-region deployment

**Inherent Risk**: 3 × 5 = **15 (Critical)** 🔴
**Residual Risk**: 2 × 5 = **10 (High)** 🟠

**Existing Controls**:
1. ✅ SLA with Appman (99.9% uptime guarantee)
2. ✅ Appman has multi-region deployment (redundancy)
3. ✅ Real-time monitoring of E-KYC API availability
4. ✅ Alerting for API downtime > 5 minutes
5. ✅ Graceful degradation (customers can skip E-KYC temporarily with manual verification)

**Additional Controls Planned**:
1. 🔄 Identify and pre-qualify backup E-KYC provider (by Q2 2025)
2. 🔄 Design multi-provider architecture (API abstraction layer)
3. 🔄 Conduct annual failover test with Appman

**Risk Treatment**: **Mitigate**

**Risk Owner**: CTO

**Review Frequency**: Monthly (review availability metrics)

---

### **RISK R-005**: 🔴 E-KYC Provider Loses ISO 27001 Certification

| Field | Value |
|-------|-------|
| **Risk ID** | R-005 |
| **Risk Title** | E-KYC Provider Loses ISO 27001 Certification |
| **Classification** | 🟡 **MEDIUM** |
| **Asset** | E-KYC service (Appman), Certogo's ISO 27001 certification |
| **Threat** | Appman fails surveillance audit and loses ISO 27001 certification |
| **Vulnerability** | - Certogo's ISO 27001 certification depends on supplier compliance<br>- Contract may not have strong enough exit clauses |

**Impact Assessment**:
- **Legal/Regulatory**: 4 (High) - Certogo may fail ISO 27001 audit due to supplier non-compliance
- **Reputational**: 3 (Medium) - Questions about due diligence
- **Overall Impact**: **4 (High)**

**Likelihood Assessment**:
- **Inherent Likelihood**: 2 (Low) - Rare for certified companies to lose certification
- **Residual Likelihood**: 1 (Very Low) - Appman has maintained ISO 27001 for [X] years

**Inherent Risk**: 2 × 4 = **8 (Medium)** 🟡
**Residual Risk**: 1 × 4 = **4 (Low)** 🟢

**Existing Controls**:
1. ✅ Annual verification of Appman's ISO 27001 certificate
2. ✅ Contract clause requiring Appman to maintain ISO 27001
3. ✅ Immediate notification if certification status changes

**Additional Controls Planned**:
1. 🔄 Contract clause: Termination right if ISO 27001 lost (30-day grace period to remediate)
2. 🔄 Backup provider pre-qualified (so can switch quickly if needed)

**Risk Treatment**: **Mitigate + Accept (residual low risk)**

**Risk Owner**: Procurement Manager + CISO

**Review Frequency**: Annually (when certificate renewed)

---

### **RISK R-009**: 🔴 Unauthorized Data Processing by E-KYC Sub-processor

| Field | Value |
|-------|-------|
| **Risk ID** | R-009 |
| **Risk Title** | Unauthorized Sub-processing of Biometric Data |
| **Classification** | 🟡 **MEDIUM** |
| **Asset** | Biometric data |
| **Threat** | Appman uses a sub-processor (e.g., cloud provider, ML vendor) without Certogo's approval |
| **Vulnerability** | - Limited visibility into Appman's data processing chain<br>- DPA sub-processor clause may not be enforced |

**Impact Assessment**:
- **Legal/Regulatory**: 4 (High) - PDPA violation (lack of lawful basis for sub-processing)
- **Confidentiality**: 4 (High) - Additional party has access to biometric data
- **Overall Impact**: **4 (High)**

**Likelihood Assessment**:
- **Inherent Likelihood**: 3 (Medium) - Sub-processing is common in SaaS
- **Residual Likelihood**: 2 (Low) - DPA requires prior approval

**Inherent Risk**: 3 × 4 = **12 (High)** 🟠
**Residual Risk**: 2 × 4 = **8 (Medium)** 🟡

**Existing Controls**:
1. ✅ DPA clause requiring written approval for sub-processors
2. ✅ List of approved sub-processors in DPA annex
3. ✅ Quarterly review of Appman's sub-processors

**Additional Controls Planned**:
1. 🔄 Annual audit of Appman's data flow (verify no unauthorized sub-processors)
2. 🔄 Contract penalty for unauthorized sub-processing

**Risk Treatment**: **Mitigate**

**Risk Owner**: DPO

**Review Frequency**: Quarterly

---

### **RISK R-011**: 🔴 E-KYC Provider Change Disruption

| Field | Value |
|-------|-------|
| **Risk ID** | R-011 |
| **Risk Title** | Business Disruption When Changing E-KYC Providers |
| **Classification** | 🟡 **MEDIUM** |
| **Asset** | E-KYC service continuity, customer experience |
| **Threat** | Need to change E-KYC provider (due to performance, cost, or compliance issues) causes service disruption |
| **Vulnerability** | - No documented provider change procedure<br>- Vendor lock-in (API integration tightly coupled to Appman)<br>- No backup provider pre-qualified |

**Impact Assessment**:
- **Availability**: 4 (High) - Potential outage during migration
- **Financial**: 3 (Medium) - Migration costs, lost revenue
- **Reputational**: 3 (Medium) - Customer dissatisfaction if migration poorly handled
- **Overall Impact**: **4 (High)**

**Likelihood Assessment**:
- **Inherent Likelihood**: 2 (Low) - Provider changes are rare but possible
- **Residual Likelihood**: 2 (Low) - Appman performance currently acceptable

**Inherent Risk**: 2 × 4 = **8 (Medium)** 🟡
**Residual Risk**: 2 × 4 = **8 (Medium)** 🟡

**Existing Controls**:
1. ✅ Documented E-KYC provider change procedure (A.5.22)
2. ✅ API abstraction layer (reduces tight coupling)
3. ✅ Contract has 90-day termination notice period

**Additional Controls Planned**:
1. 🔄 Pre-qualify backup E-KYC provider (by Q3 2025)
2. 🔄 Conduct annual provider change simulation exercise
3. 🔄 Develop detailed migration playbook

**Risk Treatment**: **Mitigate**

**Risk Owner**: CTO + Procurement Manager

**Review Frequency**: Annually

---

### **RISK R-012**: 🔴 Inadequate Data Deletion by E-KYC Provider

| Field | Value |
|-------|-------|
| **Risk ID** | R-012 |
| **Risk Title** | E-KYC Provider Fails to Delete Biometric Data After 30 Days |
| **Classification** | 🟠 **HIGH** |
| **Asset** | Biometric data |
| **Threat** | Appman does not delete biometric data within 30 days as required by DPA |
| **Vulnerability** | - No automated verification of deletion<br>- Reliance on Appman's self-reporting |

**Impact Assessment**:
- **Legal/Regulatory**: 5 (Critical) - PDPA violation (data retention beyond purpose)
- **Reputational**: 4 (High) - Breach of customer trust
- **Overall Impact**: **5 (Critical)**

**Likelihood Assessment**:
- **Inherent Likelihood**: 3 (Medium) - Deletion failures do occur in industry
- **Residual Likelihood**: 2 (Low) - Appman has automated deletion process

**Inherent Risk**: 3 × 5 = **15 (Critical)** 🔴
**Residual Risk**: 2 × 5 = **10 (High)** 🟠

**Existing Controls**:
1. ✅ DPA clause mandating 30-day deletion
2. ✅ Quarterly reviews with Appman include deletion compliance check
3. ✅ Sample verification (random selection of deleted records)

**Additional Controls Planned**:
1. 🔄 API endpoint for Certogo to verify deletion status
2. 🔄 Automated monthly audit of deletion logs
3. 🔄 Contractual penalty for non-compliance with deletion timeline

**Risk Treatment**: **Mitigate**

**Risk Owner**: DPO

**Review Frequency**: Monthly

---

## 9. Risk Treatment Decisions
## การตัดสินใจจัดการความเสี่ยง

### 9.1 Risk Treatment Plan Summary | สรุปแผนการจัดการความเสี่ยง

Detailed risk treatment plan maintained in:
แผนการจัดการความเสี่ยงโดยละเอียดเก็บไว้ที่:

`/03-planning/risk-treatment-plan-[YYYY].pdf`

**Summary of Treatment Decisions**:

| Risk Level | Count | Treatment Strategy |
|------------|-------|-------------------|
| 🔴 Critical | 0 | All mitigated to High or lower |
| 🟠 High | 5 | Mitigation in progress (target: reduce to Medium within 3 months) |
| 🟡 Medium | 15 | Mitigation planned (target: reduce to Low within 6 months) |
| 🟢 Low | 30 | Accept and monitor |
| **Total** | **50** | |

### 9.2 Key Risk Treatment Actions | การดำเนินการจัดการความเสี่ยงที่สำคัญ

**Priority 1 (Critical/High Risks)** - Due within 3 months:

1. **R-001**: Biometric Data Breach at E-KYC Provider
   - Action: Obtain Appman's penetration test reports
   - Owner: CISO
   - Due: [DATE]

2. **R-002**: E-KYC Service Outage
   - Action: Identify and pre-qualify backup E-KYC provider
   - Owner: CTO
   - Due: [DATE]

3. **R-003**: SQL Injection Attack
   - Action: Implement Web Application Firewall (WAF)
   - Owner: CTO
   - Due: [DATE]

4. **R-004**: Ransomware Attack
   - Action: Deploy endpoint detection and response (EDR)
   - Owner: CISO
   - Due: [DATE]

5. **R-012**: Inadequate Data Deletion by E-KYC Provider
   - Action: Develop API for deletion verification
   - Owner: DPO
   - Due: [DATE]

---

## 10. Approval and Review
## การอนุมัติและการทบทวน

### 10.1 Risk Assessment Approval | การอนุมัติการประเมินความเสี่ยง

This risk assessment has been reviewed and approved by:
การประเมินความเสี่ยงนี้ได้รับการทบทวนและอนุมัติโดย:

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Risk Assessment Owner (CISO)** | [NAME] | _____________ | [DATE] |
| **Technical Review (CTO)** | [NAME] | _____________ | [DATE] |
| **Data Protection Review (DPO)** | [NAME] | _____________ | [DATE] |
| **Management Approval (CEO)** | [NAME] | _____________ | [DATE] |

### 10.2 Review Schedule | กำหนดการทบทวน

| Review Type | Frequency | Next Review Date |
|-------------|-----------|------------------|
| **Full Risk Assessment** | Annual | [DATE] |
| **E-KYC Provider Risk Review** 🔴 | Quarterly | [DATE] |
| **Risk Treatment Progress Review** | Quarterly | [DATE] |
| **Critical/High Risk Review** | Monthly | [DATE] |

### 10.3 Triggers for Ad-Hoc Review | เงื่อนไขสำหรับการทบทวนพิเศษ

Risk assessment must be updated immediately if:
ต้องอัปเดตการประเมินความเสี่ยงทันทีหาก:

- ✅ Major security incident occurs | เกิดเหตุการณ์ความปลอดภัยที่สำคัญ
- ✅ New asset or service introduced (e.g., new module in LMS) | ทรัพย์สินหรือบริการใหม่ถูกนำมาใช้
- ✅ 🔴 **Change of E-KYC provider** | **เปลี่ยนผู้ให้บริการ E-KYC**
- ✅ Regulatory changes (e.g., new PDPA guidelines) | กฎระเบียบเปลี่ยนแปลง
- ✅ Significant changes to infrastructure or architecture | การเปลี่ยนแปลงโครงสร้างพื้นฐานหรือสถาปัตยกรรมที่สำคัญ
- ✅ Loss of critical certification (e.g., Appman loses ISO 27001) | สูญเสียการรับรองที่สำคัญ

---

## Appendix A: Risk Assessment Worksheet
## ภาคผนวก A: แบบฟอร์มการประเมินความเสี่ยง

**Use this template for documenting each risk**:

```
RISK ID: R-XXX
RISK TITLE: _________________________________

ASSET AT RISK: _________________________________
ASSET OWNER: _________________________________
ASSET CLASSIFICATION: Public / Internal / Confidential / Highly Confidential

THREAT: _________________________________
VULNERABILITY: _________________________________

EXISTING CONTROLS:
1. _________________________________
2. _________________________________
3. _________________________________

LIKELIHOOD ASSESSMENT:
Inherent Likelihood (1-5): ___
Justification: _________________________________

IMPACT ASSESSMENT:
Confidentiality Impact (1-5): ___
Integrity Impact (1-5): ___
Availability Impact (1-5): ___
Financial Impact (1-5): ___
Reputational Impact (1-5): ___
Legal/Regulatory Impact (1-5): ___
Overall Impact (highest): ___

RISK CALCULATION:
Inherent Risk Score: Likelihood × Impact = ___ × ___ = ___
Inherent Risk Level: Low / Medium / High / Critical

EFFECTIVENESS OF EXISTING CONTROLS:
Residual Likelihood (1-5): ___
Residual Risk Score: Likelihood × Impact = ___ × ___ = ___
Residual Risk Level: Low / Medium / High / Critical

RISK TREATMENT DECISION:
☐ Mitigate   ☐ Accept   ☐ Transfer   ☐ Avoid

ADDITIONAL CONTROLS REQUIRED (if Mitigate):
1. _________________________________
2. _________________________________

RISK OWNER: _________________________________
TARGET RESIDUAL RISK: Low / Medium

DUE DATE: _________________________________
REVIEW FREQUENCY: Monthly / Quarterly / Annually
```

---

## Appendix B: E-KYC Provider Risk Questionnaire
## ภาคผนวก B: แบบสอบถามความเสี่ยงของผู้ให้บริการ E-KYC

**Complete this annually for Appman (or any new E-KYC provider)**:

### 1. Security Certifications | การรับรองด้านความปลอดภัย

- [ ] ISO 27001 certified? (Certificate copy required)
- [ ] SOC 2 Type II report available?
- [ ] PDPA compliant? (Documentation required)
- [ ] Other relevant certifications:

### 2. Data Protection | การคุ้มครองข้อมูล

- [ ] Where is biometric data stored? (Country, data center)
- [ ] Encryption at rest? (Algorithm, key length)
- [ ] Encryption in transit? (TLS version)
- [ ] Data retention period for biometric data? (Must be ≤ 30 days)
- [ ] Automated deletion process? (Describe)
- [ ] Sub-processors used? (List all, require approval)

### 3. Availability | ความพร้อมใช้งาน

- [ ] SLA uptime guarantee? (%)
- [ ] Multi-region deployment?
- [ ] Disaster recovery plan? (RTO, RPO)
- [ ] Last 12-month availability? (%)

### 4. Incident Management | การจัดการเหตุการณ์

- [ ] Incident response plan documented?
- [ ] Notification timeline for data breaches? (Must be ≤ 4 hours)
- [ ] Number of security incidents in last 12 months?
- [ ] Lessons learned process?

### 5. Access Control | การควบคุมการเข้าถึง

- [ ] MFA for admin access?
- [ ] Access review frequency?
- [ ] Privileged access management?

### 6. Monitoring | การตรวจสอบ

- [ ] 24/7 security monitoring?
- [ ] SIEM deployed?
- [ ] Log retention period?

### 7. Penetration Testing | การทดสอบเจาะระบบ

- [ ] Last penetration test date?
- [ ] Frequency of pen testing?
- [ ] Copy of pen test report available?

### 8. Financial Stability | เสถียรภาพทางการเงิน

- [ ] Company financial statements reviewed?
- [ ] Any bankruptcy risks?

### 9. Contract Terms | เงื่อนไขสัญญา

- [ ] Data Processing Agreement (DPA) signed?
- [ ] SLA with penalties?
- [ ] Termination notice period? (Days)
- [ ] Transition support guaranteed?

---

**Document Version** | **เวอร์ชันเอกสาร**: 1.0
**Last Updated** | **อัปเดตล่าสุด**: 2025-01-20
**Next Review** | **ทบทวนครั้งต่อไป**: 2026-01-20 (or upon significant change)

---

**Notes for Certogo** | **หมายเหตุสำหรับ Certogo**:

1. This template must be completed annually (at minimum) | ต้องกรอกแม่แบบนี้ทุกปี (อย่างน้อย)
2. E-KYC provider risks (Section 8) are **CRITICAL** for ISO 27001 audit | ความเสี่ยงของผู้ให้บริการ E-KYC (ส่วนที่ 8) **สำคัญมาก** สำหรับการตรวจสอบ ISO 27001
3. Risk assessment must be approved by CEO and CISO | การประเมินความเสี่ยงต้องได้รับการอนุมัติจาก CEO และ CISO
4. Link this risk assessment to Risk Treatment Plan (A.6.1.3) | เชื่อมโยงการประเมินความเสี่ยงนี้กับแผนการจัดการความเสี่ยง
5. Update immediately if E-KYC provider changes | อัปเดตทันทีหากผู้ให้บริการ E-KYC เปลี่ยนแปลง
