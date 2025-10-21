# CISO Assistant Integration Guide for Certogo
# คู่มือการเชื่อมต่อ CISO Assistant สำหรับ Certogo

## Document Information | ข้อมูลเอกสาร

**Organization** | **องค์กร**: Certogo Co., Ltd.
**Purpose** | **วัตถุประสงค์**: Guide for integrating CISO Assistant Community Edition for ISO 27001:2022 compliance tracking
**Version** | **เวอร์ชัน**: 1.0
**Date** | **วันที่**: 2025-01-20
**Status** | **สถานะ**: Implementation Guide

---

## Table of Contents | สารบัญ

1. [What is CISO Assistant?](#1-what-is-ciso-assistant)
2. [Why Use CISO Assistant for Certogo?](#2-why-use-ciso-assistant-for-certogo)
3. [Installation Options](#3-installation-options)
4. [Quick Start Setup](#4-quick-start-setup)
5. [Importing ISO 27001:2022 Framework](#5-importing-iso-270012022-framework)
6. [Mapping Certogo's Implementation](#6-mapping-certogos-implementation)
7. [E-KYC Provider Risk Tracking](#7-e-kyc-provider-risk-tracking-)
8. [Evidence Management](#8-evidence-management)
9. [Compliance Dashboard](#9-compliance-dashboard)
10. [Audit Trail](#10-audit-trail)
11. [Integration with Existing Documentation](#11-integration-with-existing-documentation)
12. [Best Practices](#12-best-practices)

---

## 1. What is CISO Assistant?

**CISO Assistant** is an open-source **Governance, Risk, and Compliance (GRC)** platform designed to help organizations manage multiple compliance frameworks including ISO 27001, SOC 2, NIST, GDPR, and more.

**CISO Assistant** เป็นแพลตฟอร์ม **Governance, Risk, and Compliance (GRC)** แบบโอเพนซอร์ส ที่ออกแบบมาเพื่อช่วยองค์กรจัดการกรอบการปฏิบัติตามหลายมาตรฐาน รวมถึง ISO 27001, SOC 2, NIST, GDPR และอื่นๆ

### Key Features | คุณสมบัติหลัก

- ✅ **Multi-Framework Support** | รองรับหลายมาตรฐาน
  - ISO 27001:2022, ISO 27002:2022
  - SOC 2 Type II
  - NIST CSF, NIST 800-53
  - GDPR, PDPA (Thailand)
  - And 50+ more frameworks

- ✅ **Risk Management** | การจัดการความเสี่ยง
  - Risk register
  - Risk assessment with likelihood and impact
  - Risk treatment tracking
  - **Perfect for tracking E-KYC provider risks** 🔴

- ✅ **Compliance Tracking** | การติดตามการปฏิบัติตาม
  - Control implementation status
  - Evidence attachment
  - Gap analysis
  - Remediation plan tracking

- ✅ **Audit Support** | การสนับสนุนการตรวจสอบ
  - Audit trail (who changed what and when)
  - Report generation (PDF, Excel)
  - Evidence repository
  - Statement of Applicability (SoA) export

- ✅ **Collaboration** | การทำงานร่วมกัน
  - Multi-user support with role-based access
  - Task assignment
  - Comments and discussions
  - Email notifications

- ✅ **Open Source & Free** | โอเพนซอร์สและฟรี
  - Community Edition: 100% free
  - Self-hosted or cloud deployment
  - Active community support
  - GitHub: https://github.com/intuitem/ciso-assistant-community

---

## 2. Why Use CISO Assistant for Certogo?

### Benefits for Certogo | ประโยชน์สำหรับ Certogo

1. **Centralized Compliance Management** | **การจัดการการปฏิบัติตามแบบรวมศูนย์**
   - Single platform for ISO 27001, CSA-STAR, PDPA
   - No need for spreadsheets or multiple tools
   - Real-time compliance status dashboard

2. **E-KYC Provider Risk Tracking** 🔴 | **การติดตามความเสี่ยงของผู้ให้บริการ E-KYC**
   - Create dedicated risk entries for Appman
   - Link risks to controls (A.5.19, A.5.20, A.5.22)
   - Set review reminders (quarterly for E-KYC risks)
   - Track mitigation actions with due dates

3. **Evidence Repository** | **คลังหลักฐาน**
   - Attach evidence files directly to controls
   - Version control for documents
   - Easy access during audits (no scrambling for files)
   - Example: Attach Appman's ISO 27001 certificate to A.5.19

4. **Audit Preparation** | **การเตรียมการตรวจสอบ**
   - Generate Statement of Applicability (SoA) with one click
   - Export compliance reports for auditors
   - Audit trail shows all changes (who, what, when)
   - Gap analysis highlights missing controls

5. **Collaboration** | **การทำงานร่วมกัน**
   - Assign controls to owners (CISO, CTO, DPO)
   - Task assignments with due dates
   - Email notifications for overdue tasks
   - Comments for discussions

6. **Cost Savings** | **การประหยัดต้นทุน**
   - Free (Community Edition)
   - Reduces manual effort (spreadsheets, emails)
   - Faster audit preparation = less consultant time

7. **Scalability** | **ความสามารถในการขยาย**
   - Start with ISO 27001
   - Add SOC 2, PDPA, NIST later
   - Reuse evidence across frameworks

---

## 3. Installation Options

### Option 1: Cloud (Recommended for Quick Start) | ระบบคลาวด์ (แนะนำสำหรับการเริ่มต้นอย่างรวดเร็ว)

**Pros**:
- No setup required
- Instant access
- Automatic updates
- No infrastructure management

**Cons**:
- Data stored on third-party servers (may not be acceptable for highly sensitive data)
- Requires internet connection

**Steps**:
1. Go to https://ciso-assistant.cloud (or check official website for latest URL)
2. Sign up for free account
3. Verify email
4. Log in and start using

**Cost**: Free for Community Edition

---

### Option 2: Self-Hosted (Recommended for Certogo) 🔴

**Pros**:
- Full control over data (data residency in Thailand)
- Can customize as needed
- No data sharing with third parties
- Compliant with PDPA data localization requirements

**Cons**:
- Requires server setup
- Manual updates
- Requires technical expertise

**Recommended for Certogo** because:
- You handle biometric data (highly sensitive) 🔴
- PDPA compliance requires data control
- You already have cloud infrastructure (AWS/Azure/GCP)

---

### Option 2A: Self-Hosted with Docker (Easiest) | ติดตั้งเองด้วย Docker (ง่ายที่สุด)

**Requirements**:
- Docker and Docker Compose installed
- Linux server (Ubuntu 22.04 recommended) or macOS
- Minimum 2 GB RAM, 20 GB disk
- Open ports: 8000 (web interface), 5432 (PostgreSQL - optional)

**Installation Steps**:

```bash
# 1. Clone the repository
git clone https://github.com/intuitem/ciso-assistant-community.git
cd ciso-assistant-community

# 2. Create .env file
cp .env.example .env

# 3. Edit .env file (set secrets)
nano .env
# Set:
# - SECRET_KEY (generate with: openssl rand -base64 32)
# - POSTGRES_PASSWORD (strong password)
# - ALLOWED_HOSTS (your domain or IP)
# - EMAIL_* (SMTP settings for notifications)

# 4. Start the application
docker-compose up -d

# 5. Create superuser account
docker-compose exec backend python manage.py createsuperuser
# Enter email: ciso@certogo.com
# Enter password: [STRONG_PASSWORD]

# 6. Access the application
# Open browser: http://your-server-ip:8000
# Login with superuser credentials
```

**Estimated Setup Time**: 30 minutes

---

### Option 2B: Self-Hosted on Kubernetes (Production) | ติดตั้งเองบน Kubernetes (สำหรับการใช้งานจริง)

For production deployment on AWS EKS, Azure AKS, or GCP GKE.

สำหรับการติดตั้งใช้งานจริงบน AWS EKS, Azure AKS หรือ GCP GKE

**Helm Chart** (if available):
```bash
helm repo add ciso-assistant https://intuitem.github.io/ciso-assistant-helm
helm install ciso-assistant ciso-assistant/ciso-assistant \
  --set postgresql.enabled=true \
  --set ingress.enabled=true \
  --set ingress.hosts[0].host=ciso-assistant.certogo.com
```

**Benefits**:
- High availability
- Auto-scaling
- Backup and disaster recovery
- Integration with existing cloud infrastructure

**Estimated Setup Time**: 2-4 hours (with Kubernetes experience)

---

## 4. Quick Start Setup

### Step 1: Initial Configuration | การกำหนดค่าเริ่มต้น

After logging in to CISO Assistant:

1. **Create Organization** | **สร้างองค์กร**:
   - Name: `Certogo Co., Ltd.`
   - Description: `B2B/B2C SaaS LMS Platform with E-KYC Integration`

2. **Create Domain** | **สร้างโดเมน**:
   - Name: `Certogo LMS + Appman E-KYC`
   - Description: `Information Security Management System (ISMS) covering Certogo LMS platform and third-party E-KYC integration with Appman`

3. **Add Users** | **เพิ่มผู้ใช้**:
   - CISO: `ciso@certogo.com` (Role: Domain Manager)
   - CTO: `cto@certogo.com` (Role: Contributor)
   - DPO: `dpo@certogo.com` (Role: Contributor)
   - Supplier Manager: `procurement@certogo.com` (Role: Contributor)
   - Auditor: `auditor@certogo.com` (Role: Reviewer - read-only)

4. **Configure Settings** | **กำหนดค่าการตั้งค่า**:
   - Time zone: `Asia/Bangkok`
   - Language: `English` (UI language - Thai may be added by community)
   - Date format: `YYYY-MM-DD`

---

## 5. Importing ISO 27001:2022 Framework

CISO Assistant comes with **pre-built frameworks** including ISO 27001:2022.

CISO Assistant มาพร้อมกับ **กรอบมาตรฐานที่สร้างไว้ล่วงหน้า** รวมถึง ISO 27001:2022

### Import ISO 27001:2022 | นำเข้า ISO 27001:2022

1. **Navigate to**: `Library` → `Frameworks`

2. **Find**: `ISO/IEC 27001:2022`
   - Description: Information security, cybersecurity and privacy protection — Information security management systems — Requirements
   - Controls: 93 (Annex A)

3. **Click**: `Import Framework`

4. **Select Domain**: `Certogo LMS + Appman E-KYC`

5. **Confirm Import**

✅ **Result**: All 93 Annex A controls are now imported and ready to be mapped to your implementation.

---

## 6. Mapping Certogo's Implementation

### Step 1: Review All Controls | ทบทวนมาตรการควบคุมทั้งหมด

Navigate to: `Compliance` → `ISO 27001:2022` → `Controls`

You will see all 93 controls grouped by category:
- A.5: Organizational Controls (23)
- A.6: People Controls (8)
- A.7: Physical Controls (14)
- A.8: Technological Controls (34)

### Step 2: Set Applicability Status | กำหนดสถานะการประยุกต์ใช้

For each control, set the status:

| Status in CISO Assistant | Meaning | Use When |
|--------------------------|---------|----------|
| **Applicable** | Fully applicable | Control is relevant and implemented |
| **Not Applicable** | Not applicable | Control is not relevant (with justification) |
| **Partially Applicable** | Partially applicable | Control is relevant but only partially implemented |
| **Planned** | Planned for future | Control is relevant but not yet implemented |

**Example**: Map the controls based on our SoA:

#### A.5.1 Policies for Information Security
- **Status**: `Applicable`
- **Implementation Status**: `Implemented`
- **Owner**: CISO
- **Description**:
  ```
  Information Security Policy approved by CEO on [DATE].
  Covers Certogo LMS and E-KYC integration.
  Reviewed annually.
  ```
- **Evidence**:
  - Upload: `/evidence/policies/information-security-policy.pdf`

#### A.5.19 Information Security in Supplier Relationships 🔴
- **Status**: `Applicable` 🔴 **CRITICAL FOR E-KYC**
- **Implementation Status**: `Implemented`
- **Owner**: Procurement Manager + CISO
- **Description**:
  ```
  5-phase security assessment process for E-KYC providers.
  Current provider: Appman Co., Ltd.
  Annual assessment required.
  Minimum requirements: ISO 27001, PDPA compliance.
  ```
- **Evidence**:
  - Upload: `/evidence/records/supplier-security-assessment/appman-assessment-2025.pdf`
  - Upload: `/evidence/records/appman-iso27001-certificate.pdf`
  - Upload: `/evidence/policies/supplier-security-policy.pdf`

#### A.5.20 Addressing Information Security within Supplier Agreements 🔴
- **Status**: `Applicable` 🔴 **CRITICAL FOR E-KYC**
- **Implementation Status**: `Implemented`
- **Owner**: Procurement Manager + DPO
- **Description**:
  ```
  Contract with Appman includes:
  - Data Processing Agreement (DPA) with 30-day biometric data retention
  - Security requirements (AES-256, TLS 1.3, ISO 27001)
  - SLA 99.9% uptime with penalties
  - Incident notification within 4 hours for data breaches
  - Data deletion certification upon termination
  ```
- **Evidence**:
  - Upload: `/evidence/contracts/appman-service-agreement.pdf`
  - Upload: `/evidence/contracts/appman-dpa.pdf`
  - Upload: `/evidence/contracts/appman-sla.pdf`

#### A.5.22 Monitoring, Review and Change Management of Supplier Services 🔴
- **Status**: `Applicable` 🔴 **CRITICAL FOR E-KYC**
- **Implementation Status**: `Implemented`
- **Owner**: CISO + Procurement Manager
- **Description**:
  ```
  Quarterly security reviews with Appman.
  Monthly performance scorecards (availability, accuracy).
  20-week provider change procedure documented.
  ```
- **Evidence**:
  - Upload: `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/`
  - Upload: `/evidence/records/supplier-monitoring/ekyc-monthly-reports/`
  - Upload: `/evidence/procedures/ekyc-provider-change-procedure.pdf`

### Step 3: Assign Owners | มอบหมายเจ้าของ

Assign each control to responsible person:

| Control Category | Primary Owner |
|------------------|---------------|
| A.5.1-5.4 (Policies, Leadership) | CISO |
| A.5.5-5.8 (External parties, Threat intel) | CISO |
| A.5.9-5.14 (Asset management, Classification) | CISO + DPO |
| A.5.15-5.18 (Access control, Identity) | CTO |
| A.5.19-5.23 (Supplier management) 🔴 | Procurement + CISO |
| A.6 (People) | HR Manager + CISO |
| A.7 (Physical) | Facility Manager + CISO |
| A.8 (Technology) | CTO |

### Step 4: Set Review Dates | กำหนดวันทบทวน

For each control, set review frequency:
- **Most controls**: Annual review
- **E-KYC provider controls (A.5.19-5.22)** 🔴: Quarterly review
- **High-risk controls**: Monthly review

CISO Assistant will send email reminders when reviews are due.

---

## 7. E-KYC Provider Risk Tracking 🔴

One of the most powerful features for Certogo: **Track E-KYC provider risks in CISO Assistant**.

คุณสมบัติที่มีประสิทธิภาพมากที่สุดอย่างหนึ่งสำหรับ Certogo: **ติดตามความเสี่ยงของผู้ให้บริการ E-KYC ใน CISO Assistant**

### Create Risk Entries | สร้างรายการความเสี่ยง

Navigate to: `Risk Management` → `Risks` → `+ Add Risk`

#### Risk R-001: Biometric Data Breach at E-KYC Provider

- **Risk ID**: R-001
- **Title**: Biometric Data Breach at E-KYC Provider (Appman)
- **Category**: Third-Party Risk
- **Asset**: Biometric Data (facial images, ID cards)
- **Owner**: CISO
- **Description**:
  ```
  Risk that Appman (E-KYC provider) suffers a data breach exposing
  customer biometric data (facial images, ID card scans).

  Impact: PDPA fines (up to 5% revenue), reputational damage,
  loss of customer trust.
  ```

- **Threat**: External attacker breaches Appman's systems
- **Vulnerability**: Limited direct control over Appman's security

- **Likelihood (Inherent)**: 3 - Medium
- **Impact**: 5 - Critical
  - Confidentiality: 5 (Critical)
  - Financial: 5 (Critical) - PDPA fines
  - Reputational: 5 (Critical)
  - Legal: 5 (Critical)

- **Inherent Risk Score**: 15 (Critical) 🔴

- **Existing Controls**:
  - Link to Control: `A.5.19` (Supplier security assessment)
  - Link to Control: `A.5.20` (DPA with security requirements)
  - Link to Control: `A.8.24` (Encryption - AES-256, TLS 1.3)

- **Control Effectiveness**: Medium

- **Likelihood (Residual)**: 2 - Low
- **Residual Risk Score**: 10 (High) 🟠

- **Risk Treatment**: Mitigate + Transfer (Cyber insurance)

- **Mitigation Actions**:
  1. **Action**: Request Appman's penetration test reports
     - Owner: CISO
     - Due Date: [DATE]
     - Status: In Progress

  2. **Action**: Conduct third-party audit of Appman
     - Owner: CISO
     - Due Date: [DATE]
     - Status: Planned

  3. **Action**: Purchase cyber insurance covering third-party breaches
     - Owner: CFO
     - Due Date: [DATE]
     - Status: Completed

- **Review Frequency**: Quarterly 🔴

- **Next Review Date**: [DATE]

---

#### Risk R-002: E-KYC Provider Service Outage

- **Risk ID**: R-002
- **Title**: E-KYC Service Outage (Appman Unavailable)
- **Category**: Availability Risk
- **Asset**: E-KYC Verification Service
- **Owner**: CTO

- **Likelihood (Inherent)**: 3 - Medium
- **Impact**: 5 - Critical (Cannot onboard customers)
- **Inherent Risk Score**: 15 (Critical) 🔴

- **Existing Controls**:
  - Link to Control: `A.5.22` (Supplier monitoring)
  - Link to Control: `A.8.14` (Redundancy - graceful degradation)

- **Residual Risk Score**: 10 (High) 🟠

- **Mitigation Actions**:
  1. **Action**: Pre-qualify backup E-KYC provider
     - Owner: CTO + Procurement
     - Due Date: Q2 2025
     - Status: Planned

  2. **Action**: Implement API abstraction layer
     - Owner: CTO
     - Due Date: [DATE]
     - Status: Completed

---

### Risk Dashboard | แดชบอร์ดความเสี่ยง

CISO Assistant provides a **Risk Dashboard** showing:
- Risk heat map (Likelihood vs. Impact)
- Residual risk distribution (Critical, High, Medium, Low)
- Risks by owner
- Overdue mitigation actions
- Trends over time

**For Certogo**: Create a **custom view** filtering for E-KYC risks:
- Filter: `Category = Third-Party Risk` + `Asset contains "E-KYC"`
- Result: All 6 E-KYC risks (R-001 to R-012)

---

## 8. Evidence Management

### Centralized Evidence Repository | คลังหลักฐานแบบรวมศูนย์

Instead of scattered folders, store all evidence in CISO Assistant:

#### For Each Control | สำหรับแต่ละมาตรการควบคุม

1. **Navigate to Control** (e.g., A.5.19)
2. **Click**: `Evidence` tab
3. **Upload Files**:
   - Appman ISO 27001 certificate
   - Supplier security assessment report
   - Contract documents
   - Quarterly security reports

4. **Add Metadata**:
   - File name: `Appman_ISO27001_Certificate_2024-2027.pdf`
   - Description: `Appman's ISO 27001:2013 certificate, valid until 2027-06-30`
   - Upload date: Auto-populated
   - Uploaded by: Auto-populated
   - Version: 1.0

5. **Link to Multiple Controls** (if applicable):
   - A.5.19 (Supplier assessment)
   - A.5.20 (Supplier agreements)

#### Version Control | การควบคุมเวอร์ชัน

When Appman renews their ISO 27001 certificate:
1. Upload new certificate
2. Mark old certificate as `Superseded`
3. CISO Assistant maintains history

**Benefit**: Auditors can see the continuity of Appman's certification.

---

## 9. Compliance Dashboard

### Real-Time Compliance Status | สถานะการปฏิบัติตามแบบเรียลไทม์

Navigate to: `Compliance` → `Dashboard`

**Key Metrics**:
- **Overall Compliance**: 94.6% (88/93 controls applicable + implemented)
- **By Category**:
  - A.5 Organizational: 100% (23/23)
  - A.6 People: 100% (8/8)
  - A.7 Physical: 92.9% (13/14)
  - A.8 Technological: 91.2% (31/34)

- **Controls by Status**:
  - ✅ Implemented: 74
  - 🔶 Partially Implemented: 16
  - 🔄 Planned: 3
  - ❌ Not Applicable: 3

- **Overdue Tasks**: 0 🎉 (keep it this way!)

- **Upcoming Reviews**:
  - A.5.19 (Appman assessment): Due in 15 days 🔴
  - A.5.22 (Quarterly review): Due in 7 days 🔴

### Custom Views for Certogo | มุมมองที่กำหนดเองสำหรับ Certogo

Create custom views:

1. **E-KYC Critical Controls** 🔴:
   - Filter: `Control ID in (A.5.19, A.5.20, A.5.21, A.5.22, A.8.10, A.8.32)`
   - Result: 6 controls to monitor closely

2. **Controls Requiring Evidence Upload**:
   - Filter: `Evidence Count = 0` AND `Status = Implemented`
   - Result: Controls missing evidence (action required!)

3. **Quarterly Review Due**:
   - Filter: `Next Review Date <= [Today + 30 days]`
   - Result: Controls due for review soon

---

## 10. Audit Trail

CISO Assistant automatically logs all changes:
- **Who** made the change (user email)
- **What** was changed (field, old value, new value)
- **When** the change was made (timestamp)

### Example Audit Trail Entries | ตัวอย่างรายการบันทึกการตรวจสอบ

```
2025-01-20 10:30:45 | ciso@certogo.com | Control A.5.19 | Implementation Status changed from "Planned" to "Implemented"
2025-01-20 10:35:12 | ciso@certogo.com | Control A.5.19 | Evidence added: "appman-assessment-2025.pdf"
2025-01-25 14:22:03 | procurement@certogo.com | Risk R-001 | Residual Likelihood changed from "3" to "2" (due to improved controls)
2025-02-01 09:15:30 | cto@certogo.com | Control A.5.22 | Next Review Date set to "2025-05-01"
```

**During Audit**:
- Auditor asks: "When did you implement control A.5.19?"
- You: "January 20, 2025 at 10:30 AM by our CISO" (with proof in audit trail)

---

## 11. Integration with Existing Documentation

### Link CISO Assistant to File Repository | เชื่อมโยง CISO Assistant กับคลังไฟล์

CISO Assistant can reference external files (instead of uploading):

**For large evidence folders** (e.g., `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/`):

1. Store files in shared location (SharePoint, Google Drive, internal file server)
2. In CISO Assistant control, add **External Link**:
   - Name: `Appman Quarterly Security Reports`
   - URL: `https://certogo-sharepoint.com/evidence/ekyc-quarterly-reviews`
   - Description: `Quarterly security reports from Appman (Q1 2024 - present)`

**Benefit**: No need to duplicate large files; auditors can access via link.

### Export Statement of Applicability (SoA) | ส่งออกแถลงการณ์การประยุกต์ใช้

Generate SoA for auditors:

1. Navigate to: `Compliance` → `ISO 27001:2022` → `Reports`
2. Click: `Export Statement of Applicability`
3. Format: PDF or Excel
4. Options:
   - ✅ Include implementation descriptions
   - ✅ Include evidence references
   - ✅ Include justifications for N/A controls
   - ✅ Show control owners
5. Click: `Generate`

**Result**: Professional SoA document ready for CB auditor.

---

## 12. Best Practices

### For Certogo Implementation | สำหรับการนำไปใช้ของ Certogo

1. **Start Small, Iterate** | **เริ่มต้นเล็ก ทำซ้ำ**:
   - Week 1: Import ISO 27001:2022, set applicability (93 controls)
   - Week 2: Upload evidence for critical controls (A.5.19-5.22) 🔴
   - Week 3: Add all E-KYC risks (R-001 to R-012) 🔴
   - Week 4: Assign all controls to owners
   - Week 5: Upload remaining evidence
   - Week 6: Run compliance report, identify gaps

2. **E-KYC Focus** 🔴:
   - Create a **Dashboard Filter**: "E-KYC Critical" showing A.5.19, A.5.20, A.5.22, A.8.10, A.8.32
   - Set **Quarterly Review Reminders** for these controls
   - Upload Appman's ISO 27001 certificate with **expiry date reminder**

3. **Evidence Naming Convention** | **การตั้งชื่อหลักฐาน**:
   - Use consistent naming: `[Vendor]_[DocType]_[Date].pdf`
   - Example: `Appman_ISO27001_Certificate_2024-2027.pdf`
   - Example: `Appman_QuarterlyReport_2025-Q1.pdf`

4. **Assign Tasks with Due Dates** | **มอบหมายงานพร้อมกำหนดเวลา**:
   - "Upload Appman Q1 2025 security report" → Assigned to: Procurement Manager → Due: April 15, 2025
   - Email reminder sent 7 days before due date

5. **Weekly Compliance Check** | **ตรวจสอบการปฏิบัติตามรายสัปดาห์**:
   - Every Monday, CISO reviews:
     - Overdue tasks
     - Upcoming reviews (next 30 days)
     - New risks or incidents to log
   - Takes 15 minutes

6. **Quarterly E-KYC Provider Review** 🔴:
   - Use CISO Assistant to track:
     - Appman's quarterly security report uploaded? ✅
     - Performance scorecard reviewed? ✅
     - Any new risks identified? (Add to CISO Assistant)
     - Certificate still valid? (Check expiry)
   - Document review in CISO Assistant comments

7. **Pre-Audit Export** | **การส่งออกก่อนการตรวจสอบ**:
   - 1 week before audit: Export SoA from CISO Assistant
   - Review for completeness
   - Print or share PDF with auditor

8. **Continuous Improvement** | **การปรับปรุงอย่างต่อเนื่อง**:
   - After audit: Log findings in CISO Assistant as "Corrective Actions"
   - Assign owner and due date
   - Track to closure
   - Generate "Lessons Learned" report

---

## Quick Setup Checklist | รายการตรวจสอบการตั้งค่าอย่างรวดเร็ว

**Week 1: Installation & Setup**
- [ ] Install CISO Assistant (Docker or Cloud)
- [ ] Create organization: Certogo Co., Ltd.
- [ ] Create domain: Certogo LMS + Appman E-KYC
- [ ] Add users: CISO, CTO, DPO, Procurement, Auditor
- [ ] Configure settings (timezone, language)

**Week 2: Import Framework**
- [ ] Import ISO 27001:2022 framework
- [ ] Review all 93 Annex A controls
- [ ] Set applicability status (based on SoA)
- [ ] Assign owners to all controls

**Week 3: E-KYC Provider Evidence** 🔴
- [ ] Upload Appman ISO 27001 certificate → A.5.19
- [ ] Upload Service Agreement → A.5.20
- [ ] Upload DPA → A.5.20
- [ ] Upload quarterly security reports → A.5.22
- [ ] Upload provider change procedure → A.5.22

**Week 4: Risk Management** 🔴
- [ ] Create Risk R-001 (Biometric data breach)
- [ ] Create Risk R-002 (Service outage)
- [ ] Create Risk R-005 (Loss of ISO 27001)
- [ ] Create Risk R-009 (Unauthorized sub-processing)
- [ ] Create Risk R-011 (Provider change disruption)
- [ ] Create Risk R-012 (Inadequate data deletion)
- [ ] Link risks to controls
- [ ] Set quarterly review reminders

**Week 5: Evidence Upload**
- [ ] Upload policies (InfoSec Policy, Supplier Policy, PDPA Policy)
- [ ] Upload risk assessment and treatment plan
- [ ] Upload internal audit report
- [ ] Upload management review minutes
- [ ] Upload training records

**Week 6: Compliance Check**
- [ ] Run compliance dashboard
- [ ] Identify gaps (controls without evidence)
- [ ] Export Statement of Applicability (SoA)
- [ ] Review SoA for completeness
- [ ] Address any gaps

**Week 7: Ongoing Operations**
- [ ] Set up weekly compliance check (every Monday)
- [ ] Set up quarterly E-KYC review process
- [ ] Train team on using CISO Assistant
- [ ] Document CISO Assistant procedures

---

## Support and Resources | การสนับสนุนและแหล่งข้อมูล

### Official Resources | แหล่งข้อมูลอย่างเป็นทางการ

- **GitHub**: https://github.com/intuitem/ciso-assistant-community
- **Documentation**: https://intuitem.gitbook.io/ciso-assistant (check for latest URL)
- **Community Forum**: GitHub Discussions
- **Issue Tracker**: GitHub Issues

### Getting Help | การขอความช่วยเหลือ

1. **Community Support** (Free):
   - Post questions in GitHub Discussions
   - Check existing issues on GitHub
   - Community response time: 1-3 days

2. **Professional Support** (Paid - if needed):
   - Contact Intuitem (creators of CISO Assistant)
   - For implementation assistance, training, customization
   - Response time: < 24 hours

3. **Certogo Internal Support**:
   - CISO: Primary CISO Assistant administrator
   - IT Team: Technical support for installation/infrastructure
   - Procurement: E-KYC provider evidence collection

---

## Conclusion | สรุป

CISO Assistant is a **powerful, free, open-source tool** that can significantly streamline Certogo's ISO 27001:2022 compliance efforts, especially for **managing E-KYC provider risks and evidence**.

CISO Assistant เป็น **เครื่องมือโอเพนซอร์สที่ทรงพลังและฟรี** ที่สามารถปรับปรุงความพยายามในการปฏิบัติตาม ISO 27001:2022 ของ Certogo ได้อย่างมาก โดยเฉพาะสำหรับ **การจัดการความเสี่ยงและหลักฐานของผู้ให้บริการ E-KYC**

**Key Benefits for Certogo**:
1. Centralized compliance tracking (ISO 27001, CSA-STAR, PDPA)
2. **E-KYC risk management** with quarterly review reminders 🔴
3. Evidence repository with version control
4. Audit-ready SoA export
5. Collaboration with task assignments
6. Audit trail for CB auditors
7. **100% FREE** (Community Edition)

**Recommended**: Self-host CISO Assistant on Certogo's cloud infrastructure (AWS/Azure/GCP) for data residency compliance (PDPA).

**แนะนำ**: ติดตั้ง CISO Assistant บนโครงสร้างพื้นฐานคลาวด์ของ Certogo (AWS/Azure/GCP) เพื่อการปฏิบัติตามข้อกำหนดการจัดเก็บข้อมูล (PDPA)

**Estimated Setup Time**: 1 week (part-time)
**Estimated ROI**: Saves 50-100 hours of manual effort per year

---

**Next Steps**:
1. Review this guide with CISO and CTO
2. Decide: Cloud vs. Self-Hosted
3. Allocate 1 week for setup
4. Start with E-KYC controls and risks 🔴
5. Expand to all 93 controls

---

**Document Version**: 1.0
**Last Updated**: 2025-01-20
**Prepared By**: ISMS Implementation Team

**Questions?** Contact:
- CISO: [TBD]
- Project Lead: [TBD]
