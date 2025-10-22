# Incident Response Procedure | ขั้นตอนการตอบสนองต่อเหตุการณ์ด้านความปลอดภัย

**Document Code**: PROC-003
**Version**: 1.0
**Effective Date**: 2024-01-15
**Document Owner**: CISO (Chief Information Security Officer)
**Review Cycle**: Annual

---

## Document Control | การควบคุมเอกสาร

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2024-01-15 | CISO | Initial version - Created comprehensive incident response procedure |

---

## Table of Contents | สารบัญ

1. [Purpose and Scope](#1-purpose-and-scope--วัตถุประสงค์และขอบเขต)
2. [References](#2-references--เอกสารอ้างอิง)
3. [Definitions](#3-definitions--คำจำกัดความ)
4. [Incident Classification](#4-incident-classification--การจำแนกประเภทเหตุการณ์)
5. [Incident Response Team](#5-incident-response-team--ทีมตอบสนองเหตุการณ์)
6. [Incident Response Phases](#6-incident-response-phases--ระยะการตอบสนองเหตุการณ์)
7. [Detection and Reporting](#7-detection-and-reporting--การตรวจจับและรายงาน)
8. [Initial Assessment and Triage](#8-initial-assessment-and-triage--การประเมินและคัดกรองเบื้องต้น)
9. [Containment](#9-containment--การควบคุมเหตุการณ์)
10. [Eradication](#10-eradication--การกำจัดสาเหตุ)
11. [Recovery](#11-recovery--การกลับสู่สภาวะปกติ)
12. [Post-Incident Review](#12-post-incident-review--การทบทวนหลังเหตุการณ์)
13. [Special Case: Biometric Data Breach](#13-special-case-biometric-data-breach--กรณีพิเศษการรั่วไหลของข้อมูลไบโอเมตริกซ์)
14. [PDPC Notification Procedure](#14-pdpc-notification-procedure--ขั้นตอนการแจ้ง-pdpc)
15. [Customer Notification Procedure](#15-customer-notification-procedure--ขั้นตอนการแจ้งลูกค้า)
16. [E-KYC Provider Incident Coordination](#16-e-kyc-provider-incident-coordination--การประสานงานกับผู้ให้บริการ-e-kyc)
17. [Escalation Procedures](#17-escalation-procedures--ขั้นตอนการเพิ่มระดับ)
18. [Tabletop Exercises](#18-tabletop-exercises--การซ้อมรับมือ)
19. [Tools and Resources](#19-tools-and-resources--เครื่องมือและทรัพยากร)
20. [Appendix A: Incident Report Template](#appendix-a-incident-report-template)
21. [Appendix B: PDPC Notification Template](#appendix-b-pdpc-notification-template)
22. [Appendix C: Customer Notification Template](#appendix-c-customer-notification-template)

---

## 1. Purpose and Scope | วัตถุประสงค์และขอบเขต

### 1.1 Purpose | วัตถุประสงค์

This procedure establishes a **comprehensive incident response framework** for Certogo to:

**ขั้นตอนนี้กำหนดกรอบการตอบสนองเหตุการณ์ที่ครอบคลุมสำหรับ Certogo เพื่อ:**

1. **Detect and respond** to security incidents effectively
   - **ตรวจจับและตอบสนอง**ต่อเหตุการณ์ด้านความปลอดภัยอย่างมีประสิทธิภาพ

2. **Minimize impact** of security breaches on business operations and data
   - **ลดผลกระทบ**ของการละเมิดความปลอดภัยต่อการดำเนินธุรกิจและข้อมูล

3. **Comply with legal obligations** under Thailand PDPA (especially Section 37 - 72-hour breach notification) 🔴
   - **ปฏิบัติตามภาระผูกพันทางกฎหมาย**ภายใต้ PDPA ไทย (โดยเฉพาะมาตรา 37 - การแจ้งการละเมิดภายใน 72 ชั่วโมง) 🔴

4. **Coordinate with E-KYC provider** (current: Appman) during biometric data incidents 🔄
   - **ประสานงานกับผู้ให้บริการ E-KYC** (ปัจจุบัน: Appman) ในระหว่างเหตุการณ์ข้อมูลไบโอเมตริกซ์ 🔄

5. **Learn from incidents** through post-incident reviews and continuous improvement
   - **เรียนรู้จากเหตุการณ์**ผ่านการทบทวนหลังเหตุการณ์และการปรับปรุงอย่างต่อเนื่อง

---

### 1.2 Scope | ขอบเขต

**This procedure applies to**:

1. **All security incidents** affecting Certogo's ISMS scope:
   - Data breaches (personal data, biometric data 🔴, course content)
   - System compromises (unauthorized access, malware, ransomware)
   - Service disruptions (DDoS, infrastructure failures)
   - Insider threats (malicious or accidental)
   - Third-party incidents (E-KYC provider breach 🔄, cloud provider outage)

2. **All Certogo personnel**:
   - Employees (full-time, part-time, remote workers)
   - Contractors
   - Third-party service providers (when incident affects Certogo)

3. **All IT systems** within ISMS scope:
   - Production environments (LMS, E-KYC integration API)
   - Development/staging environments
   - Cloud infrastructure (AWS, Azure)
   - Third-party services (Appman E-KYC, email, monitoring)

**Out of Scope**:
- ❌ Customer infrastructure (B2B clients' internal systems)
- ❌ Personal devices (BYOD) unless connected to Certogo systems
- ❌ Non-security incidents (hardware failures without security impact)

---

## 2. References | เอกสารอ้างอิง

### 2.1 Internal Documents

- **POL-001**: Information Security Policy
- **POL-003**: PDPA Compliance Policy
- **POL-004**: Supplier Security Policy
- **PROC-001**: Data Deletion Procedure
- **PROC-002**: E-KYC Provider Change Procedure
- **Risk Assessment**: `/standards/iso27001/03-planning/risk-assessment.md`
- **DPA (Data Processing Agreement)** with Appman Co., Ltd.

### 2.2 External Standards

- **ISO 27001:2022**:
  - A.5.24: Information security incident management planning and preparation
  - A.5.25: Assessment and decision on information security events
  - A.5.26: Response to information security incidents
  - A.5.27: Learning from information security incidents
  - A.5.28: Collection of evidence

- **Thailand PDPA B.E. 2562 (2019)**:
  - **Section 37**: Data breach notification to PDPC within **72 hours** 🔴
  - **Section 38**: Data breach notification to data subjects "without delay"

- **NIST Cybersecurity Framework**: Incident Response (RS) function

---

## 3. Definitions | คำจำกัดความ

| Term | Thai | Definition |
|------|------|------------|
| **Security Incident** | **เหตุการณ์ด้านความปลอดภัย** | An identified occurrence that compromises the confidentiality, integrity, or availability of information assets |
| **Security Event** | **เหตุการณ์ความปลอดภัย** | An observable occurrence in a system or network (may or may not be an incident) |
| **Data Breach** | **การรั่วไหลของข้อมูล** | Unauthorized access, disclosure, or acquisition of personal data |
| **Biometric Data Breach** 🔴 | **การรั่วไหลของข้อมูลไบโอเมตริกซ์** 🔴 | Unauthorized access to facial images, ID card scans (PDPA Section 26 sensitive data) |
| **PDPC** | **คณะกรรมการคุ้มครองข้อมูลส่วนบุคคล** | Personal Data Protection Committee (Thailand regulator) |
| **RTO (Recovery Time Objective)** | **เป้าหมายเวลาการกลับคืน** | Maximum acceptable downtime for a system |
| **Containment** | **การควบคุม** | Actions to limit the scope and impact of an incident |
| **Eradication** | **การกำจัด** | Removal of the root cause of the incident |
| **IRT (Incident Response Team)** | **ทีมตอบสนองเหตุการณ์** | Cross-functional team responsible for managing incidents |

---

## 4. Incident Classification | การจำแนกประเภทเหตุการณ์

### 4.1 Severity Levels | ระดับความรุนแรง

All incidents are classified into **4 severity levels**:

| Severity | Impact | Examples | Response Time |
|----------|--------|----------|---------------|
| **🔴 CRITICAL** | **Catastrophic**: Large-scale data breach, biometric data breach 🔴, complete service outage, regulatory non-compliance | - **Biometric data breach** at E-KYC provider affecting 1,000+ users<br>- Database compromise exposing all user data<br>- Ransomware encrypting production systems | **15 minutes** |
| **🟠 HIGH** | **Severe**: Limited data breach, significant service disruption, unauthorized access to production systems | - Personal data breach (100-999 users)<br>- Production database unauthorized access (no data exfiltration)<br>- DDoS attack causing 50% service degradation | **1 hour** |
| **🟡 MEDIUM** | **Moderate**: Minor data exposure, temporary service degradation, successful phishing attack | - Personal data breach (<100 users)<br>- Malware detected on employee workstation<br>- Unauthorized access to development environment | **4 hours** |
| **🟢 LOW** | **Minor**: Failed attack attempt, policy violation with no data impact | - Failed brute-force login attempts<br>- Phishing email received (not clicked)<br>- Minor configuration error (no data exposure) | **24 hours** |

---

### 4.2 Incident Categories | ประเภทเหตุการณ์

| Category | Thai | Description |
|----------|------|-------------|
| **CAT-01: Data Breach** | **การรั่วไหลของข้อมูล** | Unauthorized access, disclosure, or acquisition of personal data |
| **CAT-02: Biometric Data Breach** 🔴 | **การรั่วไหลของข้อมูลไบโอเมตริกซ์** 🔴 | Breach involving facial images, ID card scans (PDPA Section 26) |
| **CAT-03: System Compromise** | **การบุกรุกระบบ** | Unauthorized access to systems (malware, unauthorized user account) |
| **CAT-04: Service Disruption** | **การหยุดชะงักของบริการ** | DDoS, infrastructure failure, service unavailability |
| **CAT-05: Insider Threat** | **ภัยคุกคามภายใน** | Malicious or accidental actions by employees/contractors |
| **CAT-06: Third-Party Incident** 🔄 | **เหตุการณ์จากบุคคลภายนอก** 🔄 | Incident at E-KYC provider, cloud provider, or other supplier |
| **CAT-07: Phishing/Social Engineering** | **ฟิชชิ่ง/วิศวกรรมสังคม** | Attempted or successful phishing, vishing, smishing |
| **CAT-08: Malware** | **มัลแวร์** | Virus, ransomware, trojan, spyware detected |

---

### 4.3 Classification Decision Tree | ผังการตัดสินใจจำแนกประเภท

```
START: Security event detected
├─ Q1: Does it involve biometric data? 🔴
│  ├─ YES → CRITICAL (CAT-02: Biometric Data Breach)
│  └─ NO → Continue
├─ Q2: Does it involve personal data breach?
│  ├─ YES → Check number of affected users
│  │  ├─ ≥1,000 users → CRITICAL (CAT-01)
│  │  ├─ 100-999 users → HIGH (CAT-01)
│  │  └─ <100 users → MEDIUM (CAT-01)
│  └─ NO → Continue
├─ Q3: Is production system compromised?
│  ├─ YES → Check if data exfiltrated
│  │  ├─ Data exfiltrated → CRITICAL (CAT-03)
│  │  └─ No data exfiltrated → HIGH (CAT-03)
│  └─ NO → Continue
├─ Q4: Is service completely unavailable?
│  ├─ YES → CRITICAL (CAT-04)
│  └─ NO → Check degradation level
│     ├─ >50% degradation → HIGH (CAT-04)
│     ├─ 10-50% degradation → MEDIUM (CAT-04)
│     └─ <10% degradation → LOW (CAT-04)
```

---

## 5. Incident Response Team | ทีมตอบสนองเหตุการณ์

### 5.1 IRT Structure | โครงสร้างทีม IRT

**Core Team** (must participate in all CRITICAL/HIGH incidents):

| Role | Responsibilities | Contact |
|------|------------------|---------|
| **IRT Lead (CISO)** | Overall incident command, decision-making, PDPC notification | Tel: [CISO-PHONE]<br>Email: ciso@certogo.com |
| **DPO (Data Protection Officer)** 🔴 | PDPA compliance, PDPC notification, customer notification for data breaches | Tel: [DPO-PHONE]<br>Email: dpo@certogo.com |
| **IT Security Manager** | Technical investigation, containment, eradication | Tel: [SEC-PHONE]<br>Email: security@certogo.com |
| **DevOps Lead** | System recovery, infrastructure restoration | Tel: [DEVOPS-PHONE]<br>Email: devops@certogo.com |
| **Legal Counsel** | Legal advice, regulatory compliance, contract review | Tel: [LEGAL-PHONE]<br>Email: legal@certogo.com |

**Extended Team** (called in as needed):

| Role | When to Involve |
|------|-----------------|
| **CEO** | CRITICAL incidents, PDPC notification, major customer impact |
| **PR/Communications** | Customer notification, media inquiries, public statements |
| **Customer Success** | Customer communication, impact assessment for B2B clients |
| **External Forensics** | CRITICAL incidents requiring deep investigation, legal evidence collection |
| **E-KYC Provider (Appman)** 🔄 | Biometric data breach 🔴, E-KYC API compromise |

---

### 5.2 Contact Information | ข้อมูลติดต่อ

**Emergency Contact List** (24/7 availability):

```
🔴 CRITICAL Incident Hotline: [HOTLINE-NUMBER]

Primary Contacts:
- CISO: [CISO-PHONE] / ciso@certogo.com
- DPO: [DPO-PHONE] / dpo@certogo.com
- IT Security: [SEC-PHONE] / security@certogo.com

Escalation Chain:
1. IT Security Manager (0-15 min)
2. CISO (15-30 min)
3. CEO (30-60 min) for CRITICAL incidents

External Contacts:
- Appman Security: security@appman.co.th / [APPMAN-PHONE] 🔄
- PDPC: pdpc@mdes.go.th / 02-142-1033 🔴
- AWS Support: [AWS-CASE-NUMBER]
- External Forensics: [FORENSICS-CONTACT]
```

---

## 6. Incident Response Phases | ระยะการตอบสนองเหตุการณ์

### 6.1 NIST Incident Response Lifecycle

Certogo follows the **NIST 6-phase incident response lifecycle**:

```
┌─────────────────────────────────────────────────────────────┐
│                   INCIDENT RESPONSE LIFECYCLE                │
└─────────────────────────────────────────────────────────────┘

Phase 1: PREPARATION
├─ Maintain IRT readiness
├─ Deploy monitoring tools
├─ Conduct tabletop exercises (annual)
└─ Update incident response plans

Phase 2: DETECTION & REPORTING
├─ Monitor security events (SIEM, alerts)
├─ Receive incident reports (employees, customers, E-KYC provider)
└─ Log all events in incident tracking system

Phase 3: INITIAL ASSESSMENT & TRIAGE
├─ Classify incident (CRITICAL/HIGH/MEDIUM/LOW)
├─ Assemble IRT
└─ Begin incident log

Phase 4: CONTAINMENT
├─ Short-term containment (isolate affected systems)
├─ Evidence preservation
└─ Long-term containment (temporary fixes)

Phase 5: ERADICATION
├─ Remove malware, unauthorized access
├─ Patch vulnerabilities
└─ Verify root cause eliminated

Phase 6: RECOVERY
├─ Restore systems to normal operation
├─ Monitor for residual threats
└─ Validate full functionality

Phase 7: POST-INCIDENT REVIEW
├─ Conduct lessons learned meeting (within 5 days)
├─ Update incident response plan
└─ Implement corrective actions
```

**Timeline for CRITICAL Incidents** 🔴:
- Detection → Initial Assessment: **15 minutes**
- Initial Assessment → Containment: **1 hour**
- Containment → Eradication: **4 hours**
- Eradication → Recovery: **24 hours**
- Recovery → Post-Incident Review: **5 days**

---

## 7. Detection and Reporting | การตรวจจับและรายงาน

### 7.1 Detection Sources | แหล่งตรวจจับ

Incidents may be detected from:

1. **Automated Monitoring**:
   - SIEM (Security Information and Event Management) alerts
   - IDS/IPS (Intrusion Detection/Prevention) alerts
   - AWS CloudWatch alarms
   - Application logs (failed logins, API errors)
   - E-KYC API monitoring 🔄

2. **Manual Reporting**:
   - Employee reports (suspicious emails, unusual system behavior)
   - Customer complaints (unauthorized access to accounts)
   - **E-KYC provider notification** 🔄 (Appman reports breach)
   - External security researchers (vulnerability disclosure)
   - Regulatory notification (PDPC informs Certogo of breach)

3. **Third-Party Notifications**:
   - Cloud provider (AWS) security alerts
   - Antivirus/EDR vendor alerts
   - Threat intelligence feeds

---

### 7.2 Reporting Channels | ช่องทางการรายงาน

**All employees MUST report suspected security incidents immediately via**:

#### Option 1: Email 📧
```
To: security@certogo.com
Subject: [SECURITY INCIDENT] Brief description

Body:
- What happened? (describe the event)
- When did it happen? (date/time)
- Who discovered it? (your name)
- What systems are affected?
- Is it still ongoing?
```

#### Option 2: Incident Hotline ☎️
```
🔴 24/7 Security Hotline: [HOTLINE-NUMBER]
```

#### Option 3: SIEM Dashboard (for IT staff)
```
Log in to SIEM: https://siem.certogo.com
Navigate to: Incidents → Create New Incident
```

**DO NOT**:
- ❌ Ignore suspicious activity ("it's probably nothing")
- ❌ Try to investigate alone (may destroy evidence)
- ❌ Delay reporting ("I'll report it tomorrow")
- ❌ Discuss incident on public channels (Slack, email to entire company)

---

### 7.3 Initial Incident Log | การบันทึกเหตุการณ์เบื้องต้น

When receiving a report, **Security Team** immediately creates an incident log:

**Incident ID Format**: `INC-YYYY-MM-DD-###`
**Example**: `INC-2024-01-15-001`

**Incident Log Template** (use `/evidence/templates/incident-log-template.xlsx`):

| Field | Example |
|-------|---------|
| Incident ID | INC-2024-01-15-001 |
| Reported By | John Doe (IT Security Analyst) |
| Reported Date/Time | 2024-01-15 14:35:00 UTC+7 |
| Detection Source | SIEM Alert - Failed Login Attempts |
| Initial Description | 500+ failed login attempts from IP 203.0.113.45 targeting admin accounts |
| Affected Systems | Production LMS (lms.certogo.com) |
| Classification (Preliminary) | 🟡 MEDIUM - CAT-07 (Brute Force Attack) |
| IRT Lead Assigned | CISO |

**All subsequent actions are logged** in this incident log throughout the incident lifecycle.

---

## 8. Initial Assessment and Triage | การประเมินและคัดกรองเบื้องต้น

### 8.1 Assessment Checklist | รายการตรวจสอบการประเมิน

**IRT Lead (CISO)** conducts initial assessment within **15 minutes** (CRITICAL) or **1 hour** (HIGH):

#### Step 1: Confirm Incident Validity
- [ ] **Is this a real incident** or false positive?
- [ ] Review detection source (SIEM logs, user report)
- [ ] Check for similar past events (was this previously classified as benign?)

**If FALSE POSITIVE**:
- Close incident log with reason: "False positive - [explanation]"
- Update detection rules to reduce future false positives
- END

**If REAL INCIDENT**:
- Continue to Step 2

#### Step 2: Classify Incident Severity
Use decision tree from Section 4.3:

- [ ] **Does it involve biometric data?** 🔴
  - YES → **CRITICAL** (CAT-02) → **Immediate CISO + DPO notification**
  - NO → Continue

- [ ] **Does it involve personal data breach?**
  - YES → Count affected users:
    - ≥1,000 → **CRITICAL** (CAT-01)
    - 100-999 → **HIGH** (CAT-01)
    - <100 → **MEDIUM** (CAT-01)
  - NO → Continue

- [ ] **Is production system compromised?**
  - YES → **HIGH** or **CRITICAL** (CAT-03)
  - NO → Continue

- [ ] **Is service unavailable or degraded?**
  - Complete outage → **CRITICAL** (CAT-04)
  - >50% degradation → **HIGH** (CAT-04)
  - 10-50% degradation → **MEDIUM** (CAT-04)
  - <10% degradation → **LOW** (CAT-04)

#### Step 3: Assemble IRT
Based on severity:

**CRITICAL** 🔴:
- ✅ CISO (IRT Lead)
- ✅ DPO
- ✅ IT Security Manager
- ✅ DevOps Lead
- ✅ Legal Counsel
- ✅ CEO (within 30 minutes)
- ✅ External Forensics (if data breach)

**HIGH** 🟠:
- ✅ CISO (IRT Lead)
- ✅ IT Security Manager
- ✅ DevOps Lead
- ⏳ DPO (if data breach)
- ⏳ Legal Counsel (if compliance issue)

**MEDIUM** 🟡:
- ✅ IT Security Manager (IRT Lead)
- ✅ DevOps Lead (if infrastructure issue)

**LOW** 🟢:
- ✅ IT Security Analyst (handles alone, escalates if needed)

#### Step 4: Establish Communication Channel
- [ ] Create **dedicated Slack channel**: `#incident-[INC-ID]` (e.g., `#incident-2024-01-15-001`)
- [ ] Invite all IRT members
- [ ] **Set channel to PRIVATE** (prevent information leakage)
- [ ] Pin incident log link to channel

#### Step 5: Initial Containment Decision
- [ ] **Should affected systems be isolated immediately?**
  - CRITICAL biometric breach 🔴 → **YES** (isolate E-KYC API immediately)
  - Active ransomware → **YES** (disconnect infected systems from network)
  - Suspected data exfiltration → **YES** (block external connections)
  - Failed login attempts → **NO** (continue monitoring, implement IP block)

**If immediate containment required**:
- Execute **Short-Term Containment** (Section 9.1)
- Then continue to full response

---

### 8.2 PDPA Breach Assessment (for Data Breaches) 🔴

**If incident involves personal data breach**, DPO immediately assesses:

#### Question 1: Is this a PDPA-reportable breach?

**PDPA Section 37 requires notification to PDPC if breach is likely to affect data subjects' rights and freedoms.**

**Reportable** ✅:
- Biometric data breach (any number of users) 🔴
- Personal data breach affecting ≥100 users
- Breach involving sensitive data (health, religion, political opinion)
- Breach likely to cause financial harm (credit card data)

**Not Reportable** ❌:
- <10 users affected with non-sensitive data
- Data encrypted with no key compromise
- Internal unauthorized access with no exfiltration (containment successful)

#### Question 2: What is the notification timeline?

**PDPC Notification**: **Within 72 hours** of becoming aware of breach 🔴

**Data Subject Notification**: "Without delay" (interpret as **within 7 days**)

**Countdown Starts**: When Certogo becomes aware (not when breach occurred)

**Example Timeline**:
```
Day 0, 14:00: Breach detected → Countdown starts ⏰
Day 0, 17:00: PDPC notification drafted (53 hours remaining)
Day 1, 10:00: CEO approves PDPC notification (33 hours remaining)
Day 1, 14:00: PDPC notification sent ✅ (48 hours elapsed, 24 hours buffer)
Day 5: Data subject notification sent ✅ (5 days elapsed)
```

---

## 9. Containment | การควบคุมเหตุการณ์

### 9.1 Short-Term Containment | การควบคุมระยะสั้น

**Goal**: **Stop the bleeding** - prevent incident from spreading.

**Timeline**: Execute within **1 hour** (CRITICAL), **4 hours** (HIGH).

#### Containment Actions by Incident Type:

##### CAT-01/CAT-02: Data Breach / Biometric Data Breach 🔴

**Actions**:
1. **Isolate compromised systems**:
   - Disconnect affected servers from network (AWS Security Group: block all inbound/outbound)
   - Disable compromised user accounts (suspend all sessions)

2. **Block attacker access**:
   - Block attacker IP addresses at firewall (AWS NACL, WAF)
   - Revoke compromised API keys/tokens

3. **Preserve evidence**:
   - Take EBS snapshot of affected EC2 instances (for forensics)
   - Export database logs (last 30 days) to S3 immutable storage
   - Do NOT shut down systems yet (RAM contents needed for forensics)

4. **Notify E-KYC provider** 🔄 (if biometric data breach at Certogo's side):
   - Email Appman: security@appman.co.th
   - Subject: "URGENT: Potential Biometric Data Breach at Certogo"
   - Ask Appman to check for suspicious API access from Certogo

**Example - E-KYC API Compromise**:
```bash
# Immediate actions (executed by DevOps Lead within 15 minutes):

# 1. Block all traffic to E-KYC integration API
aws ec2 modify-security-group-rules \
  --group-id sg-ekyc-api \
  --security-group-rules SecurityGroupRuleId=sgr-xxx,SecurityGroupRule='{IpProtocol=-1,CidrIpv4=0.0.0.0/0,Description="INCIDENT CONTAINMENT - Block all"}'

# 2. Revoke E-KYC API credentials
# (Coordinate with Appman to rotate OAuth client secret)

# 3. Snapshot affected systems
aws ec2 create-snapshot \
  --volume-id vol-ekyc-api \
  --description "Forensic snapshot - INC-2024-01-15-001"

# 4. Export API access logs (last 30 days)
aws logs create-export-task \
  --log-group-name /aws/lambda/ekyc-integration \
  --from $(date -d '30 days ago' +%s)000 \
  --to $(date +%s)000 \
  --destination s3://certogo-forensics/INC-2024-01-15-001/
```

##### CAT-03: System Compromise (Malware, Unauthorized Access)

**Actions**:
1. **Isolate infected systems**:
   - Disconnect from network (preserve RAM for forensics)
   - Block lateral movement (firewall rules between VPCs)

2. **Disable compromised accounts**:
   - Suspend user accounts with suspicious activity
   - Force password reset for all users with access to compromised systems

3. **Deploy enhanced monitoring**:
   - Enable VPC Flow Logs (if not already enabled)
   - Increase SIEM log verbosity for affected systems

##### CAT-04: Service Disruption (DDoS, Infrastructure Failure)

**Actions**:
1. **DDoS Mitigation**:
   - Enable AWS Shield Advanced (if not already active)
   - Activate CloudFront rate limiting
   - Contact AWS Support for DDoS Response Team

2. **Infrastructure Failure**:
   - Failover to secondary region (if multi-region setup)
   - Scale up healthy instances (Auto Scaling)

##### CAT-08: Ransomware

**Actions** 🔴:
1. **IMMEDIATE ISOLATION** (within 5 minutes):
   - Shut down infected systems (do NOT attempt to save data)
   - Disconnect backup systems (prevent ransomware from encrypting backups)
   - Block network shares (SMB, NFS)

2. **Do NOT pay ransom** (company policy):
   - Paying does not guarantee data recovery
   - Funding criminal activity
   - Use backups for recovery (PROC-004: Backup Recovery Procedure)

3. **Preserve ransomware sample**:
   - Copy ransomware executable to isolated forensics system
   - Submit to VirusTotal, Malware Analysis Platform

---

### 9.2 Long-Term Containment | การควบคุมระยะยาว

**Goal**: Maintain business operations while preparing for full eradication.

**Timeline**: Hours to days (depends on incident complexity).

**Actions**:
1. **Deploy temporary workarounds**:
   - Restore service on clean systems (from backups)
   - Route traffic around compromised infrastructure
   - Example: If production database compromised, promote read replica to temporary primary

2. **Implement enhanced monitoring**:
   - Deploy additional SIEM sensors
   - Enable full packet capture for affected network segments
   - Monitor for attacker returning

3. **Plan for eradication**:
   - Identify root cause (vulnerability exploited, compromised credentials)
   - Develop patch/fix strategy
   - Schedule maintenance window for full remediation

---

## 10. Eradication | การกำจัดสาเหตุ

### 10.1 Root Cause Analysis | การวิเคราะห์สาเหตุหลัก

**Goal**: Understand **how** the attacker got in and **ensure they can't get back in**.

**Timeline**: **4-24 hours** (CRITICAL incidents).

**5 Whys Technique**:

**Example - Unauthorized Database Access**:
```
Incident: Attacker accessed production database

Why #1: Why did attacker access database?
→ Attacker had valid database credentials

Why #2: Why did attacker have valid credentials?
→ Credentials were leaked in GitHub repository

Why #3: Why were credentials in GitHub repository?
→ Developer committed .env file with production credentials

Why #4: Why did developer commit .env file?
→ No pre-commit hook to prevent committing .env files

Why #5: Why was there no pre-commit hook?
→ Pre-commit hooks not enforced in developer onboarding

ROOT CAUSE: Lack of secure coding training and automated controls
```

**Eradication Actions**:
1. Remove credentials from GitHub (git-secrets scan)
2. Rotate all database credentials
3. Implement pre-commit hooks (prevent .env commits)
4. Add secure coding training to onboarding

---

### 10.2 Eradication Actions by Incident Type

##### CAT-01/CAT-02: Data Breach

**Actions**:
1. **Close attack vector**:
   - Patch vulnerability (SQL injection, XSS, etc.)
   - Rotate compromised credentials (API keys, passwords)
   - Fix misconfigured access controls (S3 bucket permissions)

2. **Remove attacker persistence**:
   - Delete unauthorized user accounts
   - Remove backdoors (web shells, malicious cron jobs)
   - Check for residual malware (full antivirus scan)

3. **Verify data integrity**:
   - Compare database with last known good backup
   - Check for unauthorized data modifications
   - Restore from backup if data integrity compromised

##### CAT-03: System Compromise

**Actions**:
1. **Rebuild compromised systems** (recommended over cleaning):
   - Terminate compromised EC2 instances
   - Deploy fresh instances from trusted AMI (Amazon Machine Image)
   - Restore data from clean backups (verify backup integrity first)

2. **Patch vulnerabilities**:
   - Apply OS security updates (Ubuntu, Windows Server)
   - Update application dependencies (npm audit fix, pip update)
   - Harden configurations (disable unused services, change default ports)

3. **Scan for lateral movement**:
   - Check all systems in same VPC/network segment
   - Review access logs for suspicious activity (CloudTrail, VPC Flow Logs)

##### CAT-08: Ransomware

**Actions**:
1. **Remove ransomware**:
   - Wipe infected systems (do NOT attempt to remove malware manually)
   - Rebuild from clean AMI/image

2. **Decrypt data** (if possible):
   - Check for free decryption tools (No More Ransom project)
   - If no decryption available, restore from backups (PROC-004)

3. **Identify infection vector**:
   - Check for phishing emails (malicious attachments)
   - Review RDP/SSH access logs (brute force attacks)
   - Scan for vulnerable software (unpatched systems)

---

## 11. Recovery | การกลับสู่สภาวะปกติ

### 11.1 Recovery Process | กระบวนการกลับสู่สภาวะปกติ

**Goal**: Restore systems to **normal operation** with **confidence** that threat is eliminated.

**Timeline**: **24-72 hours** (CRITICAL incidents).

#### Recovery Phases:

##### Phase 1: System Restoration

**Actions**:
1. **Restore systems from clean backups** (if systems were rebuilt):
   - Verify backup integrity (checksum validation)
   - Restore to isolated environment first (test before production)
   - Apply all security patches before reconnecting to network

2. **Reconfigure security controls**:
   - Update firewall rules (block attacker IPs, close unused ports)
   - Enable MFA for all admin accounts (if not already enforced)
   - Rotate all credentials (passwords, API keys, certificates)

3. **Verify system integrity**:
   - Run vulnerability scans (Nessus, OpenVAS)
   - Check for unauthorized changes (file integrity monitoring)
   - Validate application functionality (smoke tests)

**Go/No-Go Checklist** (before restoring service):
- [ ] Root cause identified and fixed
- [ ] All patches applied
- [ ] Credentials rotated
- [ ] Backups verified and tested
- [ ] Monitoring in place (SIEM, alerts)
- [ ] **CISO approval** to restore service

##### Phase 2: Service Restoration

**Gradual Rollout** (for CRITICAL incidents):

```
Day 1: Restore service for 10% of users (internal staff)
├─ Monitor for 4 hours
├─ If stable → Continue
└─ If issues → Rollback, investigate

Day 2: Restore service for 50% of users
├─ Monitor for 12 hours
├─ If stable → Continue
└─ If issues → Rollback

Day 3: Restore service for 100% of users
├─ Monitor for 24 hours
└─ Declare recovery complete ✅
```

**Immediate Rollout** (for LOW/MEDIUM incidents):
- Restore service to 100% of users immediately after verification

##### Phase 3: Enhanced Monitoring

**Monitoring Window**: **7 days** after recovery for CRITICAL incidents.

**Monitor for**:
- Attacker returning (same IP, similar attack patterns)
- Residual malware (unusual network traffic, unauthorized processes)
- Data integrity issues (corrupted data, unauthorized modifications)

**SIEM Alerts** (temporarily increase sensitivity):
- Failed login attempts (threshold: 5 → 3)
- Database access anomalies (large data exports)
- Network traffic to known malicious IPs

---

### 11.2 Recovery Validation | การตรวจสอบการกลับสู่สภาวะปกติ

**Validation Checklist**:

- [ ] **Functionality**:
  - [ ] All critical services operational (LMS, E-KYC integration 🔄, API)
  - [ ] No performance degradation (response times within SLA)
  - [ ] User logins successful (test 10 sample accounts)

- [ ] **Security**:
  - [ ] Vulnerability scans show no CRITICAL/HIGH findings
  - [ ] All credentials rotated (database, API keys, admin passwords)
  - [ ] MFA enforced for all admin accounts
  - [ ] Firewall rules updated (attacker IPs blocked)

- [ ] **Data Integrity**:
  - [ ] Database checksums match expected values
  - [ ] No unauthorized data modifications detected
  - [ ] Backup integrity verified (can restore from backup)

- [ ] **Monitoring**:
  - [ ] SIEM alerts functional (test with simulated event)
  - [ ] Enhanced monitoring in place (7-day window)
  - [ ] IRT on standby (ready to respond if attacker returns)

**If ALL checks PASS**:
- CISO declares: **"Recovery Complete"** ✅
- Incident status: **RECOVERY** → **POST-INCIDENT REVIEW**

**If ANY check FAILS**:
- Return to **ERADICATION** phase
- Investigate failure root cause

---

## 12. Post-Incident Review | การทบทวนหลังเหตุการณ์

### 12.1 Lessons Learned Meeting | การประชุมบทเรียนที่ได้รับ

**Timeline**: Within **5 business days** of recovery completion.

**Attendees**:
- All IRT members who participated
- CEO (for CRITICAL incidents)
- External auditors (if required by insurance/regulators)

**Agenda** (90-minute meeting):

#### Part 1: Incident Timeline Review (20 minutes)
- Chronological walkthrough of incident (from detection to recovery)
- Identify key decisions and actions

#### Part 2: What Went Well (15 minutes)
**Examples**:
- ✅ SIEM detected breach within 15 minutes
- ✅ IRT assembled within 30 minutes (met SLA)
- ✅ PDPC notification sent within 48 hours (24-hour buffer)

#### Part 3: What Went Wrong (30 minutes)
**Examples**:
- ❌ Root cause: Developer committed credentials to GitHub (preventable)
- ❌ Delay in containment: Security Group update took 45 minutes (manual process)
- ❌ Communication gap: Customer Success team not informed until Day 2

#### Part 4: Action Items (20 minutes)
**Format**: Use **5W1H** (What, Who, When, Where, Why, How)

| Action | Owner | Deadline | Priority |
|--------|-------|----------|----------|
| **Implement pre-commit hooks** to prevent .env commits | DevOps Lead | 2024-02-01 | 🔴 CRITICAL |
| **Automate Security Group updates** (Infrastructure as Code) | IT Security | 2024-02-15 | 🟠 HIGH |
| **Add Customer Success to IRT contact list** | CISO | 2024-01-20 | 🟡 MEDIUM |

#### Part 5: Documentation Updates (5 minutes)
- [ ] Update Incident Response Procedure (this document) with new learnings
- [ ] Update Risk Assessment with newly identified risks
- [ ] Update training materials (if procedural gap identified)

---

### 12.2 Incident Report | รายงานเหตุการณ์

**Timeline**: Completed within **10 business days** of recovery.

**Report Structure** (use Appendix A template):

1. **Executive Summary** (1 page):
   - Incident overview (what happened, when, impact)
   - Root cause (in non-technical language)
   - Remediation summary
   - Total cost (staff hours, revenue loss, regulatory fines)

2. **Detailed Timeline** (2-3 pages):
   - Chronological sequence of events
   - Key decisions and actions
   - Response time metrics (detection → containment → recovery)

3. **Root Cause Analysis** (1-2 pages):
   - 5 Whys analysis
   - Contributing factors
   - Why existing controls failed

4. **Impact Assessment** (1 page):
   - Users affected (number, types)
   - Data affected (types, volume)
   - Financial impact (revenue loss, response costs)
   - Regulatory impact (PDPC notification, potential fines)

5. **Remediation Actions** (1 page):
   - Immediate actions taken (containment, eradication)
   - Long-term improvements (process changes, technical controls)

6. **Lessons Learned** (1 page):
   - What went well
   - What went wrong
   - Action items (from Section 12.1)

**Distribution**:
- CISO (owner)
- CEO
- Board of Directors (for CRITICAL incidents)
- Insurance provider (if applicable)
- External auditors (if required)

**Storage**:
- `/evidence/records/incident-reports/INC-[ID]-Final-Report.pdf`
- Retain for **7 years** (PDPA requirement)

---

## 13. Special Case: Biometric Data Breach 🔴

### 13.1 Unique Characteristics | ลักษณะเฉพาะ

**Biometric data breaches** are **ALWAYS CRITICAL** 🔴 due to:

1. **PDPA Section 26**: Biometric data = **Sensitive Personal Data**
   - Requires explicit consent (higher bar than regular personal data)
   - Breach penalties: Up to **5 million THB** or **5% of annual revenue**

2. **Irreversibility**: Unlike passwords (can be changed), biometric data is **permanent**
   - Facial features, fingerprints cannot be "reset"
   - Breach has **lifetime impact** on data subjects

3. **Regulatory Scrutiny**: PDPC will investigate ALL biometric breaches
   - Mandatory PDPC notification (72 hours) 🔴
   - Likely on-site audit by PDPC
   - Potential criminal charges (PDPA Section 77)

---

### 13.2 Biometric Breach Response Procedure 🔴

**If biometric data breach occurs** (at Certogo or E-KYC provider):

#### Immediate Actions (0-1 hour):

**Step 1: Assemble CRITICAL Incident Team**
- [ ] CISO (IRT Lead)
- [ ] DPO (PDPA compliance lead) 🔴
- [ ] CEO (within 30 minutes)
- [ ] Legal Counsel
- [ ] External Forensics (engage immediately)
- [ ] **E-KYC Provider (Appman)** 🔄 (if breach at Certogo's side)

**Step 2: Determine Breach Location**
- [ ] **Breach at Certogo?**
  - Certogo does NOT store biometric data (see POL-003, Section 4.1)
  - Check: Could breach be of E-KYC verification results (Pass/Fail)? → NOT biometric data, treat as CAT-01 (Data Breach)
  - If somehow biometric data found at Certogo → **CRITICAL INCIDENT** 🔴, immediate investigation

- [ ] **Breach at E-KYC Provider (Appman)** 🔄
  - Appman notifies Certogo per DPA (24-hour notification requirement)
  - Certogo becomes Data Controller responsible for PDPC notification

**Step 3: Immediate Containment**
- [ ] **If breach at Certogo**:
  - Isolate all systems with access to E-KYC integration API
  - Revoke E-KYC API credentials (coordinate with Appman)
  - Block all API calls to Appman (AWS Security Group)

- [ ] **If breach at Appman** 🔄:
  - Request Appman's incident report (within 24 hours per DPA)
  - Demand Appman's containment actions (isolation, credential rotation)
  - Consider **emergency provider switch** (PROC-002, Section 11: Emergency Migration)

#### Timeline-Critical Actions (1-72 hours):

**Hour 2-24: Root Cause Investigation**
- [ ] Engage external forensics firm (for legal evidence quality)
- [ ] Identify number of affected users
- [ ] Identify types of biometric data exposed (facial images, ID cards)
- [ ] Identify attacker (if possible): IP addresses, attack method

**Hour 24-48: PDPC Notification Preparation**
- [ ] DPO drafts PDPC notification (use Appendix B template)
- [ ] CEO reviews and approves
- [ ] Legal Counsel reviews for accuracy

**Hour 48 (Target): PDPC Notification Sent** 🔴
- [ ] Send to PDPC: pdpc@mdes.go.th
- [ ] Subject: "Personal Data Breach Notification - Certogo Co., Ltd."
- [ ] Include: Incident Report (Appendix B), remediation plan, affected user count
- [ ] **MUST be within 72 hours** 🔴

**Hour 48-72: Data Subject Notification Preparation**
- [ ] Draft customer notification email (use Appendix C template)
- [ ] PR team reviews messaging (prevent panic, maintain trust)
- [ ] Customer Success team briefs account managers (for B2B clients)

**Day 3-5: Data Subject Notification** 🔴
- [ ] Email all affected users ("without delay" per PDPA Section 38)
- [ ] Provide: What happened, what data was exposed, what we're doing, what they should do
- [ ] Set up dedicated support hotline for affected users

---

### 13.3 E-KYC Provider Breach Coordination 🔄

**If Appman (current E-KYC provider) notifies Certogo of breach:**

#### Certogo's Responsibilities as Data Controller:

**Step 1: Demand Information from Appman** (within 24 hours per DPA):
```
To: security@appman.co.th
Cc: legal@appman.co.th
Subject: URGENT: Information Request - Biometric Data Breach

Dear Appman Security Team,

We have received your breach notification. As Data Controller, we require
the following information within 24 hours (per DPA Clause 8.3):

1. Number of Certogo users affected (provide user IDs)
2. Types of biometric data exposed (facial images, ID cards)
3. Root cause of breach (vulnerability exploited, attacker method)
4. Containment actions taken (timestamp, specific actions)
5. Timeline: When breach occurred vs. when Appman detected
6. Evidence: Forensic report, attacker IP addresses, compromised systems

Failure to provide this information will constitute DPA breach and may
trigger emergency provider migration (PROC-002).

Certogo DPO
[DPO-NAME] / dpo@certogo.com
```

**Step 2: Assess Appman's Response**

**Acceptable Response** ✅:
- Full transparency (all 6 questions answered)
- Containment completed within 4 hours of Appman's detection
- Root cause identified with remediation plan
- **Appman offers**: Free credit monitoring for affected users (1 year)

**Action**: Proceed with PDPC notification, maintain Appman relationship

**Unacceptable Response** ❌:
- Delayed response (>24 hours)
- Incomplete information (evading questions)
- No remediation plan
- Appman blames Certogo without evidence

**Action**: **Initiate emergency provider migration** (PROC-002, Section 11: 6-10 weeks)

**Step 3: Joint Remediation Plan**

Certogo + Appman collaborate on:
1. **Immediate**: Credential rotation, system hardening
2. **Short-term** (1-4 weeks): Vulnerability patches, security audit
3. **Long-term** (1-3 months): Architecture review, penetration testing

Certogo monitors Appman's progress (weekly status calls until complete).

---

## 14. PDPC Notification Procedure | ขั้นตอนการแจ้ง PDPC

### 14.1 When to Notify PDPC 🔴

**Mandatory Notification** (PDPA Section 37):

**Notify PDPC within 72 hours if**:
- ✅ Biometric data breach (any number of users) 🔴
- ✅ Personal data breach affecting ≥100 users
- ✅ Breach involving sensitive data (health, religion, political opinion)
- ✅ Breach likely to cause **significant harm** (financial loss, identity theft)

**Examples - Notify PDPC**:
- Biometric data breach at E-KYC provider affecting 50 users → **YES** 🔴
- Database dump exposing 500 user emails + passwords → **YES**
- Ransomware encrypting 1,000 student course records → **YES**

**Examples - No PDPC Notification**:
- 5 user emails accidentally sent to wrong recipient (quickly recalled) → **NO**
- Encrypted backup stolen (encryption key not compromised) → **NO**
- Internal employee viewed 10 user records without authorization (no exfiltration) → **NO** (handle internally)

**When Uncertain**: **Ask DPO immediately** (err on side of notification).

---

### 14.2 PDPC Notification Process

#### Step 1: Prepare Notification (Hour 24-48)

**Use Appendix B Template**. Required information:

1. **Data Controller Details**:
   - Organization name: Certogo Co., Ltd.
   - Registration number: [TAX-ID]
   - DPO contact: [DPO-NAME], dpo@certogo.com, [DPO-PHONE]

2. **Breach Details**:
   - Date/time breach occurred (best estimate if unknown)
   - Date/time Certogo became aware (triggers 72-hour countdown)
   - Nature of breach (unauthorized access, ransomware, lost device)
   - Types of data affected (biometric, personal, sensitive)

3. **Affected Data Subjects**:
   - Number of individuals affected (exact or estimate)
   - Categories (students, instructors, business clients)

4. **Likely Consequences**:
   - Identity theft risk (if biometric data)
   - Financial harm risk (if payment data)
   - Reputational harm

5. **Measures Taken**:
   - Containment actions (system isolation, credential rotation)
   - Remediation actions (patches, security enhancements)
   - Data subject notification plan

6. **Contact Point**:
   - DPO name, email, phone (for PDPC follow-up questions)

#### Step 2: CEO Approval (Hour 47)

- [ ] DPO presents notification to CEO
- [ ] CEO reviews and approves (sign off)
- [ ] Legal Counsel confirms compliance with PDPA Section 37

#### Step 3: Submit to PDPC (Hour 48 - Target) 🔴

**Submission Methods**:

**Option 1: Email** 📧 (Recommended for speed)
```
To: pdpc@mdes.go.th
Subject: Personal Data Breach Notification - Certogo Co., Ltd.

Dear Personal Data Protection Committee,

Pursuant to PDPA Section 37, Certogo Co., Ltd. hereby notifies PDPC of
a personal data breach that occurred on [DATE].

Please find attached:
1. Breach Notification Form (PDF)
2. Incident Report Summary (PDF)

We remain available for any follow-up questions.

Respectfully,
[DPO-NAME]
Data Protection Officer
Certogo Co., Ltd.
dpo@certogo.com / [DPO-PHONE]
```

**Attachments**:
- Breach Notification Form (Appendix B, signed PDF)
- Incident Report Summary (2-page summary from Section 12.2)

**Option 2: Online Portal** (if available)
- Check PDPC website: https://www.pdpc.or.th
- Use official breach notification form

**Option 3: Registered Mail** (slower, use only if email/portal unavailable)
- Address: Office of the Personal Data Protection Committee, Ministry of Digital Economy and Society, [ADDRESS]

#### Step 4: Track PDPC Response

**PDPC may**:
1. **Acknowledge receipt** (within 3 business days)
2. **Request additional information** (respond within 5 business days)
3. **Conduct on-site investigation** (cooperate fully, provide access to systems/logs)
4. **Issue improvement order** (must comply within specified timeframe)
5. **Impose administrative fine** (up to 5 million THB, payable within 30 days)

**DPO Actions**:
- [ ] Log all PDPC communications in `/evidence/records/pdpc-correspondence/`
- [ ] Respond to PDPC requests within required timeframes
- [ ] Engage Legal Counsel if PDPC issues fine/sanctions

---

### 14.3 Late Notification (>72 hours) 🔴

**If 72-hour deadline missed**:

**Step 1: Notify PDPC Immediately** (do not delay further)

**Step 2: Provide Justification**
```
Dear PDPC,

We acknowledge that this notification exceeds the 72-hour requirement
under PDPA Section 37. The delay was due to:

[Reason - must be legitimate]:
- Complex forensic investigation required to determine scope
- Uncertainty about whether breach met notification threshold
- [Other justifiable reason]

We apologize for the delay and have implemented the following measures
to prevent future late notifications:
- [Process improvement 1]
- [Process improvement 2]
```

**Legitimate Reasons** ✅:
- Forensic investigation required to determine affected user count
- Uncertainty about breach severity (good-faith assessment)
- Technical issues (PDPC email server down - use registered mail instead)

**Illegitimate Reasons** ❌:
- "We forgot" (shows negligence)
- "We were too busy" (not acceptable)
- "We hoped breach wouldn't be discovered" (concealment - criminal offense)

**Penalty for Late Notification**:
- PDPC may impose **administrative fine** (up to 5 million THB)
- Reputational damage (media may report "Certogo failed to report breach on time")

---

## 15. Customer Notification Procedure | ขั้นตอนการแจ้งลูกค้า

### 15.1 When to Notify Customers 🔴

**Mandatory Notification** (PDPA Section 38):

**Notify data subjects "without delay" if**:
- ✅ Breach likely to result in **high risk** to rights and freedoms
- ✅ Biometric data breach (any number of users) 🔴
- ✅ Personal data breach with identity theft risk

**Interpretation**: "Without delay" = **within 7 days** of becoming aware.

**Examples - Notify Customers**:
- Biometric data breach → **YES** 🔴 (within 7 days)
- Passwords compromised (hashed but weak algorithm) → **YES** (within 7 days)
- Credit card data exposed → **YES** (within 3 days - higher urgency)

**Examples - No Customer Notification**:
- Encrypted data breach (key not compromised) → **NO** (low risk)
- Internal breach contained before data exfiltration → **NO** (no harm)
- <10 users affected with non-sensitive data → **OPTIONAL** (good practice to notify anyway)

---

### 15.2 Customer Notification Process

#### Step 1: Draft Notification (Day 1-3)

**Use Appendix C Template**. Required elements:

1. **Clear Subject Line**: "Important Security Notice - Action Required"
2. **What Happened** (simple language, avoid technical jargon)
3. **What Data Was Affected** (specific: "facial image and ID card number")
4. **What We're Doing** (containment, remediation, cooperation with PDPC)
5. **What You Should Do** (actionable steps: change password, monitor accounts)
6. **How to Contact Us** (dedicated support hotline, email)

**Tone**:
- ✅ Transparent, honest, apologetic
- ✅ Take responsibility (avoid blaming E-KYC provider publicly)
- ✅ Provide reassurance (but don't minimize severity)
- ❌ Avoid: Defensive, legalistic, vague

#### Step 2: PR Review (Day 3-4)

- [ ] PR/Communications team reviews messaging
- [ ] Ensure consistent messaging (email, website, media statement)
- [ ] Prepare FAQ for Customer Success team

#### Step 3: CEO Approval (Day 4-5)

- [ ] CEO reviews and approves final version
- [ ] Legal Counsel confirms compliance with PDPA Section 38

#### Step 4: Send Notification (Day 5-7) 🔴

**Delivery Methods**:

1. **Email** 📧 (Primary method):
   - Send to all affected users' registered email addresses
   - Subject: "Important Security Notice - Action Required"
   - Use plain text + HTML version (ensure deliverability)

2. **In-App Notification** (Secondary method):
   - Display banner on LMS dashboard for affected users
   - Require acknowledgment (user clicks "I Understand")

3. **SMS** (For CRITICAL breaches, e.g., biometric data):
   - Send SMS to affected users' registered phone numbers
   - "URGENT: Security notice from Certogo. Please check your email immediately."

**Example Email** (Biometric Data Breach):
```
Subject: Important Security Notice - Action Required

Dear [USER-NAME],

We are writing to inform you of a security incident that may affect your
personal information.

WHAT HAPPENED:
On [DATE], we discovered that biometric data (facial images and ID card
scans) processed by our E-KYC provider, Appman Co., Ltd., was accessed
by an unauthorized party. This incident occurred at Appman's systems,
not at Certogo.

WHAT DATA WAS AFFECTED:
The following data may have been accessed:
- Facial photograph (submitted during E-KYC verification)
- ID card image (front side only)
- ID card number
- E-KYC verification date

YOUR CERTOGO ACCOUNT PASSWORD AND COURSE DATA WERE NOT AFFECTED.

WHAT WE'RE DOING:
- We have notified the Personal Data Protection Committee (PDPC)
- We are working with Appman to investigate and secure their systems
- We are reviewing our E-KYC provider relationship

WHAT YOU SHOULD DO:
1. Monitor your identity: Watch for suspicious activity (unauthorized
   accounts opened in your name)
2. Change your Certogo password (as a precaution):
   https://lms.certogo.com/settings/password
3. Contact us if you notice suspicious activity: security@certogo.com

We sincerely apologize for this incident. Protecting your data is our
highest priority.

For questions, contact our dedicated support hotline:
- Email: incident-support@certogo.com
- Phone: [HOTLINE-NUMBER] (24/7 for next 30 days)

Sincerely,
[CEO-NAME]
CEO, Certogo Co., Ltd.
```

#### Step 5: Monitor Response (Day 7-30)

- [ ] Track email open rates (aim for >80% within 7 days)
- [ ] Monitor support hotline volume (staff appropriately)
- [ ] Respond to customer questions within 24 hours
- [ ] Update FAQ based on common questions

---

### 15.3 B2B Customer Notification 🔄

**For business customers** (schools, universities using Certogo LMS):

**Additional Steps**:
1. **Account Manager Outreach** (within 24 hours):
   - Personal call to each B2B customer contact
   - Explain incident, answer questions, provide reassurance

2. **Executive-Level Communication** (for large customers):
   - CEO-to-CEO call/email
   - Offer on-site meeting if requested

3. **Technical Briefing** (if requested):
   - Provide detailed incident report
   - Explain containment and remediation actions
   - Share lessons learned

**B2B Customer Concerns**:
- "Should we inform our students?" → **Yes, we'll provide template email you can send**
- "Can we trust Certogo's security?" → **Here's what we've done to prevent recurrence...**
- "Should we switch to another LMS provider?" → **We understand, but here's our commitment to security...**

---

## 16. E-KYC Provider Incident Coordination | การประสานงานกับผู้ให้บริการ E-KYC

### 16.1 Appman Notifies Certogo of Breach 🔄

**Scenario**: Appman (current E-KYC provider) discovers breach at their systems and notifies Certogo.

**DPA Requirement**: Appman must notify Certogo within **24 hours** of becoming aware.

#### Certogo's Response Checklist:

**Hour 0: Receive Appman Notification**
- [ ] Log notification timestamp (triggers Certogo's 72-hour PDPC countdown)
- [ ] Assemble IRT (CISO, DPO, CEO, Legal Counsel)
- [ ] Classify as **CRITICAL** incident 🔴

**Hour 1-24: Demand Information from Appman**
- [ ] Send information request (see Section 13.3, Step 1)
- [ ] Demand: Affected user count, breach timeline, root cause, containment actions

**Hour 24: Assess Appman's Response**
- [ ] **Acceptable** ✅ → Proceed with joint remediation
- [ ] **Unacceptable** ❌ → Initiate emergency provider migration (PROC-002)

**Hour 24-48: Prepare PDPC Notification**
- [ ] DPO drafts notification using information from Appman
- [ ] CEO approves

**Hour 48: Submit PDPC Notification** 🔴

**Day 3-7: Notify Affected Customers**

**Week 2-4: Joint Remediation Plan**
- [ ] Weekly status calls with Appman (until remediation complete)
- [ ] Certogo CISO reviews Appman's security improvements
- [ ] Independent security audit of Appman (if Certogo demands)

---

### 16.2 Certogo Suspects Appman Breach 🔄

**Scenario**: Certogo detects suspicious activity indicating possible breach at Appman (before Appman notifies Certogo).

**Indicators**:
- E-KYC API returning unexpected errors (mass failures)
- E-KYC verification results inconsistent (Pass for clearly invalid IDs)
- Media reports of Appman breach
- Threat intelligence: Appman mentioned in dark web forums

#### Certogo's Response:

**Step 1: Contact Appman Immediately** ☎️
```
To: security@appman.co.th
Cc: ceo@appman.co.th
Subject: URGENT: Suspected Security Incident at Appman

Dear Appman Security Team,

We have detected [INDICATORS]. We suspect a potential security incident
at Appman's systems.

Please confirm or deny the following within 4 hours:
1. Is Appman currently experiencing a security incident?
2. If yes, does it affect Certogo user data?
3. What is the estimated timeline for resolution?

If we do not receive a response within 4 hours, we will:
- Suspend all E-KYC verifications (as a precaution)
- Initiate emergency provider migration procedures

Certogo CISO
[CISO-NAME] / ciso@certogo.com
```

**Step 2: Precautionary Containment** (if no response in 4 hours)
- [ ] Suspend E-KYC integration (block API calls)
- [ ] Notify customers: "E-KYC verification temporarily unavailable due to provider security review"
- [ ] Begin evaluating alternative E-KYC providers (PROC-002)

**Step 3: Escalate to Appman Management** (if no response in 24 hours)
- [ ] CISO calls Appman CEO directly
- [ ] Demand transparency
- [ ] Threaten contract termination if no response

**Step 4: Emergency Provider Migration** (if confirmed breach + poor response)
- [ ] Invoke PROC-002, Section 11: Emergency Migration (6-10 weeks)

---

## 17. Escalation Procedures | ขั้นตอนการเพิ่มระดับ

### 17.1 Escalation Triggers | สัญญาณเพิ่มระดับ

**Escalate to CISO** if:
- ✅ Incident severity = HIGH or CRITICAL
- ✅ Incident unresolved after 4 hours (MEDIUM) or 1 hour (HIGH)
- ✅ Media inquiries received about incident
- ✅ PDPC contacts Certogo about breach

**Escalate to CEO** if:
- ✅ Incident severity = CRITICAL 🔴
- ✅ Biometric data breach (any number of users) 🔴
- ✅ PDPC notification required
- ✅ Estimated financial impact > 1 million THB
- ✅ Major customer threatens to leave

**Escalate to Board of Directors** if:
- ✅ Estimated financial impact > 10 million THB
- ✅ PDPC threatens license revocation
- ✅ Criminal investigation initiated

---

### 17.2 Escalation Communication Template

**Email Template** (CRITICAL incident to CEO):
```
To: ceo@certogo.com
Cc: ciso@certogo.com, dpo@certogo.com
Subject: 🔴 CRITICAL Security Incident - CEO Action Required

INCIDENT SUMMARY:
- Incident ID: INC-2024-01-15-001
- Severity: 🔴 CRITICAL
- Category: CAT-02 (Biometric Data Breach)
- Detected: 2024-01-15 14:35 UTC+7
- Status: CONTAINMENT (Hour 2)

IMPACT:
- Affected Users: 1,250 users
- Data Exposed: Biometric data (facial images, ID card scans) 🔴
- Breach Location: E-KYC provider (Appman Co., Ltd.)

CEO DECISIONS REQUIRED:
1. [ ] Approve PDPC notification (draft attached, must send within 48 hours)
2. [ ] Approve customer notification (draft attached, send within 7 days)
3. [ ] Authorize emergency provider migration budget (5 million THB estimate)

TIMELINE:
- Hour 48 (Target): PDPC notification must be sent 🔴
- Hour 72 (Deadline): PDPC notification legal deadline 🔴
- Day 7: Customer notification target

NEXT STEPS:
- IRT is conducting forensics (external firm engaged)
- Appman has been notified and demanded information (24-hour response deadline)

Please confirm receipt and provide decisions by 2024-01-15 18:00 (Hour 4).

CISO
[CISO-NAME]
```

---

## 18. Tabletop Exercises | การซ้อมรับมือ

### 18.1 Exercise Schedule | ตารางการซ้อม

**Frequency**: **Twice per year** (every 6 months)

**Scenarios** (rotate each exercise):

| Exercise # | Date | Scenario | Participants |
|------------|------|----------|--------------|
| **2024-Q2** | 2024-06-15 | Biometric data breach at E-KYC provider 🔴 | Full IRT + CEO |
| **2024-Q4** | 2024-12-15 | Ransomware attack on production LMS | Full IRT |
| **2025-Q2** | 2025-06-15 | Insider threat (employee data exfiltration) | Full IRT + HR |
| **2025-Q4** | 2025-12-15 | DDoS attack + data breach (combined) | Full IRT + CEO |

---

### 18.2 Exercise Format | รูปแบบการซ้อม

**Duration**: 2 hours

**Facilitator**: External consultant (recommended) or IT Security Manager

**Agenda**:

**Hour 1: Scenario Walkthrough**
1. Facilitator presents scenario (slide deck with timeline)
2. IRT members respond in real-time:
   - "What would you do in the first 15 minutes?"
   - "Who would you notify?"
   - "What systems would you isolate?"

**Hour 2: Discussion and Improvement**
1. Identify gaps in incident response procedure
2. Identify gaps in IRT member knowledge
3. Action items for improvement

**Example Scenario** (Biometric Data Breach):
```
SCENARIO: E-KYC Provider Biometric Data Breach 🔴

Timeline:
- Day 1, 09:00: Appman emails Certogo: "We detected unauthorized access to
  our biometric database. Investigating. Will update in 24 hours."
- Day 1, 09:30: You (IRT) receive the email.

DISCUSSION QUESTIONS:
1. What is the first action you take? (Classify incident, assemble IRT?)
2. What information do you demand from Appman? (By what deadline?)
3. Do you need to notify PDPC? (When does the 72-hour clock start?)
4. What if Appman refuses to provide details? (Contract termination?)
5. How do you prevent customer panic? (Communication strategy?)

(Facilitator injects new developments every 15 minutes to simulate real incident)
```

---

### 18.3 Post-Exercise Report | รายงานหลังการซ้อม

**Timeline**: Within **5 business days** of exercise.

**Report Structure**:

1. **Exercise Summary**:
   - Date, scenario, participants
   - Facilitator assessment (pass/fail/needs improvement)

2. **Performance Metrics**:
   - Response time: IRT assembly (target: <30 min)
   - Decision quality: Correct severity classification (yes/no)
   - Communication: Clear escalation (yes/no)

3. **Gaps Identified**:
   - **Example**: "DPO was unaware of 72-hour PDPC notification deadline"
   - **Example**: "No pre-approved PDPC notification template (caused delay)"

4. **Action Items**:
   - **Example**: "DPO to complete PDPA training (deadline: 2024-07-01)"
   - **Example**: "Create PDPC notification template (Section 14.2, Appendix B)"

**Storage**: `/evidence/records/tabletop-exercises/TTX-YYYY-MM-DD-Report.pdf`

---

## 19. Tools and Resources | เครื่องมือและทรัพยากร

### 19.1 Incident Response Tools

| Tool | Purpose | Access |
|------|---------|--------|
| **SIEM (Security Information and Event Management)** | Centralized log monitoring, alert management | https://siem.certogo.com |
| **AWS CloudTrail** | AWS API activity logs (who did what, when) | AWS Console → CloudTrail |
| **AWS GuardDuty** | Threat detection (compromised instances, unusual API calls) | AWS Console → GuardDuty |
| **Slack** | IRT communication (dedicated channels per incident) | #incident-[INC-ID] |
| **Google Drive (Secure Folder)** | Incident documentation (restricted access) | /Certogo/Security/Incidents/[INC-ID]/ |
| **External Forensics Firm** | Deep investigation, legal-quality evidence | [FORENSICS-CONTACT] |

---

### 19.2 Contact Lists

**Internal Contacts**:
- `/evidence/templates/irt-contact-list.xlsx` (update quarterly)

**External Contacts**:
- **PDPC**: pdpc@mdes.go.th / 02-142-1033
- **Appman Security**: security@appman.co.th / [APPMAN-PHONE] 🔄
- **AWS Support**: [AWS-CASE-NUMBER]
- **External Forensics**: [FORENSICS-FIRM] / [FORENSICS-CONTACT]
- **Legal Counsel (External)**: [LAW-FIRM] / [LAWYER-CONTACT]
- **Cyber Insurance**: [INSURANCE-COMPANY] / [INSURANCE-CONTACT]

---

### 19.3 Templates and Checklists

**Location**: `/standards/iso27001/06-templates/`

1. **Incident Log Template**: `incident-log-template.xlsx`
2. **PDPC Notification Template**: `pdpc-notification-template.docx` (see Appendix B)
3. **Customer Notification Template**: `customer-notification-template.docx` (see Appendix C)
4. **IRT Contact List**: `irt-contact-list.xlsx`
5. **Post-Incident Review Template**: `post-incident-review-template.pptx`

---

## 20. Appendix A: Incident Report Template

```markdown
# Incident Report: [INC-ID]

**Document Classification**: CONFIDENTIAL

## 1. Executive Summary

**Incident Overview**:
- **Incident ID**: [INC-ID]
- **Detection Date**: [YYYY-MM-DD HH:MM UTC+7]
- **Resolution Date**: [YYYY-MM-DD HH:MM UTC+7]
- **Total Duration**: [X hours/days]
- **Severity**: 🔴 CRITICAL / 🟠 HIGH / 🟡 MEDIUM / 🟢 LOW

**Impact Summary**:
- **Users Affected**: [Number] users
- **Data Affected**: [Types of data]
- **Financial Impact**: [THB amount] (staff hours + revenue loss + fines)
- **Regulatory Impact**: PDPC notification [YES/NO]

**Root Cause** (in one sentence):
[Example: Developer committed production database credentials to public GitHub repository]

**Remediation Summary**:
[Example: Rotated all credentials, implemented pre-commit hooks, added secret scanning to CI/CD]

---

## 2. Detailed Timeline

| Time (UTC+7) | Event | Actions Taken |
|--------------|-------|---------------|
| 2024-01-15 14:00 | Attacker cloned GitHub repository with exposed credentials | (Discovered later) |
| 2024-01-15 14:35 | SIEM detected 500+ failed database login attempts | IT Security Analyst notified |
| 2024-01-15 14:40 | IT Security Analyst confirmed incident, classified as HIGH | Incident log created (INC-2024-01-15-001) |
| 2024-01-15 14:50 | CISO assembled IRT (CISO, DevOps, Legal) | Slack channel #incident-2024-01-15-001 created |
| 2024-01-15 15:00 | **Containment**: Blocked attacker IP, rotated database credentials | AWS Security Group updated |
| 2024-01-15 16:00 | Forensics: Discovered credentials in GitHub (committed 2024-01-10) | Root cause identified |
| 2024-01-15 17:00 | **Eradication**: Removed credentials from GitHub, implemented git-secrets | Vulnerability closed |
| 2024-01-15 18:00 | **Recovery**: Verified database integrity (no data exfiltration) | Service restored |
| 2024-01-20 10:00 | **Post-Incident Review**: IRT meeting, lessons learned documented | Action items assigned |

**Response Time Metrics**:
- Detection → Containment: **25 minutes** ✅ (Target: <1 hour for HIGH)
- Containment → Eradication: **2 hours** ✅ (Target: <4 hours)
- Eradication → Recovery: **1 hour** ✅ (Target: <24 hours)

---

## 3. Root Cause Analysis

**5 Whys**:
1. Why did attacker access database? → Attacker had valid credentials
2. Why did attacker have credentials? → Credentials leaked on GitHub
3. Why were credentials on GitHub? → Developer committed .env file
4. Why did developer commit .env? → No pre-commit hook to prevent it
5. Why no pre-commit hook? → Not part of developer onboarding

**ROOT CAUSE**: Lack of automated controls to prevent credential leakage + insufficient security training.

**Contributing Factors**:
- No secret scanning in CI/CD pipeline
- GitHub repository was public (should be private)
- Database credentials not rotated regularly (credential was 6 months old)

---

## 4. Impact Assessment

**Users Affected**:
- **Number**: 0 users (no data breach, containment successful)
- **Categories**: N/A

**Data Affected**:
- **Types**: None (attacker failed to authenticate to database)
- **Volume**: 0 records

**Financial Impact**:
- **Staff Hours**: 15 hours × 5,000 THB/hour = 75,000 THB
- **Revenue Loss**: 0 THB (no service downtime)
- **Regulatory Fines**: 0 THB (no PDPC notification required)
- **Total**: 75,000 THB

**Regulatory Impact**:
- **PDPC Notification**: NO (no data breach)
- **Customer Notification**: NO (no customer impact)

---

## 5. Remediation Actions

**Immediate Actions** (Completed):
- ✅ Rotated all database credentials (2024-01-15)
- ✅ Blocked attacker IP (2024-01-15)
- ✅ Removed credentials from GitHub (2024-01-15)
- ✅ Changed GitHub repository to PRIVATE (2024-01-15)

**Long-Term Improvements** (In Progress):
- ⏳ Implement pre-commit hooks (git-secrets) - **Deadline: 2024-02-01** (DevOps Lead)
- ⏳ Add secret scanning to CI/CD (GitHub Advanced Security) - **Deadline: 2024-02-15** (IT Security)
- ⏳ Mandatory secure coding training for all developers - **Deadline: 2024-03-01** (CISO)
- ⏳ Quarterly credential rotation policy - **Deadline: 2024-02-01** (IT Security)

---

## 6. Lessons Learned

**What Went Well** ✅:
- SIEM detected attack within 35 minutes (fast detection)
- IRT assembled within 15 minutes (met SLA)
- Containment successful (no data exfiltration)

**What Went Wrong** ❌:
- Preventable incident (should have been caught by code review)
- GitHub repository was public (increased attack surface)
- No automated secret scanning (manual process failed)

**Action Items**:
- See Section 5 (Long-Term Improvements)

---

**Report Prepared By**: [CISO-NAME], CISO
**Report Date**: 2024-01-20
**Report Approved By**: [CEO-NAME], CEO

**Distribution**: CISO, CEO, Board of Directors (for CRITICAL incidents only)
**Retention**: 7 years (PDPA requirement)
```

---

## 21. Appendix B: PDPC Notification Template

```markdown
# Personal Data Breach Notification to PDPC

**To**: Personal Data Protection Committee (PDPC)
**Email**: pdpc@mdes.go.th
**Date**: [YYYY-MM-DD]
**Subject**: Personal Data Breach Notification - Certogo Co., Ltd.

---

## 1. Data Controller Information

**Organization Name**: Certogo Co., Ltd.
**Registration Number**: [TAX-ID]
**Address**: [COMPANY-ADDRESS]

**Data Protection Officer (DPO)**:
- **Name**: [DPO-NAME]
- **Email**: dpo@certogo.com
- **Phone**: [DPO-PHONE]

---

## 2. Breach Details

**Date and Time of Breach**:
- **Breach Occurred**: [YYYY-MM-DD HH:MM UTC+7] (estimated)
- **Breach Discovered**: [YYYY-MM-DD HH:MM UTC+7]
- **PDPC Notification**: [YYYY-MM-DD HH:MM UTC+7] (within 72 hours ✅)

**Nature of Breach**:
[Select one or more]:
- ☐ Unauthorized access (hacking, compromised credentials)
- ☐ Unauthorized disclosure (data sent to wrong recipient)
- ☐ Data loss (lost device, deleted data)
- ☐ Ransomware (data encrypted by malware)
- ☑ Third-party breach (E-KYC provider: Appman Co., Ltd.) 🔄

**Description of Incident**:
[Example for biometric data breach]:
On [DATE], our E-KYC provider, Appman Co., Ltd., notified Certogo that
unauthorized parties accessed their biometric database containing facial
images and ID card scans of Certogo users who completed E-KYC verification.

Appman reported that the breach occurred on [DATE] and was discovered on
[DATE]. The root cause was [unauthorized access via compromised admin credentials].

Certogo does NOT store biometric data (per our Data Processing Agreement with
Appman). All biometric data is processed and stored by Appman under PDPA
Section 26 requirements.

---

## 3. Categories and Number of Affected Data Subjects

**Number of Individuals Affected**: [Number] users (exact count)

**Categories of Data Subjects**:
- ☑ Students (enrolled in courses)
- ☑ Instructors (teaching on platform)
- ☐ Business clients (B2B administrators)

**Geographic Distribution**:
- Thailand: [Number] users
- International: [Number] users (if applicable)

---

## 4. Categories and Volume of Personal Data Affected

**Types of Personal Data**:
- ☑ **Biometric data** (PDPA Section 26 sensitive data) 🔴:
  - Facial photographs ([Number] records)
  - ID card images - front side only ([Number] records)
- ☑ **Identification data**:
  - Full name ([Number] records)
  - ID card number ([Number] records)
  - Date of birth ([Number] records)
- ☐ Email addresses
- ☐ Phone numbers
- ☐ Financial data (credit card, bank account)

**Volume**: [Number] total records

---

## 5. Likely Consequences for Data Subjects

**Risk Assessment**:

**Identity Theft Risk**: 🔴 HIGH
- Biometric data (facial image + ID card) can be used to impersonate data subjects
- Potential unauthorized account creation (banks, government services)

**Financial Harm Risk**: 🟡 MEDIUM
- No financial data exposed directly
- Indirect risk: Identity theft could lead to fraudulent loans

**Reputational Harm**: 🟢 LOW
- No sensitive categories (health, religion, political opinion) exposed

**Mitigation**:
- Certogo is offering [1 year free identity monitoring service] to affected users
- Advised users to monitor financial accounts for suspicious activity

---

## 6. Measures Taken or Proposed to Address the Breach

**Immediate Containment** (Completed on [DATE]):
- Demanded incident report from Appman (E-KYC provider)
- Verified Appman isolated affected systems
- Revoked compromised credentials at Appman
- Blocked API access until Appman confirms containment ✅

**Eradication** (Completed on [DATE]):
- Appman rotated all admin credentials
- Appman patched vulnerability ([specific vulnerability])
- External forensics firm confirmed no residual threat

**Recovery** (Completed on [DATE]):
- Appman restored service with enhanced security controls
- Certogo resumed E-KYC integration on [DATE]
- Enhanced monitoring in place (7-day observation period)

**Long-Term Improvements** (In Progress):
- Quarterly security audits of E-KYC provider (starting [DATE])
- Annual penetration testing of E-KYC integration API (starting [DATE])
- Evaluating backup E-KYC providers (diversification strategy)

---

## 7. Measures Taken or Proposed to Mitigate Possible Adverse Effects

**Data Subject Notification**:
- ✅ Email sent to all affected users on [DATE] (within 7 days of discovery)
- ✅ In-app notification displayed on LMS dashboard
- ✅ SMS sent to affected users (for CRITICAL severity)

**Support Measures**:
- ✅ Dedicated support hotline: [HOTLINE-NUMBER] (24/7 for 30 days)
- ✅ Email support: incident-support@certogo.com
- ✅ FAQ published: https://certogo.com/security-incident-faq

**Compensation** (if applicable):
- ☐ Free credit monitoring service ([Duration])
- ☐ Account credit ([Amount] THB per affected user)
- ☐ Other: [Specify]

---

## 8. Contact Point for Further Information

**Data Protection Officer (DPO)**:
- **Name**: [DPO-NAME]
- **Email**: dpo@certogo.com
- **Phone**: [DPO-PHONE] (available 24/7 for PDPC inquiries)

**Alternative Contact** (if DPO unavailable):
- **CISO**: [CISO-NAME]
- **Email**: ciso@certogo.com
- **Phone**: [CISO-PHONE]

---

## 9. Attachments

1. **Incident Report Summary** (2-page summary from Appendix A)
2. **E-KYC Provider (Appman) Incident Report** (provided by Appman)
3. **Data Subject Notification Email** (copy of email sent to users)

---

**Declaration**:

I, [DPO-NAME], Data Protection Officer of Certogo Co., Ltd., hereby declare
that the information provided in this notification is accurate and complete
to the best of my knowledge.

**Signature**: ________________________
**Date**: [YYYY-MM-DD]
**Name**: [DPO-NAME]
**Title**: Data Protection Officer

---

**Submitted to PDPC on**: [YYYY-MM-DD HH:MM UTC+7]
**Submission Method**: ☑ Email / ☐ Online Portal / ☐ Registered Mail
**Confirmation**: [PDPC-RECEIPT-NUMBER] (if available)
```

---

## 22. Appendix C: Customer Notification Template

```markdown
Subject: Important Security Notice - Action Required

Dear [USER-NAME],

We are writing to inform you of a security incident that may affect your personal information.

---

## What Happened

On [DATE], we discovered that [BRIEF DESCRIPTION OF INCIDENT].

[EXAMPLE for biometric data breach]:
On January 15, 2024, we discovered that biometric data (facial images and
ID card scans) processed by our E-KYC verification provider, Appman Co., Ltd.,
was accessed by an unauthorized party. This incident occurred at Appman's
systems, not at Certogo.

---

## What Data Was Affected

The following personal information may have been accessed:

**Your Data**:
- ☑ Facial photograph (submitted during E-KYC verification on [DATE])
- ☑ ID card image (front side only)
- ☑ ID card number: [xxx-xxxx-xxxx] (last 4 digits shown)
- ☑ E-KYC verification date

**NOT Affected** ✅:
- ✅ Your Certogo account password (encrypted, not compromised)
- ✅ Your course progress and certificates
- ✅ Your payment information (we do not store credit card data)

---

## What We're Doing

We take this incident very seriously and have taken the following actions:

**Immediate Actions**:
- ✅ Notified the Personal Data Protection Committee (PDPC) on [DATE]
- ✅ Demanded full incident report from Appman (E-KYC provider)
- ✅ Verified Appman has contained the breach and secured their systems
- ✅ Engaged external forensics firm to investigate

**Long-Term Actions**:
- Conducting quarterly security audits of Appman
- Evaluating backup E-KYC providers (to reduce dependency)
- Enhancing our data protection controls

---

## What You Should Do

While we have no evidence your data has been misused, we recommend the
following precautions:

**Immediate Actions** (within 7 days):
1. **Change your Certogo password** (as a precaution):
   → https://lms.certogo.com/settings/password

2. **Enable Two-Factor Authentication (2FA)** on your Certogo account:
   → https://lms.certogo.com/settings/security

**Ongoing Monitoring** (next 12 months):
3. **Monitor your identity**: Watch for suspicious activity such as:
   - Unauthorized accounts opened in your name (banks, government services)
   - Suspicious emails/calls claiming to be from Certogo or government agencies

4. **Monitor financial accounts**: Check bank statements for unauthorized transactions

5. **Report suspicious activity**: If you notice anything unusual:
   → Email: incident-support@certogo.com
   → Phone: [HOTLINE-NUMBER] (24/7 available for next 30 days)

---

## Free Identity Monitoring Service

As an apology for this incident, we are offering all affected users:

**12 months of FREE identity monitoring service** with [SERVICE-PROVIDER]

To activate:
1. Visit: https://certogo.com/identity-monitoring
2. Enter your code: [UNIQUE-CODE]
3. Complete registration (no credit card required)

This service will alert you if your personal information appears in data breaches
or is used to open new accounts.

---

## Questions and Support

We understand you may have questions. We're here to help:

**Dedicated Support** (24/7 for next 30 days):
- **Email**: incident-support@certogo.com
- **Phone**: [HOTLINE-NUMBER]
- **FAQ**: https://certogo.com/security-incident-faq

**Common Questions**:
- "Is my password safe?" → YES, passwords are encrypted and not compromised
- "Should I close my Certogo account?" → Not necessary, but we respect your choice
- "Will this happen again?" → We are implementing additional safeguards (see above)

---

## Our Commitment

Protecting your personal data is our highest priority. We sincerely apologize
for this incident and any concern it may cause.

We are committed to:
- ✅ Full transparency about the incident
- ✅ Continuous security improvements
- ✅ Protecting your trust in Certogo

Thank you for your understanding and continued trust in Certogo.

Sincerely,

[CEO-NAME]
Chief Executive Officer
Certogo Co., Ltd.

---

**Legal Notice**: This notification is provided under Thailand Personal Data
Protection Act (PDPA) Section 38. If you have concerns about how your data
is handled, you may contact the Personal Data Protection Committee (PDPC)
at pdpc@mdes.go.th or 02-142-1033.

---

**Unsubscribe**: You cannot unsubscribe from security notices (required by law).
For general marketing emails, visit: https://lms.certogo.com/settings/notifications
```

---

## Document History | ประวัติเอกสาร

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2024-01-15 | CISO | Initial version created with comprehensive incident response framework, E-KYC provider coordination procedures, PDPA compliance (72-hour notification), biometric data breach special procedures |

---

## Approval | การอนุมัติ

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Document Owner** | [CISO-NAME] | _________________ | 2024-01-15 |
| **Reviewed By** | [DPO-NAME] (DPO) | _________________ | 2024-01-15 |
| **Approved By** | [CEO-NAME] (CEO) | _________________ | 2024-01-15 |

---

**Next Review Date**: 2025-01-15 (annual review)

**Document Classification**: CONFIDENTIAL
**Distribution**: IRT Members, CEO, Legal Counsel

---

*This document is part of Certogo's ISO 27001:2022 Information Security Management System (ISMS).*

**Related Documents**:
- POL-001: Information Security Policy
- POL-003: PDPA Compliance Policy
- POL-004: Supplier Security Policy
- PROC-001: Data Deletion Procedure
- PROC-002: E-KYC Provider Change Procedure
