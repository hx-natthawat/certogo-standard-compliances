# Interested Parties and Their Requirements | ผู้มีส่วนได้ส่วนเสียและข้อกำหนดของพวกเขา

**Document Control | การควบคุมเอกสาร**

| Field | Value |
|-------|-------|
| **Document ID** | CONTEXT-003 |
| **Version** | 1.0 |
| **Effective Date** | [To be filled - วันที่มีผลบังคับใช้] |
| **Review Date** | [Annual - ทบทวนทุกปี] |
| **Document Owner** | Chief Information Security Officer (CISO) |
| **Approved By** | Chief Executive Officer (CEO) |
| **Classification** | Internal Use Only - ใช้ภายในองค์กรเท่านั้น |
| **Related Standards** | ISO 27001:2022 Clause 4.2 |

---

## 1. Purpose | วัตถุประสงค์

This document identifies and analyzes the **interested parties** (stakeholders) that are relevant to the Information Security Management System (ISMS), and determines their **requirements related to information security**.

ISO 27001:2022 Clause 4.2 requires organizations to identify:
- Interested parties relevant to the ISMS
- Requirements of these interested parties relevant to information security

**Thai | ไทย**: เอกสารนี้ระบุและวิเคราะห์ผู้มีส่วนได้ส่วนเสียที่เกี่ยวข้องกับระบบการจัดการความมั่นคงปลอดภัยสารสนเทศ (ISMS) และกำหนดข้อกำหนดของพวกเขา

---

## 2. Identification of Interested Parties | การระบุผู้มีส่วนได้ส่วนเสีย

### 2.1 Stakeholder Categories | ประเภทผู้มีส่วนได้ส่วนเสีย

Certogo has identified the following interested parties:

| # | Interested Party | Type | ISMS Relevance | Priority |
|---|------------------|------|----------------|----------|
| 1 | B2B Customers (Organizations) | External | High | 🔴 Critical |
| 2 | B2C Users (Individual Learners) | External | High | 🔴 Critical |
| 3 | E-KYC Provider (Current: Appman) 🔴 | External | High | 🔴 Critical |
| 4 | Regulators (PDPC, Certification Bodies) | External | High | 🔴 Critical |
| 5 | Shareholders/Owners | Internal | Medium | 🟠 High |
| 6 | Employees | Internal | High | 🟠 High |
| 7 | Cloud Infrastructure Provider | External | Medium | 🟡 Medium |
| 8 | Other Third-Party Suppliers | External | Medium | 🟡 Medium |
| 9 | Competitors | External | Low | 🟢 Low |
| 10 | Media and Public | External | Low | 🟢 Low |

---

## 3. Detailed Stakeholder Analysis | การวิเคราะห์ผู้มีส่วนได้ส่วนเสียโดยละเอียด

### 3.1 B2B Customers (Organizations) 🔴

#### 3.1.1 Who They Are | พวกเขาคือใคร

- Organizations using Certogo LMS for employee training
- Sectors: Banking, Healthcare, Manufacturing, Government, Energy, Retail
- Size: 50-10,000 employees per organization
- Geography: Primarily Thailand, some ASEAN countries
- Examples: [List 2-3 representative customers if permitted]

#### 3.1.2 Their Information Security Requirements | ข้อกำหนดด้านความมั่นคงปลอดภัย

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **Data Confidentiality**: Customer employee data (names, emails, training records) must be protected from unauthorized access | - Multi-tenant isolation (customer data segregated)<br>- Encryption at rest (AES-256) and in transit (TLS 1.3)<br>- Role-based access control (RBAC) | ✅ Implemented |
| **Data Integrity**: Training records and certificates must be accurate and tamper-proof | - Audit trails for all changes<br>- Certificate verification system<br>- Version control for course content | ✅ Implemented |
| **Service Availability**: LMS platform must be available 24/7 (SLA: ≥ 99.5% uptime) | - Multi-AZ deployment<br>- Load balancing<br>- Disaster recovery (Singapore region)<br>- RTO < 4 hours | ✅ Implemented |
| **Compliance**: Certogo must comply with PDPA and other relevant regulations | - PDPA Compliance Policy (POL-003)<br>- DPO appointed<br>- Data subject rights procedures | ✅ Implemented |
| **ISO 27001 Certification**: Many customers require suppliers to be ISO 27001 certified | - ISO 27001:2022 implementation underway<br>- Target certification: 6-12 months | 🔄 In Progress |
| **Security Audits**: Customers may request security questionnaires or audits | - Security questionnaire template prepared<br>- SOC 2 Type II report (if available)<br>- Right-to-audit clause in contracts | ✅ Implemented |
| **Incident Notification**: Customers must be notified of security incidents affecting their data within 24 hours | - Incident response procedure with customer notification SLA<br>- Communication templates | ✅ Implemented |
| **Data Portability**: Customers can export their data (PDPA right to data portability) | - Data export API<br>- CSV/JSON export functionality | ✅ Implemented |
| **Data Deletion**: Upon contract termination, customer data must be deleted within 30 days | - Data deletion procedure (PROC-001)<br>- Certificate of deletion provided | ✅ Implemented |

#### 3.1.3 How We Engage | การมีส่วนร่วม

- **Contract Negotiations**: Security requirements discussed during sales process
- **Security Questionnaires**: Respond to RFPs and security assessments
- **Quarterly Business Reviews** (for enterprise customers): Discuss security posture, incidents, improvements
- **Customer Support**: Security inquiries via support ticket or dedicated account manager

---

### 3.2 B2C Users (Individual Learners) 🔴

#### 3.2.1 Who They Are | พวกเขาคือใคร

- Individual users accessing Certogo LMS directly (not through employer)
- Demographics: 18-65 years old, primarily Thailand-based (95%)
- Use cases:
  - Professional certifications (e.g., occupational safety, first aid)
  - Skill development (language, IT skills, soft skills)
  - Regulated training requiring identity verification (via E-KYC) 🔴

#### 3.2.2 Their Information Security Requirements | ข้อกำหนดด้านความมั่นคงปลอดภัย

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **Personal Data Protection**: Name, email, phone, ID card number must be protected | - Encryption at rest and in transit<br>- Access control (users can only see their own data)<br>- PDPA Compliance Policy | ✅ Implemented |
| **🔴 Biometric Data Protection**: Facial images and ID card scans (E-KYC) must be handled with HIGHEST security | - **Certogo does NOT store biometric data**<br>- E-KYC provider (Appman) processes and deletes after 30 days<br>- ISO 27001 certified E-KYC provider<br>- DPA with PDPA-compliant clauses | ✅ Implemented |
| **Consent and Transparency**: Users must understand how their data is used | - Privacy Notice (clear, plain language, Thai/English)<br>- Explicit consent for E-KYC (separate checkbox) 🔴<br>- Cookie consent | ✅ Implemented |
| **Data Subject Rights**: Users can access, rectify, delete, or port their data (PDPA Sections 28-35) | - Data subject rights request form<br>- Self-service data export<br>- 30-day SLA for rights requests<br>- DPO contact (privacy@certogo.com) | ✅ Implemented |
| **Account Security**: Protect user accounts from unauthorized access | - Strong password requirements (min 12 chars, complexity)<br>- Optional MFA (multi-factor authentication)<br>- Session timeout (30 minutes inactivity)<br>- Password reset (OTP via email) | ✅ Implemented |
| **Data Breach Notification**: Users must be notified if their data is breached | - PDPA Section 37 compliance (72-hour notification)<br>- Clear breach notification templates<br>- DPO coordinates notification | ✅ Implemented |

#### 3.2.3 How We Engage | การมีส่วนร่วม

- **Privacy Notice**: Displayed during account registration and available on website
- **Customer Support**: Help desk for privacy inquiries (privacy@certogo.com)
- **Data Subject Rights Requests**: Online form + email channel
- **Breach Notifications**: Email + in-app notification (if breach occurs)

---

### 3.3 E-KYC Provider (Current: Appman Co., Ltd.) 🔴

#### 3.3.1 Who They Are | พวกเขาคือใคร

- **Current Provider**: Appman Co., Ltd. (Thailand-based)
- **Service**: Digital identity verification (E-KYC)
  - Facial recognition and liveness detection
  - ID card OCR (Optical Character Recognition)
  - Match verification (selfie vs. ID card photo)
- **Data Processed**: **Biometric data** (facial images, ID card scans) - PDPA Section 26 sensitive data 🔴
- **Role**: Data Processor (Certogo is Data Controller under PDPA)

**⚠️ IMPORTANT**: E-KYC provider may change in the future (business decision, performance issues, cost). Certogo maintains **provider change capability** (20-week migration procedure).

#### 3.3.2 Their Requirements from Certogo | ข้อกำหนดของพวกเขาจาก Certogo

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **Clear Scope of Work**: Define what E-KYC services are needed | - Service Agreement with clear scope<br>- API integration specifications<br>- SLA targets (99% availability) | ✅ Implemented |
| **Lawful Basis for Processing**: Certogo must have legal basis to send biometric data to E-KYC provider | - User explicit consent obtained (PDPA Section 26)<br>- Consent logged with timestamp | ✅ Implemented |
| **Data Minimization**: Send only necessary data (ID card image, selfie, user consent timestamp) | - API sends minimal data<br>- No extraneous user data (email, phone, etc.) sent to E-KYC provider | ✅ Implemented |
| **Timely Payment**: Pay for E-KYC services per contract terms | - Billing process established<br>- Payment within 30 days of invoice | ✅ Implemented |
| **Reasonable Request Volume**: Don't exceed API rate limits | - Rate limiting on Certogo side<br>- Monitoring to prevent abuse | ✅ Implemented |

#### 3.3.3 Certogo's Requirements from E-KYC Provider | ข้อกำหนดของ Certogo จากผู้ให้บริการ E-KYC

| Requirement | E-KYC Provider's Response | Verification | Status |
|-------------|---------------------------|--------------|--------|
| **🔴 ISO 27001 Certification**: E-KYC provider MUST be ISO 27001 certified | - Appman is ISO 27001 certified<br>- Certificate expiry: [Date] | - Certogo reviews certificate annually<br>- Request renewed cert 3 months before expiry | ✅ Verified |
| **🔴 Biometric Data Encryption**: Encrypt biometric data at rest (AES-256 min) and in transit (TLS 1.3 min) | - Appman confirms AES-256 at rest, TLS 1.3 in transit<br>- Security assessment score: [X/100] | - Security questionnaire (100+ questions)<br>- Penetration test report review | ✅ Verified |
| **🔴 30-Day Data Retention**: Delete biometric data after 30 days maximum | - DPA specifies 30-day retention<br>- Automated deletion process | - Certogo DPO requests quarterly deletion verification<br>- Certificate of deletion | ✅ Contractual |
| **🔴 Thailand Data Localization**: Store biometric data in Thailand ONLY (no cross-border transfer) | - Appman confirms Thailand data center<br>- Bangkok region | - DPA includes data localization clause<br>- Certogo verifies in security assessment | ✅ Contractual |
| **99% Service Availability**: E-KYC API available 99% of time (measured monthly) | - Appman commits to 99% SLA<br>- Service credits for breaches | - Certogo monitors API uptime (health checks every 5 minutes)<br>- Monthly SLA reports | ✅ Monitored |
| **24-Hour Breach Notification**: Notify Certogo within 24 hours of security incident | - DPA specifies 24-hour notification<br>- Appman security contact: [email/phone] | - Incident response drill (annual)<br>- Test notification process | ✅ Contractual |
| **Sub-Processor Approval**: Obtain Certogo's written consent before engaging sub-processors | - DPA requires approval<br>- Current sub-processors: [List or None] | - Certogo reviews sub-processor list annually<br>- New sub-processors trigger security assessment | ✅ Contractual |
| **Quarterly Security Reports**: Provide security posture updates (incidents, vulnerabilities, pen test summary) | - Appman provides quarterly reports | - Certogo CISO reviews each report<br>- Escalate if concerns arise | 🔄 In Progress |
| **Audit Rights**: Certogo may audit Appman's biometric data handling (annually) | - DPA grants audit rights | - Certogo plans audit for [Year]<br>- May engage third-party auditor | ⏳ Planned |

#### 3.3.4 How We Engage | การมีส่วนร่วม

- **Quarterly Security Reviews**: CISO + Appman security lead discuss performance, incidents, improvements
- **Annual Contract Review**: Procurement + Legal review pricing, terms, SLA compliance
- **Incident Coordination**: Immediate escalation if Appman detects incident affecting Certogo data
- **Change Notifications**: Appman notifies Certogo 30 days before infrastructure changes (data center, sub-processors)

---

### 3.4 Regulators (PDPC, Certification Bodies) 🔴

#### 3.4.1 Who They Are | พวกเขาคือใคร

1. **Personal Data Protection Committee (PDPC)** - Thailand:
   - Government agency enforcing PDPA
   - Contact: https://www.pdpc.or.th, pdpc@mdes.go.th, 02-141-6993

2. **ISO 27001 Certification Bodies (CB)**:
   - Accredited organizations that audit and certify ISO 27001 compliance
   - Examples: SGS, BSI, TÜV, MASCI (Thailand)

#### 3.4.2 Their Information Security Requirements | ข้อกำหนดด้านความมั่นคงปลอดภัย

**A. PDPC (Personal Data Protection Committee)**

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **PDPA Compliance**: Process Personal Data lawfully, fairly, transparently (PDPA Sections 19-27) | - PDPA Compliance Policy (POL-003)<br>- Privacy Notice (Thai/English)<br>- Consent management | ✅ Implemented |
| **🔴 Sensitive Data Protection**: Biometric data (PDPA Section 26) requires explicit consent | - Explicit consent checkbox for E-KYC (separate from general consent)<br>- Consent logged with timestamp | ✅ Implemented |
| **DPO Appointment**: Appoint Data Protection Officer (PDPA Section 40) | - DPO appointed: [Name]<br>- Contact: privacy@certogo.com | ✅ Implemented |
| **🔴 72-Hour Breach Notification**: Notify PDPC within 72 hours if breach likely to affect rights and freedoms (PDPA Section 37) | - Incident response procedure includes PDPC notification<br>- Breach notification template<br>- DPO coordinates notification | ✅ Implemented |
| **Data Subject Rights**: Facilitate data subject rights (access, rectification, deletion, portability, etc.) - PDPA Sections 28-35 | - Data subject rights request form<br>- 30-day SLA<br>- Self-service data export | ✅ Implemented |
| **Record of Processing Activities (ROPA)**: Maintain records of data processing activities (PDPA Section 39) | - ROPA maintained at `/evidence/records/ropa.xlsx`<br>- Updated quarterly by DPO | ✅ Implemented |
| **DPIA for High-Risk Processing**: Conduct Data Protection Impact Assessment for biometric data (PDPA Section 37/1) | - DPIA conducted for E-KYC biometric processing<br>- File: `/evidence/records/dpia/ekyc-biometric-dpia.pdf` | ✅ Implemented |

**B. ISO 27001 Certification Bodies (CB)**

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **ISO 27001:2022 Compliance**: Implement all mandatory clauses (4-10) and applicable Annex A controls | - All 93 Annex A controls addressed in SoA<br>- 74 fully applicable, 16 partially, 3 not applicable<br>- Compliance rate: 94.6% | ✅ Documented |
| **ISMS Documentation**: Maintain policies, procedures, records | - 3 policies created (8,000+ lines)<br>- SoA, risk assessment, audit checklist<br>- Evidence collection 20% complete | 🔄 In Progress |
| **Internal Audits**: Conduct internal audits annually | - Internal audit planned for [Month/Year]<br>- Auditor: [Internal/External] | ⏳ Planned |
| **Management Review**: CEO reviews ISMS performance annually | - Management review planned for [Month/Year] | ⏳ Planned |
| **Corrective Actions**: Close audit findings promptly (Critical: 7 days, High: 30 days) | - Corrective action tracking in ISMS system<br>- CISO monitors closure | ✅ Process Defined |
| **Evidence Availability**: Provide evidence to CB during audit (signed policies, records, logs) | - Evidence repository at `/evidence/`<br>- Audit preparation checklist (153 items) | 🔄 In Progress |

#### 3.4.3 How We Engage | การมีส่วนร่วม

**With PDPC**:
- **Proactive**: Stay informed on PDPA updates (attend PDPC workshops, monitor website)
- **Reactive**: Respond to PDPC inquiries (if complaint filed or breach reported)
- **Breach Notification**: Submit via PDPC online portal within 72 hours

**With CB (Certification Body)**:
- **Stage 1 Audit** (document review): CB reviews ISMS documentation remotely
- **Stage 2 Audit** (on-site): CB interviews staff, reviews evidence, tests controls
- **Surveillance Audits** (annual after certification): CB verifies ongoing compliance
- **Recertification Audit** (every 3 years): Full re-assessment

---

### 3.5 Shareholders/Owners 🟠

#### 3.5.1 Who They Are | พวกเขาคือใคร

- Company owners and investors
- Board of Directors (if applicable)

#### 3.5.2 Their Information Security Requirements | ข้อกำหนดด้านความมั่นคงปลอดภัย

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **Protect Company Assets**: Prevent data breaches, service disruptions that damage reputation or finances | - ISMS implementation (ISO 27001:2022)<br>- Cyber insurance coverage | ✅ Implemented |
| **Compliance**: Avoid regulatory penalties (PDPA fines up to 5% revenue) | - PDPA Compliance Policy<br>- DPO oversight | ✅ Implemented |
| **Customer Retention**: Security posture must support customer confidence and retention | - ISO 27001 certification in progress<br>- Security questionnaire responses | 🔄 In Progress |
| **Cost Control**: Security investments must be justified and cost-effective | - Risk-based approach (prioritize high-impact controls)<br>- Quarterly budget reviews | ✅ Implemented |
| **Transparency**: Regular reporting on security posture and incidents | - Quarterly CISO report to CEO/Board<br>- Annual management review | ✅ Implemented |

#### 3.5.3 How We Engage | การมีส่วนร่วม

- **Quarterly Board Meetings**: CISO presents security metrics, incidents, budget
- **Annual Management Review**: CEO reviews ISMS effectiveness
- **Ad-hoc**: Immediate notification of Critical incidents (biometric breach, ransomware)

---

### 3.6 Employees 🟠

#### 3.6.1 Who They Are | พวกเขาคือใคร

- All Certogo employees ([Number] total)
- Departments: Executive, Engineering, IT Ops, Security, Customer Support, Sales, HR, Admin
- Work arrangements: Office, remote (work-from-home), hybrid

#### 3.6.2 Their Information Security Requirements | ข้อกำหนดด้านความมั่นคงปลอดภัย

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **Clear Security Policies**: Employees need to know what is expected | - Information Security Policy (POL-001)<br>- Acceptable Use Policy (to be created)<br>- All employees acknowledge policies | 🔄 In Progress |
| **Security Training**: Employees need training to avoid security mistakes | - Mandatory security awareness training (annual)<br>- Tier 2: PDPA & biometric data handling (for PII access roles) 🔴<br>- Phishing simulations (quarterly) | ✅ Implemented |
| **Secure Tools**: Employees need secure devices and systems to do their job | - Company-issued laptops (encrypted, EDR)<br>- VPN for production access<br>- MFA for all systems | ✅ Implemented |
| **Incident Reporting**: Easy way to report security incidents or concerns | - Incident reporting channels (email, Slack, phone)<br>- No retaliation policy (encourage reporting) | ✅ Implemented |
| **Personal Data Protection**: Employee Personal Data (HR records) protected | - HR data encrypted<br>- Access restricted to HR team<br>- PDPA compliance | ✅ Implemented |
| **Fair Disciplinary Process**: Violations handled consistently | - Disciplinary process in policies (Level 1-4)<br>- Level 4 (termination) for biometric data violations 🔴 | ✅ Implemented |

#### 3.6.3 How We Engage | การมีส่วนร่วม

- **Onboarding**: New hires receive security training, sign policy acknowledgments
- **Annual Training**: All employees complete mandatory security training
- **All-Hands Meetings**: CISO updates on security posture, incidents, reminders
- **Security Champions**: Volunteer employees in each department promote security

---

### 3.7 Cloud Infrastructure Provider 🟡

#### 3.7.1 Who They Are | พวกเขาคือใคร

- Cloud provider: [AWS / Azure / GCP - specify]
- Service: IaaS (Infrastructure as a Service) - compute, storage, networking, databases
- Regions: Thailand (primary), Singapore (DR)

#### 3.7.2 Their Information Security Requirements | ข้อกำหนดด้านความมั่นคงปลอดภัย

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **Shared Responsibility Model**: Cloud provider secures infrastructure; Certogo secures application and data | - Certogo implements application security (OWASP Top 10, secure coding)<br>- Certogo manages encryption keys<br>- Certogo configures IAM (Identity and Access Management) | ✅ Implemented |
| **Compliance with Cloud Provider ToS**: Adhere to terms of service and acceptable use policy | - Legal reviews cloud provider contracts<br>- Prohibited activities avoided (crypto mining, spam) | ✅ Implemented |
| **Timely Payment**: Pay for cloud services | - Billing process established<br>- Auto-pay enabled to avoid service interruption | ✅ Implemented |
| **Responsible Disclosure**: Report vulnerabilities in cloud provider services responsibly | - Bug bounty program participation (if cloud provider has one) | ✅ Implemented |

#### 3.7.3 Certogo's Requirements from Cloud Provider | ข้อกำหนดของ Certogo จากผู้ให้บริการคลาวด์

| Requirement | Cloud Provider's Response | Verification | Status |
|-------------|---------------------------|--------------|--------|
| **ISO 27001 and SOC 2 Certification**: Cloud provider must be certified | - [Provider] is ISO 27001 and SOC 2 Type II certified<br>- Certificates available on website | - Certogo reviews annually | ✅ Verified |
| **99.9% Uptime SLA**: Infrastructure availability guarantee | - [Provider] commits to 99.9% SLA<br>- Service credits for breaches | - Certogo monitors with CloudWatch/Azure Monitor/GCP Monitoring | ✅ Contractual |
| **Data Residency**: Ability to specify data location (Thailand, Singapore) | - [Provider] offers Thailand and Singapore regions | - Certogo configures region restrictions in IaC | ✅ Implemented |
| **Encryption**: Support for encryption at rest and in transit | - [Provider] offers encryption services (KMS, TLS) | - Certogo enables encryption for all data stores | ✅ Implemented |
| **Incident Notification**: Notify customers of security incidents affecting their resources | - [Provider] has incident notification process | - Certogo subscribes to security bulletins | ✅ Contractual |

#### 3.7.4 How We Engage | การมีส่วนร่วม

- **Cloud Management Console**: Daily operations
- **Support Tickets**: Technical issues, billing inquiries
- **Account Manager** (for enterprise accounts): Quarterly business reviews
- **Security Bulletins**: Monitor for vulnerabilities affecting Certogo infrastructure

---

### 3.8 Other Third-Party Suppliers 🟡

#### 3.8.1 Who They Are | พวกเขาคือใคร

- Email service provider (transactional emails, marketing)
- Customer support platform (help desk ticketing)
- Payment gateway (if applicable)
- Security tools (SIEM, EDR, penetration testing firms)

#### 3.8.2 Their Information Security Requirements | ข้อกำหนดด้านความมั่นคงปลอดภัย

| Requirement | Certogo's Response | Status |
|-------------|-------------------|--------|
| **Supplier Security Assessment**: Critical and High-risk suppliers undergo security assessment | - Supplier Security Policy (POL-004)<br>- 100+ question assessment for Critical<br>- 50 questions for High-risk | ✅ Implemented |
| **Data Processing Agreements (DPA)**: Suppliers handling PII sign DPA | - DPA template available (in Supplier Security Policy Appendix A)<br>- DPA signed with all PII-handling suppliers | ✅ Implemented |
| **SLA Commitments**: Service level agreements for availability, performance | - SLAs negotiated during procurement<br>- Monitored by Procurement + CISO | ✅ Implemented |

#### 3.8.3 Certogo's Requirements from Suppliers | ข้อกำหนดของ Certogo จากผู้ให้บริการ

- Security certifications (ISO 27001, SOC 2) preferred for Critical suppliers
- Encryption for data at rest and in transit
- Incident notification within 72 hours (24 hours for Critical suppliers)
- Annual security reviews

#### 3.8.4 How We Engage | การมีส่วนร่วม

- **Procurement Process**: Security assessment before contract signature
- **Annual Reviews**: Procurement + CISO review supplier performance
- **Incident Coordination**: Escalation procedures if supplier has incident

---

### 3.9 Competitors 🟢

#### 3.9.1 Who They Are | พวกเขาคือใคร

- Other LMS providers in Thailand and ASEAN
- EdTech platforms offering similar training solutions

#### 3.9.2 Their Influence on ISMS | อิทธิพลต่อ ISMS

- **Indirect**: Competitors' security posture sets market expectations
- **ISO 27001 Certification**: If competitors are certified, Certogo needs certification to remain competitive
- **Security Incidents**: Public breaches at competitors increase customer scrutiny

#### 3.9.3 How We Respond | การตอบสนอง

- Monitor competitor certifications (ISO 27001, SOC 2)
- Learn from public incidents (not to make same mistakes)
- Differentiate on security (ISO 27001, PDPA compliance, biometric data protection) 🔴

---

### 3.10 Media and Public 🟢

#### 3.10.1 Who They Are | พวกเขาคือใคร

- Media outlets (tech news, business news)
- General public (potential customers, job seekers)

#### 3.10.2 Their Influence on ISMS | อิทธิพลต่อ ISMS

- **Reputational Risk**: Public data breach would damage reputation
- **Transparency Expectations**: Customers expect prompt, honest breach notifications

#### 3.10.3 How We Engage | การมีส่วนร่วม

- **Proactive**: Publish security practices (website, blog)
- **Reactive**: If breach occurs, issue public statement (for major incidents affecting > 10,000 individuals)
- **PR Coordination**: Legal and PR team coordinate messaging

---

## 4. Stakeholder Requirements Summary Matrix | ตารางสรุปข้อกำหนดผู้มีส่วนได้ส่วนเสีย

| Requirement Category | B2B Customers | B2C Users | E-KYC Provider | PDPC | CB | Shareholders | Employees | Cloud Provider |
|---------------------|---------------|-----------|----------------|------|----|--------------|-----------| ---------------|
| **Data Confidentiality** | ✅ High | ✅ High | ✅ Critical 🔴 | ✅ High | ✅ High | ✅ Medium | ✅ Medium | ✅ High |
| **Data Integrity** | ✅ High | ✅ Medium | ✅ Medium | ✅ Medium | ✅ Medium | ✅ Medium | ❌ Low | ✅ Medium |
| **Service Availability** | ✅ Critical 🔴 | ✅ High | ✅ High | ❌ Low | ❌ Low | ✅ High | ✅ Medium | ✅ High |
| **PDPA Compliance** | ✅ High | ✅ Critical 🔴 | ✅ Critical 🔴 | ✅ Critical 🔴 | ✅ High | ✅ High | ✅ Medium | ❌ Low |
| **ISO 27001 Certification** | ✅ High | ❌ Low | ✅ Critical 🔴 | ❌ Low | ✅ Critical 🔴 | ✅ Medium | ❌ Low | ✅ Medium |
| **Incident Notification** | ✅ High (24h) | ✅ High (72h) | ✅ Critical (24h) 🔴 | ✅ Critical (72h) 🔴 | ✅ High | ✅ High | ❌ Low | ✅ Medium |
| **Transparency** | ✅ Medium | ✅ High | ✅ Medium | ✅ High | ✅ High | ✅ High | ✅ High | ❌ Low |

**Legend**:
- ✅ **Applicable** - Stakeholder has this requirement
- ❌ **Not Applicable** - Stakeholder does not have this requirement
- 🔴 **Critical** - Highest priority requirement

---

## 5. Monitoring and Review | การติดตามและทบทวน

### 5.1 Review Schedule | กำหนดการทบทวน

This Interested Parties analysis shall be reviewed:

- **Annually** (by CISO, approved by CEO)
- **Ad-hoc** when significant changes occur:
  - New major customer segment (e.g., enter healthcare sector with stricter requirements)
  - E-KYC provider change 🔴
  - Regulatory changes (PDPA updates, new regulations)
  - Significant incidents (breach affecting stakeholder perception)

### 5.2 Stakeholder Engagement Tracking | การติดตามการมีส่วนร่วมผู้มีส่วนได้ส่วนเสีย

| Stakeholder | Engagement Method | Frequency | Owner |
|-------------|-------------------|-----------|-------|
| B2B Customers | Quarterly Business Reviews | Quarterly | Account Manager |
| B2C Users | Surveys, Support Tickets | Ongoing | Customer Support |
| E-KYC Provider | Security Review Meetings | Quarterly | CISO |
| PDPC | Monitor Updates, Workshops | Quarterly | DPO |
| CB (Certification Body) | Audits | Annual (after cert) | CISO |
| Shareholders | Board Meetings | Quarterly | CEO |
| Employees | All-Hands, Training | Quarterly/Annual | HR + CISO |
| Cloud Provider | Account Reviews | Quarterly | CTO |

### 5.3 Integration with ISMS | การบูรณาการกับ ISMS

Stakeholder requirements inform:
- **Risk Assessment**: Stakeholder expectations drive risk identification (e.g., customer requirement for 99.5% uptime → availability risk)
- **Control Selection**: Annex A controls chosen to meet stakeholder requirements
- **ISMS Objectives**: Objectives aligned with stakeholder needs
- **Management Review**: Stakeholder feedback discussed in annual management review

---

## 6. Approval | การอนุมัติ

**Approved By**:

```
_________________________________________
[CEO Name]
Chief Executive Officer
Certogo Co., Ltd.

Date: _______________
```

**Reviewed By**:

```
_________________________________________
[CISO Name]
Chief Information Security Officer
Certogo Co., Ltd.

Date: _______________
```

---

**END OF DOCUMENT | สิ้นสุดเอกสาร**

**Document Classification**: Internal Use Only
**Version**: 1.0
**Last Updated**: [Date]
**Next Review**: [Date + 1 year]
