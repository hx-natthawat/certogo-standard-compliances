# Information Security Policy | นโยบายความมั่นคงปลอดภัยสารสนเทศ

**Document Control | การควบคุมเอกสาร**

| Field | Value |
|-------|-------|
| **Document ID** | POL-001 |
| **Version** | 1.0 |
| **Effective Date** | [To be filled - วันที่มีผลบังคับใช้] |
| **Review Date** | [Annual - ทบทวนทุกปี] |
| **Document Owner** | Chief Information Security Officer (CISO) |
| **Approved By** | Chief Executive Officer (CEO) |
| **Classification** | Internal Use Only - ใช้ภายในองค์กรเท่านั้น |

---

## 1. Policy Statement | แถลงการณ์นโยบาย

### 1.1 English Version

Certogo Co., Ltd. is committed to protecting the confidentiality, integrity, and availability of all information assets under our control. As a provider of Learning Management System (LMS) services for both compliance and non-compliance training, and as an integrator of third-party E-KYC services, we recognize our responsibility to:

- **Protect customer data**, including Personal Data (PII) and highly sensitive biometric data processed through our E-KYC integration
- **Ensure service availability** to support our B2B and B2C customers' critical training and certification needs
- **Comply with legal and regulatory requirements**, including Thailand's Personal Data Protection Act (PDPA) B.E. 2562 (2019)
- **Maintain customer trust** through transparent and responsible security practices
- **Manage third-party risks**, particularly related to E-KYC service providers

This policy establishes the foundation for Certogo's Information Security Management System (ISMS) in accordance with **ISO/IEC 27001:2022** standards.

### 1.2 Thai Version | ฉบับภาษาไทย

บริษัท Certogo จำกัด มุ่งมั่นในการปกป้องความลับ ความถูกต้องครบถ้วน และความพร้อมใช้งานของสินทรัพย์สารสนเทศทั้งหมดภายใต้การควบคุมของเรา ในฐานะผู้ให้บริการระบบการจัดการการเรียนรู้ (LMS) สำหรับการฝึกอบรมทั้งด้านการปฏิบัติตามกฎระเบียบและที่ไม่ใช่การปฏิบัติตามกฎระเบียบ และในฐานะผู้เชื่อมต่อบริการ E-KYC ของบุคคลที่สาม เรารับทราบความรับผิดชอบของเราในการ:

- **ปกป้องข้อมูลลูกค้า** รวมถึงข้อมูลส่วนบุคคล (PII) และข้อมูลไบโอเมตริกซ์ที่มีความละเอียดอ่อนสูงซึ่งประมวลผลผ่านการเชื่อมต่อ E-KYC ของเรา
- **รับประกันความพร้อมใช้งานของบริการ** เพื่อสนับสนุนความต้องการด้านการฝึกอบรมและการรับรองที่สำคัญของลูกค้า B2B และ B2C
- **ปฏิบัติตามข้อกำหนดทางกฎหมายและกฎระเบียบ** รวมถึงพระราชบัญญัติคุ้มครองข้อมูลส่วนบุคคล พ.ศ. 2562 ของประเทศไทย
- **รักษาความไว้วางใจของลูกค้า** ผ่านการปฏิบัติด้านความปลอดภัยที่โปร่งใสและรับผิดชอบ
- **จัดการความเสี่ยงจากบุคคลที่สาม** โดยเฉพาะที่เกี่ยวข้องกับผู้ให้บริการ E-KYC

นโยบายนี้กำหนดรากฐานสำหรับระบบการจัดการความมั่นคงปลอดภัยสารสนเทศ (ISMS) ของ Certogo ตามมาตรฐาน **ISO/IEC 27001:2022**

---

## 2. Scope | ขอบเขต

### 2.1 In Scope | อยู่ในขอบเขต

This policy applies to:

**Systems and Services | ระบบและบริการ**:
- Certogo LMS Platform (B2B SaaS/PaaS and B2C services)
- Web applications, mobile applications, APIs
- Databases, file storage, backup systems
- **Third-party integrations**, particularly **Appman E-KYC service** (current provider)
- Cloud infrastructure (AWS/Azure/GCP)
- Development, staging, and production environments

**Data Assets | สินทรัพย์ข้อมูล**:
- Customer data (course enrollments, certificates, progress tracking)
- Personal Data (PII): names, email addresses, phone numbers, ID card numbers
- **🔴 CRITICAL: Biometric data** (facial images, ID card scans) - processed by E-KYC provider
- Employee data
- Business confidential information
- Intellectual property (course content, source code)

**People | บุคลากร**:
- All Certogo employees (full-time, part-time, contractors)
- Board of Directors and management
- Third-party service providers with access to Certogo systems
- B2B customers' administrators
- B2C end users

**Locations | สถานที่**:
- Certogo offices in Thailand
- Remote work locations
- Cloud data centers (Thailand region for PDPA compliance)
- **E-KYC provider's facilities** (Appman - subject to contractual controls)

### 2.2 Out of Scope | นอกขอบเขต

- Customer-owned infrastructure (for PaaS deployments where customer manages infrastructure)
- Third-party services not integrated with Certogo platform
- Personal devices not used for work purposes

---

## 3. Information Security Objectives | วัตถุประสงค์ด้านความมั่นคงปลอดภัยสารสนเทศ

Certogo establishes the following information security objectives aligned with ISO 27001:2022:

### 3.1 Confidentiality | ความลับ

**Objective**: Ensure that information is accessible only to authorized individuals

**Specific Goals**:
- **Zero tolerance** for biometric data breaches 🔴
- < 0.1% unauthorized access incidents per year
- 100% of PII encrypted at rest and in transit
- Multi-factor authentication (MFA) for all administrative access
- Role-based access control (RBAC) implementation

**Thai | ไทย**: รับประกันว่าข้อมูลสามารถเข้าถึงได้โดยบุคคลที่ได้รับอนุญาตเท่านั้น

### 3.2 Integrity | ความถูกต้องครบถ้วน

**Objective**: Safeguard the accuracy and completeness of information and processing methods

**Specific Goals**:
- Certificate issuance accuracy: 99.99%
- E-KYC verification result integrity: 100% (no tampering)
- Audit trail completeness: 100% for critical operations
- Version control for all code and documentation

**Thai | ไทย**: ปกป้องความถูกต้องและความครบถ้วนของข้อมูลและวิธีการประมวลผล

### 3.3 Availability | ความพร้อมใช้งาน

**Objective**: Ensure that authorized users have access to information when needed

**Specific Goals**:
- LMS platform uptime: ≥ 99.5% (excluding planned maintenance)
- **E-KYC service availability**: ≥ 99% (measured at integration point) 🔴
- Recovery Time Objective (RTO): < 4 hours for critical services
- Recovery Point Objective (RPO): < 1 hour (maximum data loss)
- Backup success rate: 100%

**Thai | ไทย**: รับประกันว่าผู้ใช้ที่ได้รับอนุญาตสามารถเข้าถึงข้อมูลได้เมื่อต้องการ

### 3.4 Compliance | การปฏิบัติตามกฎระเบียบ

**Objective**: Comply with all applicable legal, regulatory, and contractual requirements

**Specific Goals**:
- **PDPA compliance**: 100% (Thailand Personal Data Protection Act)
- **ISO 27001:2022 compliance**: Achieve certification within 12 months
- Contract fulfillment: 100% of SLA commitments met
- Audit findings: Close all critical and high findings within 30 days

**Thai | ไทย**: ปฏิบัติตามข้อกำหดทางกฎหมาย กฎระเบียบ และสัญญาทั้งหมดที่เกี่ยวข้อง

### 3.5 Third-Party Risk Management | การจัดการความเสี่ยงจากบุคคลที่สาม 🔴

**Objective**: Ensure third-party service providers meet Certogo's security standards

**Specific Goals**:
- 100% of critical suppliers (including E-KYC provider) are ISO 27001 certified
- Quarterly security reviews for E-KYC provider
- Annual penetration test review for E-KYC provider
- **Provider change capability**: Maintain documented migration procedure 🔴
- Supplier incident response time: < 24 hours for critical incidents

**Thai | ไทย**: รับประกันว่าผู้ให้บริการบุคคลที่สามเป็นไปตามมาตรฐานความปลอดภัยของ Certogo

---

## 4. Roles and Responsibilities | บทบาทและความรับผิดชอบ

### 4.1 Chief Executive Officer (CEO) | ประธานเจ้าหน้าที่บริหาร

**Responsibilities**:
- Approve and endorse this Information Security Policy
- Allocate adequate resources for ISMS implementation
- Demonstrate leadership and commitment to information security
- Review ISMS performance at management reviews (minimum annually)
- Approve high-risk treatment decisions

**Accountable for**: Overall ISMS effectiveness and strategic alignment

### 4.2 Chief Information Security Officer (CISO) | หัวหน้าเจ้าหน้าที่ความมั่นคงปลอดภัยสารสนเทศ

**Responsibilities**:
- Own and maintain this policy and supporting ISMS documentation
- Lead risk assessment and treatment activities
- Oversee security incident response
- Manage third-party security assessments (including E-KYC provider) 🔴
- Report ISMS performance to CEO and Board
- Lead internal audits and certification activities
- Approve security exceptions and risk acceptances (within delegated authority)

**Accountable for**: Day-to-day ISMS operation and ISO 27001 compliance

### 4.3 Chief Technology Officer (CTO) | หัวหน้าเจ้าหน้าที่เทคโนโลยี

**Responsibilities**:
- Implement technical security controls (encryption, access control, network security)
- Ensure secure software development lifecycle (SDLC)
- Manage cloud infrastructure security
- Oversee E-KYC API integration security 🔴
- Lead business continuity and disaster recovery planning
- Approve technology architecture changes

**Accountable for**: Technical security implementation and platform availability

### 4.4 Data Protection Officer (DPO) | เจ้าหน้าที่คุ้มครองข้อมูลส่วนบุคคล

**Responsibilities**:
- Ensure PDPA compliance, particularly for biometric data handling 🔴
- Manage data subject rights requests (access, deletion, portability)
- Oversee data retention and deletion procedures
- Review Data Processing Agreements (DPAs) with third parties
- Conduct Data Protection Impact Assessments (DPIAs) for high-risk processing
- Liaise with Personal Data Protection Committee (PDPC) if required

**Accountable for**: PDPA compliance and data privacy

### 4.5 Human Resources (HR) Manager | ผู้จัดการทรัพยากรบุคคล

**Responsibilities**:
- Conduct background screening for new hires (especially for roles with PII access) 🔴
- Deliver security awareness training to all employees
- Manage security training records and acknowledgments
- Enforce disciplinary procedures for policy violations
- Process termination procedures (access revocation)

**Accountable for**: People security controls (ISO 27001 A.6)

### 4.6 Procurement/Vendor Management | ฝ่ายจัดซื้อ/การจัดการผู้จำหน่าย

**Responsibilities**:
- Conduct supplier security assessments (using CISO-approved questionnaire)
- Ensure all supplier contracts include security requirements
- Monitor supplier performance and SLAs
- Coordinate with CISO for critical supplier reviews (e.g., E-KYC provider) 🔴
- Manage supplier offboarding and data return/deletion

**Accountable for**: Supplier security assurance

### 4.7 All Employees | พนักงานทุกคน

**Responsibilities**:
- Read, understand, and comply with this policy and all supporting policies
- Complete mandatory security awareness training (annually)
- Report security incidents immediately (within 1 hour of discovery)
- Protect credentials (passwords, API keys, access tokens)
- **CRITICAL**: Never access, copy, or share biometric data 🔴
- Report suspected policy violations

**Accountable for**: Personal compliance with security policies

### 4.8 Developers and Engineers | นักพัฒนาและวิศวกร

**Responsibilities**:
- Follow secure coding standards
- Conduct code reviews with security focus
- Implement security controls in E-KYC integration (encryption, access control) 🔴
- Never log biometric data or PII in plain text
- Participate in security testing (SAST, DAST, penetration tests)

**Accountable for**: Secure application development

---

## 5. Supporting Policies and Procedures | นโยบายและขั้นตอนสนับสนุน

This Information Security Policy is supported by the following detailed policies and procedures:

### 5.1 Mandatory Supporting Policies | นโยบายสนับสนุนบังคับ

| Policy Name | Document ID | Owner | Status |
|-------------|-------------|-------|--------|
| **Access Control Policy** | POL-002 | CISO | 🔄 In Development |
| **PDPA Compliance Policy** 🔴 | POL-003 | DPO | 🔄 In Development |
| **Supplier Security Policy** 🔴 | POL-004 | CISO | 🔄 In Development |
| **Incident Response Policy** | POL-005 | CISO | 🔄 In Development |
| **Business Continuity Policy** | POL-006 | CTO | 🔄 In Development |
| **Asset Management Policy** | POL-007 | CTO | 🔄 In Development |
| **Cryptography Policy** | POL-008 | CTO | 🔄 In Development |
| **Acceptable Use Policy** | POL-009 | CISO | 🔄 In Development |

### 5.2 Mandatory Procedures | ขั้นตอนบังคับ

| Procedure Name | Document ID | Owner | Priority |
|----------------|-------------|-------|----------|
| **Data Deletion Procedure** 🔴 | PROC-001 | DPO | High |
| **E-KYC Provider Change Procedure** 🔴 | PROC-002 | CISO | High |
| **Incident Response Procedure** | PROC-003 | CISO | High |
| **Backup and Recovery Procedure** | PROC-004 | CTO | High |
| **User Access Provisioning/Deprovisioning** | PROC-005 | IT Manager | Medium |
| **Change Management Procedure** | PROC-006 | CTO | Medium |
| **Vulnerability Management Procedure** | PROC-007 | CISO | Medium |

---

## 6. E-KYC Integration Security Requirements | ข้อกำหนดความปลอดภัยสำหรับการเชื่อมต่อ E-KYC 🔴

Given the critical nature of E-KYC integration involving biometric data, Certogo establishes specific security requirements:

### 6.1 Current E-KYC Provider | ผู้ให้บริการ E-KYC ปัจจุบัน

**Provider**: Appman Co., Ltd.
**Service**: Digital identity verification (ID card OCR + facial recognition + liveness detection)
**Data Processed**: Biometric data (facial images, ID card scans)
**Classification**: Highly Confidential - PDPA Sensitive Data 🔴

### 6.2 Mandatory Security Controls | การควบคุมความปลอดภัยบังคับ

**E-KYC Provider MUST**:

1. **Certification Requirements**:
   - ✅ Hold valid ISO 27001 certification
   - ✅ Demonstrate PDPA compliance
   - ✅ Provide annual certification renewal

2. **Technical Controls**:
   - ✅ Encrypt biometric data at rest (AES-256 minimum)
   - ✅ Encrypt data in transit (TLS 1.3 minimum)
   - ✅ Implement secure API authentication (OAuth 2.0 + JWT)
   - ✅ Maintain audit trails for all biometric data access
   - ✅ Network segmentation and DDoS protection

3. **Data Handling**:
   - ✅ **Data retention**: Maximum 30 days for biometric data 🔴
   - ✅ **Data localization**: Store data in Thailand only
   - ✅ **Purpose limitation**: Use data only for identity verification
   - ✅ **Data deletion**: Provide certificate of deletion upon request
   - ✅ **Sub-processor approval**: Obtain Certogo's written consent before engaging sub-processors

4. **Transparency and Monitoring**:
   - ✅ Provide quarterly security reports
   - ✅ Notify Certogo of security incidents within 24 hours
   - ✅ Allow Certogo to review penetration test results (annually)
   - ✅ Participate in Certogo's security audits (every 2 years)

### 6.3 Certogo's Responsibilities | ความรับผิดชอบของ Certogo

**Certogo MUST**:

1. **Integration Security**:
   - ✅ Secure API key management (never hardcoded, rotated every 90 days)
   - ✅ Implement rate limiting to prevent abuse
   - ✅ Log all E-KYC API calls (excluding biometric data)
   - ✅ Monitor E-KYC service availability and performance

2. **Data Minimization**:
   - ✅ Send only necessary data to E-KYC provider (ID card image, selfie)
   - ✅ Receive only verification result (not raw biometric data)
   - ✅ Never store biometric data on Certogo systems 🔴

3. **Supplier Management**:
   - ✅ Conduct annual security review of E-KYC provider
   - ✅ Maintain valid Data Processing Agreement (DPA)
   - ✅ Monitor SLA compliance (99% availability)
   - ✅ Maintain E-KYC provider change procedure (20-week process) 🔴

### 6.4 Provider Changeability | ความสามารถในการเปลี่ยนผู้ให้บริการ 🔴

**IMPORTANT**: Certogo reserves the right to change E-KYC providers if business or security requirements change.

**Triggers for Provider Change**:
- Loss of ISO 27001 certification
- PDPA violation or data breach
- Repeated SLA failures (availability < 95% for 2 consecutive months)
- Unacceptable cost increases
- Better alternative provider available

**Migration Process**: See **PROC-002: E-KYC Provider Change Procedure** (20-week process)

**Documentation Updates Required Upon Provider Change**:
- ✅ This Information Security Policy (Section 6.1)
- ✅ Statement of Applicability (provider name in critical controls)
- ✅ Risk Assessment (update R-001 to R-012)
- ✅ Data Processing Agreement (new DPA)
- ✅ Supplier contracts and SLAs

---

## 7. Risk Management | การจัดการความเสี่ยง

### 7.1 Risk Assessment | การประเมินความเสี่ยง

Certogo shall:
- Conduct formal risk assessments **at least annually**
- Use ISO 27005:2022 methodology
- Assess likelihood (1-5 scale) and impact (1-5 scale across 6 dimensions)
- Identify risks to confidentiality, integrity, and availability
- **Prioritize E-KYC related risks** (R-001 to R-012) 🔴

**Risk Appetite**:
- **Critical risks** (score 16-25): Zero tolerance - MUST be treated to High or below
- **High risks** (score 10-15): Low tolerance - Treat within 30 days
- **Medium risks** (score 5-9): Moderate tolerance - Treat within 90 days
- **Low risks** (score 1-4): High tolerance - May accept with justification

### 7.2 Risk Treatment | การจัดการความเสี่ยง

For each identified risk, Certogo shall select one of the following treatments:

1. **Mitigate**: Implement controls to reduce likelihood or impact (preferred for High/Critical risks)
2. **Accept**: Document rationale and obtain CEO/CISO approval (only for Low risks)
3. **Transfer**: Use insurance or contractual clauses (e.g., cyber insurance for third-party breaches)
4. **Avoid**: Discontinue the activity causing the risk (last resort)

**Mandatory Treatments for E-KYC Risks** 🔴:
- **R-001 (Biometric data breach at E-KYC provider)**: Mitigate + Transfer (cyber insurance)
- **R-002 (E-KYC service outage)**: Mitigate (monitoring, SLA enforcement)
- **R-011 (E-KYC provider change disruption)**: Mitigate (documented 20-week procedure)
- **R-012 (Biometric data deletion failure)**: Mitigate (verification with certificate)

### 7.3 Risk Review | การทบทวนความเสี่ยง

Risks shall be reviewed:
- **Quarterly**: All Critical and High risks
- **Annually**: All risks (comprehensive review)
- **Ad-hoc**: When significant changes occur (e.g., new E-KYC provider, new service launch, major security incident)

---

## 8. Security Incident Management | การจัดการเหตุการณ์ด้านความปลอดภัย

### 8.1 Incident Reporting | การรายงานเหตุการณ์

**All employees MUST report security incidents immediately**:

**Reporting Timeframe**:
- **Critical incidents** 🔴 (biometric data breach, ransomware, complete system outage): **Within 1 hour**
- **High incidents**: Within 4 hours
- **Medium/Low incidents**: Within 24 hours

**Reporting Channels**:
- Email: security@certogo.com
- Slack: #security-incidents (for urgent matters)
- Phone: [CISO contact number]

**What to Report**:
- Date/time of incident
- Description of what happened
- Systems/data affected
- Potential impact
- Actions already taken

### 8.2 Incident Classification | การจำแนกเหตุการณ์

| Severity | Examples | Response Time |
|----------|----------|---------------|
| **Critical** 🔴 | - Biometric data breach<br>- Ransomware attack<br>- Complete platform outage<br>- E-KYC provider data breach notification | **Immediate** (< 1 hour) |
| **High** 🟠 | - PII data breach (< 100 records)<br>- Successful phishing attack<br>- Unauthorized admin access<br>- E-KYC service outage > 4 hours | **< 4 hours** |
| **Medium** 🟡 | - Malware detected (isolated)<br>- Failed intrusion attempt<br>- Minor data leak (non-PII)<br>- E-KYC service degradation | **< 24 hours** |
| **Low** 🟢 | - Policy violation (isolated)<br>- Suspicious activity (investigated, false alarm) | **< 3 days** |

### 8.3 Third-Party Incident Coordination | การประสานงานเหตุการณ์จากบุคคลที่สาม 🔴

**If E-KYC provider (Appman) notifies Certogo of a security incident**:

1. **Immediate Actions (within 1 hour)**:
   - CISO and DPO alerted
   - Incident logged in ISMS system
   - Assess impact on Certogo customers

2. **Investigation (within 24 hours)**:
   - Request detailed incident report from provider
   - Determine if biometric data was compromised
   - Assess PDPA notification requirements

3. **Customer Notification (if required by PDPA)**:
   - If biometric data breach: Notify affected users within 72 hours
   - Provide clear explanation and remediation steps

4. **Post-Incident Review (within 7 days)**:
   - Evaluate provider's response effectiveness
   - Determine if provider change is required
   - Update risk assessment

---

## 9. Compliance and Audit | การปฏิบัติตามและการตรวจสอบ

### 9.1 Internal Audits | การตรวจสอบภายใน

Certogo shall conduct:
- **Annual comprehensive ISMS audit** covering all ISO 27001 clauses and Annex A controls
- **Quarterly focused audits** on high-risk areas (E-KYC integration, access control, data protection)

**Audit Requirements**:
- Conducted by independent auditors (not responsible for audited area)
- Follow ISO 19011:2018 guidelines
- Document findings and corrective action plans
- Track closure of findings (Critical: 7 days, High: 30 days, Medium: 90 days)

### 9.2 External Audits | การตรวจสอบภายนอก

Certogo shall undergo:
- **ISO 27001 Certification Audit** (Stage 1 + Stage 2)
- **ISO 27001 Surveillance Audits** (annually after certification)
- **ISO 27001 Recertification Audit** (every 3 years)

**Audit Preparation**:
- See **Audit Preparation Checklist** (153 items)
- Ensure all evidence is collected and organized
- Conduct pre-audit readiness review

### 9.3 Management Review | การทบทวนโดยฝ่ายบริหาร

**Frequency**: At least annually (or more frequently if significant changes occur)

**Participants**: CEO, CISO, CTO, DPO, CFO, HR Manager

**Agenda**:
1. Review of previous management review actions
2. Changes in internal/external issues affecting ISMS
3. Feedback on information security performance (KPIs, objectives)
4. Results of risk assessments
5. Status of corrective actions from audits
6. Opportunities for continual improvement
7. Resource needs

**Output**: Management review minutes documenting decisions and action items

---

## 10. Training and Awareness | การฝึกอบรมและการสร้างการรับรู้

### 10.1 Mandatory Training | การฝึกอบรมบังคับ

All employees must complete:

**Tier 1: General Security Awareness** (All employees)
- **Duration**: 1 hour
- **Frequency**: Annually + upon hire
- **Topics**: Password hygiene, phishing, physical security, incident reporting

**Tier 2: PDPA & Biometric Data Handling** 🔴 (Roles with PII access)
- **Duration**: 2 hours
- **Frequency**: Annually + upon hire
- **Mandatory for**: Developers, DevOps, Security Team, Customer Support, HR
- **Topics**: PDPA requirements, biometric data sensitivity, E-KYC data flow, data retention/deletion

**Tier 3: Secure Coding** (Developers only)
- **Duration**: 4 hours
- **Frequency**: Annually
- **Topics**: OWASP Top 10, secure API development, E-KYC integration security

### 10.2 Training Records | บันทึกการฝึกอบรม

HR shall maintain:
- Training completion records (who, what, when)
- Quiz/assessment results (minimum 80% pass rate)
- Policy acknowledgment forms (signed by all employees)

**Retention**: Training records kept for 3 years

---

## 11. Policy Enforcement | การบังคับใช้นโยบาย

### 11.1 Policy Violations | การละเมิดนโยบาย

Violations of this policy or supporting policies will result in disciplinary action:

| Severity | Examples | Consequence |
|----------|----------|-------------|
| **Level 1: Minor** | First-time accidental policy violation (e.g., weak password) | Written warning + retraining |
| **Level 2: Moderate** | Repeated policy violations, negligence (e.g., leaving workstation unlocked) | Formal reprimand + performance review |
| **Level 3: Serious** | Intentional policy violation (e.g., sharing credentials) | Suspension + final warning |
| **Level 4: Critical** 🔴 | **Unauthorized access to biometric data**, intentional data leak, sabotage | **Termination + legal action** |

### 11.2 Exceptions | ข้อยกเว้น

In rare cases, exceptions to policy requirements may be granted:

**Process**:
1. Requester submits exception request to CISO (with business justification)
2. CISO evaluates risk and approves/denies (within 5 business days)
3. If approved: Document exception, compensating controls, and expiration date
4. Exceptions reviewed quarterly

**Prohibited Exceptions** 🔴:
- No exceptions allowed for biometric data protection requirements
- No exceptions allowed for PDPA compliance requirements
- No exceptions allowed for ISO 27001 mandatory clauses

---

## 12. Policy Review and Updates | การทบทวนและปรับปรุงนโยบาย

### 12.1 Review Schedule | กำหนดการทบทวน

This policy shall be reviewed:
- **Annually** (by CISO, approved by CEO)
- **Ad-hoc** when significant changes occur:
  - E-KYC provider change 🔴
  - New legal/regulatory requirements (e.g., PDPA updates)
  - Major security incident
  - Significant business changes (new services, mergers)
  - Audit findings requiring policy updates

### 12.2 Version Control | การควบคุมเวอร์ชัน

| Version | Date | Author | Changes | Approved By |
|---------|------|--------|---------|-------------|
| 1.0 | [Date] | CISO | Initial version | CEO |
| | | | | |

**Change History**: Maintained in `/evidence/policies/information-security-policy-changelog.md`

---

## 13. References | เอกสารอ้างอิง

### 13.1 Standards and Regulations | มาตรฐานและกฎระเบียบ

- **ISO/IEC 27001:2022** - Information Security Management Systems - Requirements
- **ISO/IEC 27002:2022** - Information Security Controls
- **ISO/IEC 27005:2022** - Information Security Risk Management
- **Thailand Personal Data Protection Act B.E. 2562 (2019)** - PDPA
- **ISO 19011:2018** - Guidelines for Auditing Management Systems

### 13.2 Related Certogo Documents | เอกสารที่เกี่ยวข้องของ Certogo

- Statement of Applicability (SoA) - `/standards/iso27001/annex-a-controls/statement-of-applicability.md`
- Risk Assessment Template - `/standards/iso27001/templates/risk-assessment-template.md`
- Audit Preparation Checklist - `/standards/iso27001/templates/audit-preparation-checklist.md`
- A.5 Organizational Controls - `/standards/iso27001/annex-a-controls/A.5-organizational-controls.md`
- A.6 People Controls - `/standards/iso27001/annex-a-controls/A.6-people-controls.md`
- E-KYC Provider Change Procedure (PROC-002) - To be created

---

## 14. Approval and Acknowledgment | การอนุมัติและการรับทราบ

### 14.1 Executive Approval | การอนุมัติโดยผู้บริหาร

This policy has been reviewed and approved by:

**CEO Signature** | **ลายเซ็น CEO**:

```
_________________________________________
[CEO Name]
Chief Executive Officer
Certogo Co., Ltd.

Date: _______________
```

### 14.2 CISO Endorsement | การรับรองโดย CISO

**CISO Signature** | **ลายเซ็น CISO**:

```
_________________________________________
[CISO Name]
Chief Information Security Officer
Certogo Co., Ltd.

Date: _______________
```

### 14.3 Employee Acknowledgment | การรับทราบของพนักงาน

**I acknowledge that I have read, understood, and agree to comply with this Information Security Policy.**

**ข้าพเจ้ารับทราบว่าได้อ่าน เข้าใจ และตกลงที่จะปฏิบัติตามนโยบายความมั่นคงปลอดภัยสารสนเทศนี้**

```
Employee Name (Print): _________________________________

Employee Signature: ____________________________________

Date: _______________
```

**Note**: All employees must sign this acknowledgment within 7 days of policy issuance or upon hire.

---

## Appendix A: Glossary | ภาคผนวก A: อภิธานศัพท์

| Term | Definition (English) | คำจำกัดความ (ไทย) |
|------|---------------------|-------------------|
| **Biometric Data** | Personal data resulting from specific technical processing relating to physical, physiological, or behavioral characteristics (e.g., facial images, fingerprints) | ข้อมูลส่วนบุคคลที่ได้จากการประมวลผลทางเทคนิคเฉพาะที่เกี่ยวกับลักษณะทางกายภาพ สรีรวิทยา หรือพฤติกรรม (เช่น ภาพใบหน้า ลายนิ้วมือ) |
| **E-KYC** | Electronic Know Your Customer - Digital identity verification process | การยืนยันตัวตนทางดิจิทัล |
| **ISMS** | Information Security Management System - Systematic approach to managing sensitive information (ISO 27001) | ระบบการจัดการความมั่นคงปลอดภัยสารสนเทศ |
| **PDPA** | Personal Data Protection Act B.E. 2562 (2019) - Thailand's data privacy law | พระราชบัญญัติคุ้มครองข้อมูลส่วนบุคคล พ.ศ. 2562 |
| **PII** | Personally Identifiable Information - Data that can identify an individual | ข้อมูลส่วนบุคคลที่สามารถระบุตัวบุคคลได้ |
| **DPA** | Data Processing Agreement - Contract between data controller and processor | สัญญาการประมวลผลข้อมูล |
| **SLA** | Service Level Agreement - Contract defining service expectations | ข้อตกลงระดับบริการ |

---

## Appendix B: Contact Information | ภาคผนวก B: ข้อมูลการติดต่อ

**Security Incident Reporting**:
- Email: security@certogo.com
- Phone: [CISO Phone Number]
- Slack: #security-incidents

**PDPA/Privacy Inquiries**:
- Email: privacy@certogo.com
- DPO Phone: [DPO Phone Number]

**General ISMS Questions**:
- Email: isms@certogo.com
- CISO Office: [Office Location]

---

**END OF POLICY | สิ้นสุดนโยบาย**

**Document Classification**: Internal Use Only - ใช้ภายในองค์กรเท่านั้น
**Version**: 1.0
**Last Updated**: [Date]
