# A.6 People Controls | มาตรการควบคุมด้านบุคลากร
# ISO 27001:2022 Implementation Guide for Certogo

## Document Information | ข้อมูลเอกสาร

**Organization** | **องค์กร**: Certogo Co., Ltd.
**Scope** | **ขอบเขต**: Certogo LMS Platform + Appman E-KYC Integration
**Standard** | **มาตรฐาน**: ISO/IEC 27001:2022
**Version** | **เวอร์ชัน**: 1.0
**Date** | **วันที่**: 2025-01-20
**Status** | **สถานะ**: Initial Draft | ร่างเอกสารเบื้องต้น

---

## Overview | ภาพรวม

**A.6 People Controls** focus on managing information security risks related to employees, contractors, and other personnel who have access to Certogo's systems and data, including **sensitive biometric data from E-KYC integration**.

**มาตรการควบคุมด้านบุคลากร A.6** มุ่งเน้นไปที่การจัดการความเสี่ยงด้านความมั่นคงปลอดภัยสารสนเทศที่เกี่ยวข้องกับพนักงาน ผู้รับเหมา และบุคลากรอื่นๆ ที่สามารถเข้าถึงระบบและข้อมูลของ Certogo รวมถึง **ข้อมูลชีวมิติที่ละเอียดอ่อนจากการเชื่อมต่อ E-KYC**

---

## Table of Contents | สารบัญ

1. [A.6.1 Screening](#a61-screening)
2. [A.6.2 Terms and Conditions of Employment](#a62-terms-and-conditions-of-employment)
3. [A.6.3 Information Security Awareness, Education and Training](#a63-information-security-awareness-education-and-training)
4. [A.6.4 Disciplinary Process](#a64-disciplinary-process)
5. [A.6.5 Responsibilities after Termination or Change of Employment](#a65-responsibilities-after-termination-or-change-of-employment)
6. [A.6.6 Confidentiality or Non-Disclosure Agreements](#a66-confidentiality-or-non-disclosure-agreements)
7. [A.6.7 Remote Working](#a67-remote-working)
8. [A.6.8 Information Security Event Reporting](#a68-information-security-event-reporting)

---

## A.6.1 Screening
## การตรวจสอบประวัติ

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้**

### Control Objective | วัตถุประสงค์
To ensure that employees and contractors understand their responsibilities and are suitable for the roles for which they are considered.

เพื่อให้แน่ใจว่าพนักงานและผู้รับเหมาเข้าใจความรับผิดชอบของตนและเหมาะสมสำหรับบทบาทที่พวกเขาได้รับการพิจารณา

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Screening Requirements by Role | ข้อกำหนดการตรวจสอบตามบทบาท

| Role Type | Background Check Level | Justification |
|-----------|------------------------|---------------|
| **Developers with DB Access** 🔴 | **Level 3 (Highest)** | Access to production database containing PII and E-KYC verification results |
| **DevOps/Infrastructure Team** 🔴 | **Level 3 (Highest)** | Root access to servers, potential access to biometric data logs |
| **Security Team** 🔴 | **Level 3 (Highest)** | Access to security logs, incident data, E-KYC API logs |
| **Customer Support (with PII access)** | **Level 2 (Medium)** | Access to customer personal data for support |
| **Developers (no DB access)** | **Level 2 (Medium)** | Access to source code, may handle test data |
| **Marketing, Sales** | **Level 1 (Basic)** | No access to production systems or customer data |

#### 2. Background Check Levels | ระดับการตรวจสอบประวัติ

**Level 1 - Basic Screening** | **ระดับ 1 - การตรวจสอบพื้นฐาน**:
- Identity verification (government ID)
- Education verification (degree, certificates)
- Employment history verification (last 2 positions)
- Reference checks (2 professional references)

**Level 2 - Medium Screening** | **ระดับ 2 - การตรวจสอบปานกลาง**:
- All Level 1 checks
- Criminal background check (national database)
- Credit check (for financial roles)
- Employment gap explanation

**Level 3 - Highest Screening** 🔴 | **ระดับ 3 - การตรวจสอบสูงสุด**:
- All Level 2 checks
- **Enhanced criminal background check** (international if applicable)
- **Drug screening** (optional but recommended for sensitive roles)
- **Personal interview with security team** (discuss security responsibilities)
- **PDPA training completion** before granting access to biometric data

#### 3. Screening Procedure | ขั้นตอนการตรวจสอบ

**Step 1**: Conditional Job Offer
- Extend conditional offer pending background check completion
- Obtain candidate's written consent for background check

**Step 2**: Background Check
- Use third-party screening agency (e.g., [VENDOR NAME])
- Typical timeline: 7-14 days
- Cost: ฿2,000 (Level 1), ฿5,000 (Level 2), ฿10,000 (Level 3)

**Step 3**: Review Results
- HR reviews background check report
- **Red flags**:
  - Criminal convictions (especially fraud, theft, hacking)
  - Falsified education or employment history
  - Unexplained employment gaps
- **Action**: If red flags, consult with CISO and legal team before proceeding

**Step 4**: Approval and Onboarding
- If background check clears: Finalize job offer
- If concerns: Discuss with candidate, may withdraw offer

**Step 5**: Documented Results
- Store background check results securely
- Retention: As long as employment + 7 years (per Thai labor law)
- Access: HR only (strictly confidential)

#### 4. Contractors and Third-Party Personnel | ผู้รับเหมาและบุคลากรจากบุคคลที่สาม

**Appman E-KYC Provider Personnel** 🔴:
- Appman is responsible for screening their own employees
- Certogo verifies in contract: Appman must conduct background checks for personnel handling biometric data
- Annual audit: Request confirmation from Appman that background checks are current

**Other Contractors** (e.g., consultants, auditors):
- Level 2 screening required if accessing production systems
- NDA signed before access granted
- Access limited to minimum necessary (principle of least privilege)

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/procedures/background-check-procedure.pdf` - Screening procedure
- `/evidence/records/hr-records/background-check-summary.xlsx` - Summary (anonymized for privacy)
- `/evidence/contracts/background-check-vendor-agreement.pdf` - Third-party screening vendor contract

**Note**: Actual background check reports are stored in HR system (not in ISMS documentation due to privacy).

---

## A.6.2 Terms and Conditions of Employment
## ข้อกำหนดและเงื่อนไขการจ้างงาน

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้**

### Control Objective | วัตถุประสงค์
To ensure that employees and contractors are aware of and fulfill their information security responsibilities.

เพื่อให้แน่ใจว่าพนักงานและผู้รับเหมาตระหนักและปฏิบัติตามความรับผิดชอบด้านความมั่นคงปลอดภัยสารสนเทศของตน

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Employment Contract Security Clauses | ข้อกำหนดด้านความปลอดภัยในสัญญาจ้างงาน

All employment contracts include the following security-related clauses:

**Clause 1**: **Confidentiality Obligation** | **ข้อผูกพันด้านความลับ**
```
Employee agrees to maintain confidentiality of all Certogo information,
including but not limited to:
- Customer personal data (PII)
- Biometric data processed through E-KYC integration
- Training content and certification data
- Source code, algorithms, and trade secrets
- Business strategies and financial information

Confidentiality obligation continues beyond termination of employment.
```

**Clause 2**: **Acceptable Use** | **การใช้งานที่ยอมรับได้**
```
Employee agrees to use Certogo systems and data only for authorized
business purposes. Prohibited activities include:
- Unauthorized access to customer data or biometric data
- Sharing login credentials
- Installing unauthorized software
- Accessing systems for personal use beyond reasonable limits
- Downloading company data to personal devices without approval
```

**Clause 3**: **Data Protection (PDPA)** 🔴 | **การคุ้มครองข้อมูล**
```
Employee acknowledges that Certogo processes sensitive personal data,
including biometric data (facial images, ID card scans) through our
E-KYC service provider.

Employee agrees to:
- Complete PDPA training within 30 days of hire
- Handle personal data only as authorized and necessary for job duties
- Report any suspected data breach or unauthorized access immediately
- Not retain customer data after employment termination
```

**Clause 4**: **Security Incident Reporting** | **การรายงานเหตุการณ์ด้านความปลอดภัย**
```
Employee must immediately report any security incidents, including:
- Lost or stolen devices (laptop, phone, badge)
- Suspected phishing emails or malware
- Unauthorized access attempts
- Data breaches or leaks
- Violations of security policy by colleagues
```

**Clause 5**: **Return of Assets** | **การคืนทรัพย์สิน**
```
Upon termination, employee must return all company assets:
- Laptop, phone, badge, keys
- Access cards
- Company data (delete from personal devices)
- Documents (physical and electronic)

Failure to return may result in withholding final paycheck.
```

**Clause 6**: **Consequences of Violation** | **ผลที่ตามมาจากการละเมิด**
```
Violation of information security policies may result in:
- Disciplinary action (warning, suspension, termination)
- Legal action (civil or criminal prosecution)
- Financial liability for damages caused

Examples of serious violations:
- Unauthorized disclosure of customer biometric data
- Intentional data breach or sabotage
- Selling customer data to third parties
```

#### 2. Contractor Agreements | สัญญาผู้รับเหมา

**Contractors** (e.g., freelance developers, consultants) sign similar agreements with additional clauses:

**Clause**: **No Data Retention After Contract** 🔴
```
Contractor must not retain any Certogo data (including test data,
customer data, or source code) after contract termination.

All data must be securely deleted and deletion certificate provided.
```

**Clause**: **Sub-Contractor Prohibition** 🔴
```
Contractor may not sub-contract work to third parties without
Certogo's written approval.

If sub-contractors are used, they must sign identical security agreements.
```

#### 3. Acknowledgment Process | กระบวนการรับทราบ

**During Onboarding**:
1. HR provides employment contract with security clauses highlighted
2. Employee reads and signs contract
3. Employee signs **Information Security Acknowledgment Form**:
   - "I have read and understood the Information Security Policy"
   - "I agree to comply with security policies and procedures"
   - "I understand the consequences of policy violations"
4. Signature stored in HR system
5. Copy provided to CISO for ISMS records

**Annual Re-Acknowledgment**:
- Every January, all employees re-sign security acknowledgment
- Ensures awareness of policy updates
- Tracked in HR system

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/templates/employment-contract-template.pdf` - Contract template with security clauses
- `/evidence/templates/contractor-agreement-template.pdf` - Contractor agreement template
- `/evidence/records/hr-records/security-acknowledgment-log.xlsx` - Tracking of signed acknowledgments
- `/evidence/forms/information-security-acknowledgment-form.pdf` - Acknowledgment form template

---

## A.6.3 Information Security Awareness, Education and Training
## ความตระหนักรู้ การศึกษา และการฝึกอบรมด้านความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้** 🔴 **CRITICAL FOR E-KYC DATA HANDLING**

### Control Objective | วัตถุประสงค์
To ensure that employees and contractors receive appropriate information security awareness, education and training.

เพื่อให้แน่ใจว่าพนักงานและผู้รับเหมาได้รับความตระหนักรู้ การศึกษา และการฝึกอบรมด้านความมั่นคงปลอดภัยสารสนเทศที่เหมาะสม

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Security Training Program | โปรแกรมการฝึกอบรมด้านความปลอดภัย

**Three-Tier Training Approach** | **แนวทางการฝึกอบรมสามระดับ**:

##### Tier 1: General Security Awareness (All Employees) | ความตระหนักรู้ด้านความปลอดภัยทั่วไป (พนักงานทุกคน)

**Frequency**: Annual (every January)
**Duration**: 1 hour
**Format**: Online course + quiz (80% passing score required)
**Language**: Thai (with English subtitles)

**Topics Covered** | **หัวข้อที่ครอบคลุม**:
1. Information Security Policy overview
2. Password best practices (strong passwords, MFA)
3. Phishing and social engineering (how to recognize and report)
4. Physical security (badge usage, tailgating prevention, clean desk)
5. Acceptable use of company systems
6. Incident reporting (how and when to report)
7. **PDPA basics** (what is personal data, employee obligations)
8. Remote work security (VPN, Wi-Fi security)
9. **Consequences of security violations**

**Completion Tracking**:
- LMS (Learning Management System) tracks completion
- HR sends reminders to non-completers
- Deadline: January 31st each year
- Non-completion = performance issue

---

##### Tier 2: PDPA & Biometric Data Handling (Roles with PII Access) 🔴

**Frequency**: Annual + upon hire
**Duration**: 2 hours
**Format**: Instructor-led (virtual or in-person) + online module
**Language**: Thai (with English materials)
**Mandatory for**: Developers, DevOps, Security Team, Customer Support, HR

**Topics Covered** 🔴:
1. **PDPA Overview**:
   - What is PDPA? (Thailand's Personal Data Protection Act)
   - Data controller vs. data processor
   - Lawful basis for processing (consent, contract, legal obligation)
   - Data subject rights (access, deletion, portability)

2. **Certogo's Data Classification**:
   - Public, Internal, Confidential, **Highly Confidential** (biometric data)
   - How to identify each classification
   - Handling requirements for each

3. **Biometric Data Handling** 🔴 **CRITICAL**:
   - What is biometric data? (facial images, fingerprints, ID card scans)
   - Why is it highly sensitive? (PDPA Section 26 - sensitive personal data)
   - **Certogo's E-KYC process**:
     - Customer uploads ID card and selfie
     - Appman processes and verifies
     - Certogo receives only verification result (not raw biometric data)
   - **Employee responsibilities**:
     - Never access biometric data directly (stored at Appman)
     - If you see biometric data in logs, report immediately (should not happen)
     - Do not screenshot or copy biometric data
   - **Data retention**: Biometric data deleted after 30 days (Appman's responsibility)

4. **Data Breach Response**:
   - What constitutes a data breach?
   - Immediate action: Report to CISO within 1 hour
   - PDPA requirement: Notify authorities within 72 hours (for serious breaches)
   - Potential consequences: Fines up to 5% of revenue

5. **Real-World Scenarios** (Case Studies):
   - Scenario 1: Employee receives email asking for customer list → **Phishing, report immediately**
   - Scenario 2: Customer requests deletion of their biometric data → **Forward to DPO, coordinate with Appman**
   - Scenario 3: Developer notices biometric data in production logs → **Report to CISO immediately (data minimization violation)**

**Assessment**:
- Quiz at end (90% passing score required for roles with biometric data access)
- Re-take if failed (with additional coaching)

**Certificate**:
- Upon completion, certificate issued (valid 1 year)
- Certificate required before granting production access

---

##### Tier 3: Secure Coding & DevSecOps (Developers, DevOps) | การเขียนโค้ดที่ปลอดภัย

**Frequency**: Annual + upon hire
**Duration**: 4 hours
**Format**: Hands-on workshop + online labs
**Mandatory for**: Developers, DevOps Engineers

**Topics Covered**:
1. **OWASP Top 10**:
   - SQL Injection, XSS, CSRF, etc.
   - How to prevent in code
   - Code examples (Node.js, Python, React)

2. **Secure API Development**:
   - **E-KYC API Security** 🔴:
     - OAuth 2.0 + JWT authentication
     - TLS 1.3 encryption
     - Rate limiting
     - API key rotation
   - Input validation and sanitization
   - Error handling (don't leak sensitive info in errors)

3. **Data Protection in Code**:
   - Encryption at rest and in transit
   - Never log sensitive data (passwords, API keys, 🔴 biometric data)
   - Use environment variables for secrets (not hardcoded)

4. **Dependency Management**:
   - Check for vulnerabilities in npm/pip packages
   - Use tools: npm audit, Snyk, Dependabot

5. **Code Review for Security**:
   - Security checklist for reviewers
   - How to spot security issues

**Hands-On Labs**:
- Lab 1: Exploit SQL injection in test app, then fix it
- Lab 2: Implement OAuth 2.0 authentication
- Lab 3: Secure API key management

**Assessment**:
- Practical exam: Fix security vulnerabilities in sample code

---

#### 2. Ongoing Awareness Campaigns | แคมเปญความตระหนักรู้อย่างต่อเนื่อง

**Monthly Security Tips** (Email + Slack):
- Short tips (2-3 paragraphs) sent every month
- Topics:
  - January: Password hygiene
  - February: Phishing awareness (with simulated phishing test)
  - March: 🔴 **Biometric data protection** (PDPA anniversary month)
  - April: Physical security
  - May: Secure remote work
  - June: Social engineering
  - July: Insider threat awareness
  - August: Incident reporting
  - September: Vendor security (E-KYC provider review)
  - October: Mobile device security
  - November: Cloud security
  - December: Year-end security review

**Quarterly Security Webinars** (Optional Attendance):
- Guest speakers (external experts)
- Recent security incidents in the industry
- New threats and defenses
- Q&A session

**Simulated Phishing Tests** (Quarterly):
- Send simulated phishing emails to employees
- Track click rate
- If clicked: Immediate training module (15 minutes)
- Goal: < 5% click rate

---

#### 3. Role-Specific Training | การฝึกอบรมเฉพาะบทบาท

| Role | Additional Training Required |
|------|------------------------------|
| **Security Team** | Advanced security courses (SANS, CISSP prep, CEH) |
| **DPO** | PDPA certification, privacy law training |
| **CISO** | Leadership, risk management, compliance frameworks |
| **Developers** | Secure coding certification (e.g., OWASP) |
| **DevOps** | Cloud security (AWS Security Specialty, Azure Security) |
| **Customer Support** | PDPA basics, social engineering awareness |

**Budget**: ฿50,000 - ฿100,000 per year for external training and certifications

---

#### 4. New Hire Onboarding | การปฐมนิเทศพนักงานใหม่

**Security Onboarding Checklist** (Completed within first 30 days):

- [ ] **Day 1**: Security orientation (1 hour)
  - Introduction to InfoSec team
  - Overview of security policies
  - Badge and access card issuance
  - Sign security acknowledgment form

- [ ] **Week 1**: General security awareness training (online, 1 hour)

- [ ] **Week 2**: PDPA & Biometric Data Handling training (if applicable, 2 hours) 🔴

- [ ] **Week 3**: Secure coding training (if developer/DevOps, 4 hours)

- [ ] **Week 4**: Shadow a senior employee to see security practices in action

**No production access granted until all training completed.** 🔴

---

#### 5. Training Tracking and Reporting | การติดตามและรายงานการฝึกอบรม

**Training Records** maintained in:
- LMS (Learning Management System) for online courses
- HR system for instructor-led training
- Excel tracker: `/evidence/records/training-records.xlsx`

**Monthly Report** (sent to CISO):
- Completion rate by department
- Overdue trainings
- Quiz pass/fail rate
- Simulated phishing click rate

**Annual Report** (for Management Review):
- Overall training completion: Target 100%
- Certifications earned
- Training budget spent vs. allocated
- Recommendations for next year

---

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/policies/security-awareness-program.pdf` - Training program description
- `/evidence/records/training-records.xlsx` - Training completion tracker
- `/evidence/training-materials/general-security-awareness.pdf` - Training slides
- `/evidence/training-materials/pdpa-biometric-data-handling.pdf` - PDPA training slides 🔴
- `/evidence/training-materials/secure-coding-workshop.pdf` - Developer training materials
- `/evidence/records/training-attendance-sheets/` - Sign-in sheets for instructor-led sessions
- `/evidence/records/training-certificates/` - Completion certificates (samples)

---

## A.6.4 Disciplinary Process
## กระบวนการลงโทษทางวินัย

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้**

### Control Objective | วัตถุประสงค์
To ensure that there is a formal disciplinary process for employees who have committed an information security breach.

เพื่อให้แน่ใจว่ามีกระบวนการลงโทษทางวินัยอย่างเป็นทางการสำหรับพนักงานที่ละเมิดความมั่นคงปลอดภัยสารสนเทศ

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Security Violation Severity Levels | ระดับความรุนแรงของการละเมิดความปลอดภัย

| Severity | Examples | Typical Consequence |
|----------|----------|---------------------|
| **Level 1: Minor** | - Forgot to lock screen when leaving desk<br>- Used weak password<br>- Lost non-sensitive documents | **Verbal Warning** + Remedial training |
| **Level 2: Moderate** | - Shared login credentials with colleague<br>- Clicked phishing link (no data compromise)<br>- Installed unauthorized software | **Written Warning** + Mandatory security training |
| **Level 3: Serious** | - Unauthorized access to customer PII<br>- Took customer data home without approval<br>- Repeatedly violated security policies | **Suspension** (1-3 days) + Corrective action plan |
| **Level 4: Critical** 🔴 | - **Unauthorized access to biometric data**<br>- Intentional data leak or sabotage<br>- Selling customer data to third parties<br>- Hacking or unauthorized system access | **Termination** + Legal action (civil/criminal) |

---

#### 2. Disciplinary Procedure | ขั้นตอนการลงโทษทางวินัย

**Step 1**: **Incident Discovery and Reporting**
- Security incident discovered (via SIEM alert, audit log, manager report, etc.)
- Incident reported to CISO
- Initial assessment: Is it a security policy violation?

**Step 2**: **Investigation**
- CISO (or delegate) investigates
- Collect evidence:
  - Log files (access logs, SIEM alerts)
  - Screenshots
  - Witness statements
  - Device forensics (if needed)
- Interview employee (with HR present)
- **Employee has right to explain** their actions

**Step 3**: **Severity Determination**
- CISO + HR determine severity level (1-4)
- Consider:
  - Intent (accidental vs. malicious)
  - Impact (was data compromised?)
  - Repetition (first offense vs. repeat)

**Step 4**: **Disciplinary Action**
- Apply consequence per severity level
- Document in employee file
- **For Level 3 & 4**: CEO approval required

**Step 5**: **Communication to Employee**
- HR communicates decision in writing
- Specify:
  - What policy was violated
  - Evidence
  - Consequence
  - Corrective actions required (e.g., training)
  - Right to appeal (within 7 days)

**Step 6**: **Appeal Process** (if employee disagrees)
- Employee can submit written appeal to HR Director
- HR Director + independent party (e.g., external lawyer) review
- Decision within 14 days
- Final decision is binding

**Step 7**: **Follow-Up**
- Monitor employee to ensure no repeat
- If termination: Exit procedures (see A.6.5)

---

#### 3. Special Considerations for Biometric Data Violations 🔴

**CRITICAL VIOLATIONS** involving biometric data:

**Scenario 1**: Employee accesses biometric data without authorization
- **Severity**: Level 4 (Critical)
- **Immediate Action**:
  - Suspend access to all systems immediately
  - Notify DPO and legal team
  - **PDPA notification**: Assess if data breach notification required (to authorities and data subjects)
  - Forensic investigation to determine scope
- **Consequence**: Termination + possible legal action

**Scenario 2**: Employee leaks biometric data to unauthorized party
- **Severity**: Level 4 (Critical)
- **Immediate Action**:
  - All of Scenario 1 above
  - **Plus**: Report to Thai PDPC (Personal Data Protection Commission) within 72 hours
  - Notify affected customers
  - Engage legal counsel for potential criminal charges
- **Consequence**: Termination + **criminal prosecution** (PDPA Section 41 - up to 6 months imprisonment)

**Scenario 3**: Developer inadvertently logs biometric data (data minimization violation)
- **Severity**: Level 2 or 3 (depending on intent and scope)
- **Immediate Action**:
  - Purge logs containing biometric data
  - Fix code to prevent future logging
  - Conduct code review
- **Consequence**: Written warning (if unintentional, first offense) OR Suspension (if negligent)

---

#### 4. Documentation and Records | เอกสารและบันทึก

**For Each Disciplinary Case**:
- Case number (e.g., `DISC-2025-001`)
- Date of incident
- Employee name and role
- Description of violation
- Evidence collected
- Investigation findings
- Severity level
- Disciplinary action taken
- Employee's response (if any)
- Outcome and follow-up

**Retention**: 7 years after employment termination (per Thai labor law)
**Access**: HR and CISO only (confidential)

---

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/procedures/disciplinary-procedure.pdf` - Formal disciplinary procedure
- `/evidence/records/hr-records/disciplinary-log.xlsx` - Summary log (anonymized for audit)
- `/evidence/forms/disciplinary-action-form-template.pdf` - Template for documenting actions

**Note**: Actual disciplinary case files stored in HR system (not ISMS documentation due to privacy).

---

## A.6.5 Responsibilities after Termination or Change of Employment
## ความรับผิดชอบหลังจากการสิ้นสุดหรือการเปลี่ยนแปลงการจ้างงาน

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้** 🔴 **CRITICAL FOR DATA ACCESS**

### Control Objective | วัตถุประสงค์
To ensure that information security responsibilities and duties remain valid and are enforced after termination or change of employment.

เพื่อให้แน่ใจว่าความรับผิดชอบและหน้าที่ด้านความมั่นคงปลอดภัยสารสนเทศยังคงมีผลบังคับและได้รับการบังคับใช้หลังจากการสิ้นสุดหรือการเปลี่ยนแปลงการจ้างงาน

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Termination Checklist | รายการตรวจสอบการสิ้นสุดการจ้างงาน

**Applies to**: Resignation, retirement, termination (voluntary or involuntary)

**Termination Security Checklist** (Completed within **24 hours** of termination notice) 🔴:

##### Immediate Actions (Same Day) | การดำเนินการทันที (ในวันเดียวกัน)

- [ ] **Disable Active Directory/SSO Account**
  - Prevents login to all systems
  - Owner: IT Team
  - Timing: Immediately upon notification (for involuntary termination) or last working day (for voluntary resignation)

- [ ] **Revoke VPN Access**
  - Prevents remote access to network
  - Owner: IT Team

- [ ] **Disable Email Account**
  - Set up auto-reply with alternative contact
  - Forward emails to manager (if needed for transition)
  - Owner: IT Team

- [ ] **Revoke Database Access** 🔴
  - Critical for roles with access to PII or E-KYC data
  - Owner: DBA
  - Verify: Check access logs for no activity post-termination

- [ ] **Revoke Cloud Access** (AWS/Azure/GCP Console)
  - Owner: DevOps Team

- [ ] **Revoke Application Access** (Admin panels, internal tools)
  - Owner: IT Team

- [ ] **Disable MFA Tokens**
  - Revoke enrolled devices
  - Owner: IT Security

##### Physical Security (Last Working Day) | ความปลอดภัยทางกายภาพ (วันทำงานสุดท้าย)

- [ ] **Return Badge/Access Card**
  - Deactivate card in access control system
  - Owner: Facility Manager

- [ ] **Return Keys** (if any)
  - Office keys, server room keys, etc.
  - Owner: Facility Manager

- [ ] **Escort Out of Premises** (for involuntary termination or high-risk roles)
  - HR or security escorts employee
  - Ensures no unauthorized access after termination meeting

##### Asset Return (Last Working Day or Before) | การคืนทรัพย์สิน

- [ ] **Return Laptop**
  - Check for company data (to be wiped later)
  - Owner: IT Team
  - Action: Wipe and redeploy or dispose securely

- [ ] **Return Mobile Phone** (if company-issued)
  - Wipe device remotely if not returned
  - Owner: IT Team

- [ ] **Return External Drives, USB Sticks**
  - Check for company data
  - Owner: IT Team

- [ ] **Delete Company Data from Personal Devices**
  - If employee used personal device for work (BYOD)
  - Employee signs attestation: "I have deleted all company data from my personal devices"
  - Owner: HR

##### Data and Intellectual Property | ข้อมูลและทรัพย์สินทางปัญญา

- [ ] **Confirm No Data Retention** 🔴
  - Employee signs form: "I confirm I have not retained any company data, including customer PII, biometric data, source code, or confidential information on personal devices or external storage."
  - Violation consequence: Legal action
  - Owner: HR + CISO

- [ ] **Review Access Logs** (Post-Termination) 🔴
  - 7 days after termination, review logs to ensure no access attempts
  - If access detected: Investigate (possible account compromise or unauthorized access)
  - Owner: CISO

##### Knowledge Transfer | การถ่ายทอดความรู้

- [ ] **Document Handover** (for planned resignations)
  - Employee documents their work (projects, passwords for service accounts, etc.)
  - Owner: Manager

- [ ] **Service Account Password Changes** 🔴
  - If employee knew passwords for service accounts (e.g., E-KYC API keys, database passwords)
  - **Immediately rotate passwords/keys** after termination
  - Owner: IT Security

---

#### 2. Change of Employment (Internal Transfer) | การเปลี่ยนแปลงการจ้างงาน (การโยกย้ายภายใน)

**Scenario**: Employee moves from one role to another within Certogo (e.g., Developer → Marketing)

**Access Review Checklist**:

- [ ] **Revoke Old Role Access**
  - Remove from old team's groups (Active Directory, Slack, etc.)
  - Revoke access to old role's systems (e.g., production DB if moving to non-technical role)
  - Owner: IT Team

- [ ] **Grant New Role Access**
  - Add to new team's groups
  - Grant minimum necessary access (principle of least privilege)
  - Owner: IT Team

- [ ] **Re-Training** (if needed)
  - If moving to role with different data access (e.g., gaining PII access)
  - Complete PDPA training before granting access 🔴
  - Owner: HR

**Timeline**: Complete within 3 business days of role change

---

#### 3. Continued Confidentiality Obligations | ข้อผูกพันความลับที่ยังคงมีผล

**After Termination**:
- Confidentiality obligations in employment contract **continue indefinitely** (even after termination)
- Employee cannot disclose:
  - Customer data (PII, biometric data)
  - Trade secrets (source code, algorithms)
  - Business strategies
- Violation consequence: Legal action (civil lawsuit for damages)

**Reminder Letter** (sent on last working day):
HR sends formal letter reminding employee of continued obligations:
```
Dear [Employee Name],

As your employment with Certogo ends on [DATE], we remind you of your
continued obligations:

1. Confidentiality: You must not disclose any confidential information,
   including customer data, biometric data, or trade secrets.

2. Non-Solicitation: You must not solicit Certogo's employees or customers
   for [12 months] after termination (if applicable per contract).

3. Intellectual Property: All work product created during employment remains
   Certogo's property.

Violation of these obligations may result in legal action.

Thank you for your service to Certogo.

Best regards,
Human Resources Team
```

---

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/procedures/termination-checklist.pdf` - Security termination procedure
- `/evidence/records/hr-records/termination-log.xlsx` - Summary of terminations and checklist completion
- `/evidence/forms/data-deletion-attestation-form.pdf` - Form signed by employee
- `/evidence/forms/asset-return-form.pdf` - Form for returned assets
- `/evidence/templates/termination-reminder-letter.pdf` - Template for post-termination obligations letter

---

## A.6.6 Confidentiality or Non-Disclosure Agreements
## ข้อตกลงความลับหรือการไม่เปิดเผยข้อมูล

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้** 🔴 **CRITICAL FOR E-KYC DATA**

### Control Objective | วัตถุประสงค์
To ensure that employees and external parties sign confidentiality or non-disclosure agreements.

เพื่อให้แน่ใจว่าพนักงานและบุคคลภายนอกลงนามในข้อตกลงความลับหรือการไม่เปิดเผยข้อมูล

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. NDA for Employees | NDA สำหรับพนักงาน

**Included in Employment Contract**:
- All employees sign confidentiality clause as part of employment contract
- Covers all confidential information, including:
  - Customer PII
  - 🔴 **Biometric data** (facial images, ID card scans)
  - Source code and trade secrets
  - Business strategies
- Duration: Indefinite (continues after employment)

**No separate NDA needed** (confidentiality clause in employment contract is sufficient).

---

#### 2. NDA for Contractors | NDA สำหรับผู้รับเหมา

**Standalone NDA**:
- All contractors/freelancers sign separate NDA before starting work
- Template: `/evidence/templates/contractor-nda-template.pdf`

**Key Clauses** 🔴:
1. **Definition of Confidential Information**:
   - "Any information disclosed by Certogo, including customer data, biometric data processed through E-KYC, source code, business plans, and financial information."

2. **Obligations**:
   - Contractor must not disclose confidential information to third parties
   - Contractor must use confidential information only for authorized work
   - Contractor must protect confidential information with same care as their own

3. **Exceptions** (information that is NOT confidential):
   - Publicly available information
   - Information lawfully obtained from third parties
   - Information developed independently by contractor

4. **Return or Destruction**:
   - Upon contract termination, contractor must return or destroy all confidential information
   - Deletion certificate required 🔴

5. **Remedies**:
   - Breach may result in injunction (court order to stop disclosure)
   - Contractor liable for damages

6. **Governing Law**: Thai law
7. **Jurisdiction**: Thai courts

**Signing Process**:
- NDA sent before contract start (via DocuSign or equivalent)
- Must be signed before accessing any Certogo systems or data
- Tracked in: `/evidence/records/nda-log.xlsx`

---

#### 3. NDA for Third-Party Auditors | NDA สำหรับผู้ตรวจสอบบุคคลที่สาม

**Scenario**: External auditors (e.g., ISO 27001 CB auditor, penetration testers) need access to sensitive data.

**Two-Way NDA** (Mutual NDA):
- Certogo and auditor both agree to protect each other's confidential information
- Template: `/evidence/templates/mutual-nda-template.pdf`

**Special Provisions for Auditors**:
- **Limited Use**: Auditor may use confidential information only for audit purposes
- **No Retention**: After audit, auditor must return or destroy all Certogo data
- **Sub-Contractors**: Auditor must require sub-contractors to sign NDA
- **Biometric Data** 🔴: Auditor must not be provided with actual biometric data (only verification results or anonymized/redacted data)

**Example**: ISO 27001 auditor reviews evidence:
- Certogo provides: Appman's security assessment report, DPA, quarterly reports
- Certogo **does NOT provide**: Actual customer biometric data or API keys
- Auditor signs NDA before accessing evidence repository

---

#### 4. NDA for Business Partners | NDA สำหรับพันธมิตรทางธุรกิจ

**Scenario**: Certogo explores partnership or integration with another company.

**Mutual NDA**:
- Both parties protect each other's information
- Common in pre-sales discussions, integrations, or joint ventures

**Example**: Integration with a new E-KYC provider (future):
- Before sharing technical details of current E-KYC integration
- NDA covers: Integration architecture, data flows, API specifications
- Allows evaluation without public disclosure

---

#### 5. NDA Tracking and Management | การติดตามและจัดการ NDA

**NDA Log** maintained in: `/evidence/records/nda-log.xlsx`

**Columns**:
- NDA ID
- Party Name (individual or company)
- Type (Employee, Contractor, Auditor, Partner)
- Date Signed
- Expiration Date (if applicable, usually "indefinite")
- Status (Active, Expired, Terminated)
- Custodian (who has the signed copy)

**Annual Review**:
- HR reviews NDA log annually
- Identifies expired NDAs (for contractors no longer working)
- Archives signed copies securely

**Storage**:
- Original signed NDAs stored in HR system (electronic or physical)
- Copies provided upon request (e.g., for legal action)

---

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/templates/contractor-nda-template.pdf` - Standalone NDA for contractors
- `/evidence/templates/mutual-nda-template.pdf` - Mutual NDA for auditors/partners
- `/evidence/records/nda-log.xlsx` - NDA tracking log
- `/evidence/samples/signed-nda-sample.pdf` - Sample signed NDA (redacted for privacy)

---

## A.6.7 Remote Working
## การทำงานทางไกล

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้**

### Control Objective | วัตถุประสงค์
To implement security for information when personnel are working remotely.

เพื่อนำมาตรการความปลอดภัยสำหรับสารสนเทศมาใช้เมื่อบุคลากรทำงานทางไกล

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. Remote Work Policy | นโยบายการทำงานทางไกล

**Certogo Remote Work Policy** (Post-COVID hybrid work environment):

**Eligibility**:
- All employees (except roles requiring physical presence)
- Hybrid: 3 days office, 2 days remote (typical)

**Security Requirements for Remote Work** 🔴:

##### Device Security | ความปลอดภัยของอุปกรณ์

1. **Use Company-Issued Laptop**:
   - Mandatory for roles with access to production systems or PII
   - Pre-configured with security controls (antivirus, disk encryption, firewall)
   - Managed by IT via MDM (Mobile Device Management)

2. **Personal Device (BYOD) - Restricted** 🔴:
   - Allowed for email and Slack only (not for production access)
   - Must install security app (e.g., Microsoft Intune, Workspace ONE)
   - If accessing PII: Must complete BYOD security training

##### Network Security | ความปลอดภัยของเครือข่าย

1. **VPN Mandatory** 🔴:
   - All remote access to Certogo systems must go through VPN
   - VPN enforces MFA
   - Split tunneling disabled (all traffic goes through VPN for monitoring)

2. **Home Wi-Fi Security**:
   - Use WPA3 or WPA2 encryption (not WEP or open)
   - Change default router password
   - Guest network for family members (not same network as work laptop)

3. **Public Wi-Fi Prohibited** 🔴 for sensitive work:
   - Café, airport, hotel Wi-Fi: Do NOT access production systems or PII
   - If urgent: Use VPN + mobile hotspot (from personal phone)

##### Physical Security | ความปลอดภัยทางกายภาพ

1. **Privacy Screen**:
   - Recommended when working in public spaces
   - Prevents shoulder surfing

2. **Lock Screen When Away**:
   - Configure auto-lock after 5 minutes of inactivity
   - Manually lock (Ctrl+Alt+Del or Cmd+Ctrl+Q) when leaving desk

3. **Secure Storage**:
   - Do not leave laptop in car (risk of theft)
   - Lock laptop when not in use

##### Data Protection | การคุ้มครองข้อมูล

1. **No Printing of Confidential Data** at home
   - If absolutely necessary: Use home printer, then shred immediately
   - Do not print PII or biometric data 🔴

2. **No Sharing Screens** with family members
   - Use private workspace
   - Headphones for confidential calls

3. **Encrypted USB Drives Only** (if needed)
   - BitLocker or equivalent encryption
   - Approved by IT before use

---

#### 2. Remote Access Technologies | เทคโนโลยีการเข้าถึงทางไกล

**VPN (Virtual Private Network)**:
- Solution: [VPN VENDOR, e.g., Cisco AnyConnect, OpenVPN]
- Authentication: Username + password + MFA (TOTP)
- Logging: All VPN connections logged (who, when, from where)
- Review: IT reviews VPN logs monthly for anomalies

**Remote Desktop (RDP) / Jump Server**:
- For accessing specific servers remotely
- Additional authentication required
- Session recording enabled (for audit)

**Cloud Access**:
- AWS/Azure/GCP console access via SSO (with MFA)
- Conditional access policies: Require VPN or corporate IP

---

#### 3. Remote Work Security Checklist | รายการตรวจสอบความปลอดภัยการทำงานทางไกล

**Before Working Remotely** (Employee Checklist):

- [ ] Laptop is fully patched and updated
- [ ] Antivirus is active and up-to-date
- [ ] VPN client installed and tested
- [ ] MFA enrolled (TOTP app or hardware token)
- [ ] Home Wi-Fi uses WPA2/WPA3 encryption
- [ ] Privacy screen filter attached to laptop (if working in public)

**During Remote Work**:

- [ ] Connect to VPN before accessing company systems
- [ ] Lock screen when away from desk
- [ ] Do not share screen with unauthorized persons
- [ ] Use headphones for confidential calls
- [ ] Shred any printed confidential documents

**End of Day**:

- [ ] Disconnect VPN (to allow personal use of internet)
- [ ] Shut down or lock laptop
- [ ] Store laptop securely

---

#### 4. Monitoring and Compliance | การติดตามและการปฏิบัติตาม

**IT Monitoring**:
- VPN usage logs (detect abnormal locations or times)
- Endpoint security status (via MDM): Antivirus, firewall, encryption
- Failed MFA attempts (potential account compromise)

**Non-Compliance**:
- If employee repeatedly works without VPN: Warning
- If laptop found unencrypted during spot check: Immediate remediation + written warning

---

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/policies/remote-work-policy.pdf` - Remote work security policy
- `/evidence/procedures/vpn-setup-guide.pdf` - VPN setup instructions
- `/evidence/records/vpn-usage-logs/` - VPN connection logs (last 3 months)
- `/evidence/records/mdm-compliance-report.pdf` - Endpoint security compliance

---

## A.6.8 Information Security Event Reporting
## การรายงานเหตุการณ์ด้านความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable** | **ใช้ได้** 🔴 **CRITICAL FOR INCIDENT RESPONSE**

### Control Objective | วัตถุประสงค์
To ensure information security events are reported through appropriate management channels as quickly as possible.

เพื่อให้แน่ใจว่าเหตุการณ์ด้านความมั่นคงปลอดภัยสารสนเทศได้รับการรายงานผ่านช่องทางการจัดการที่เหมาะสมอย่างรวดเร็วที่สุด

### Implementation for Certogo | การนำไปปรับใช้สำหรับ Certogo

#### 1. What to Report | สิ่งที่ต้องรายงาน

**All employees must report** the following immediately:

##### Category 1: Security Incidents 🔴 (CRITICAL - Report within 1 hour)

- **Data Breach**:
  - Unauthorized access to customer PII
  - **Biometric data exposure** 🔴
  - Database leak
  - Stolen laptop with unencrypted data

- **System Compromise**:
  - Server hacked
  - Malware/ransomware infection
  - Unauthorized admin access detected

- **Service Disruption**:
  - **E-KYC API unavailable** (customer-facing impact) 🔴
  - LMS platform down
  - DDoS attack

##### Category 2: Security Events (Report within 24 hours)

- **Suspected Phishing**:
  - Suspicious email received
  - Clicked phishing link (but no data entered)

- **Lost or Stolen Devices**:
  - Laptop, phone, USB drive, badge

- **Unauthorized Access Attempts**:
  - Failed login attempts (multiple)
  - Someone tried to tailgate into office

- **Policy Violations**:
  - Colleague sharing passwords
  - Unauthorized software installation
  - Sensitive data printed at home

##### Category 3: Security Weaknesses (Report within 7 days)

- **Vulnerabilities Discovered**:
  - Security flaw in code
  - Unpatched system
  - Weak password policy in third-party service

- **Configuration Issues**:
  - Misconfigured cloud storage (public access)
  - Firewall rule too permissive

---

#### 2. How to Report | วิธีการรายงาน

**Primary Reporting Channels** (Use in order of urgency):

##### Option 1: Email (For Non-Urgent Events)
- To: `security@certogo.com`
- Subject: `[SECURITY EVENT] [Brief Description]`
- Include:
  - What happened?
  - When did it happen?
  - Who is involved?
  - What is the potential impact?
  - What actions have you taken (if any)?

##### Option 2: Slack (For Urgent Incidents) 🔴
- Channel: `#security-incidents` (monitored 24/7)
- Tag: `@security-team`
- For **critical incidents** (data breach, system compromise):
  - Also call CISO directly: [PHONE NUMBER]

##### Option 3: Phone (For CRITICAL Incidents After Hours) 🔴
- CISO: [PHONE NUMBER]
- CTO (if CISO unavailable): [PHONE NUMBER]
- **Use for**: Biometric data breach, ransomware, major outage

##### Option 4: Anonymous Reporting (For Reporting Colleagues)
- Whistleblower hotline: [EMAIL or PHONE]
- Can report anonymously if uncomfortable reporting directly
- Example: "I saw my colleague share their password with a contractor"

---

#### 3. Incident Response Workflow | เวิร์กโฟลว์การตอบสนองเหตุการณ์

**When an incident is reported**:

**Step 1**: **Acknowledgment** (Within 15 minutes for critical, 2 hours for non-critical)
- Security team acknowledges receipt of report
- Assigns incident ID (e.g., `INC-2025-001`)
- Thanks employee for reporting

**Step 2**: **Initial Assessment** (Within 1 hour for critical)
- CISO/Security Team assesses:
  - Severity: Critical, High, Medium, Low
  - Scope: How many users/systems affected?
  - Containment: Is it still ongoing or contained?

**Step 3**: **Containment** (Immediate for critical)
- Stop the incident from spreading
- Example actions:
  - Disable compromised account
  - Isolate infected server
  - Block malicious IP
  - **For E-KYC breach**: Notify Appman, disable API temporarily

**Step 4**: **Investigation**
- Collect evidence (logs, screenshots, interviews)
- Determine root cause
- Assess impact (how much data was affected?)

**Step 5**: **Remediation**
- Fix the vulnerability that caused the incident
- Example: Patch software, change passwords, update firewall rules

**Step 6**: **Recovery**
- Restore normal operations
- Verify systems are secure

**Step 7**: **Notification** (if required)
- **Data Breach**: Notify authorities (PDPC) within 72 hours (PDPA requirement) 🔴
- **Customer Notification**: If customer data affected, notify within 72 hours
- **E-KYC Provider**: If incident related to E-KYC, notify Appman (per contract)

**Step 8**: **Post-Incident Review** (Within 7 days)
- Lessons learned
- What went well? What could improve?
- Update procedures
- Communicate findings to team (anonymized if needed)

**Step 9**: **Close Incident**
- Document final report
- Close incident ticket
- Archive evidence

---

#### 4. Reporting Culture | วัฒนธรรมการรายงาน

**"See Something, Say Something"** | **"เห็นอะไร บอกอะไร"**

**No Punishment for Good-Faith Reporting**:
- Employees will NOT be punished for reporting security events in good faith
- Example: If you clicked a phishing link, report it immediately → No penalty
- Hiding incidents is the real violation 🔴

**Rewards for Reporting**:
- Quarterly recognition for employees who report most security events
- "Security Champion" award (with small gift)
- Positive mention in performance reviews

**Monthly Security Metrics** (Shared with All Staff):
- Number of incidents reported: [X]
- Average time to report: [Y] hours
- Top incident types: [Phishing, Lost devices, etc.]
- Goal: Encourage transparency

---

#### 5. Special Reporting for E-KYC Incidents 🔴

**If incident involves E-KYC or biometric data**:

**Immediate Actions** (Within 1 hour):
1. Report to CISO
2. CISO notifies DPO (for PDPA assessment)
3. CISO notifies Appman (per contract, 4-hour notification clause)
4. Assess if PDPC notification required (72-hour deadline)

**Example Scenarios**:

**Scenario 1**: Employee sees biometric data in production logs (should not happen)
- **Report to**: CISO (immediately)
- **Action**:
  - Purge logs containing biometric data
  - Investigate: Why was it logged? (code bug?)
  - Fix code to prevent future logging
  - Assess if data breach (was log accessed by unauthorized persons?)

**Scenario 2**: E-KYC API returns error with customer facial image in response (bug)
- **Report to**: CISO + CTO (immediately)
- **Action**:
  - Disable API integration temporarily
  - Notify Appman (API bug on their end)
  - Fix and test before re-enabling
  - Review logs to see if biometric data was logged by Certogo

**Scenario 3**: Appman notifies Certogo of data breach
- **Report to**: CISO + DPO (immediately, even if after hours)
- **Action**:
  - Activate incident response plan
  - Assess scope: Which customers affected?
  - Coordinate with Appman for details
  - Notify PDPC within 72 hours (if required)
  - Notify customers within 72 hours
  - Engage legal counsel
  - Cyber insurance claim

---

### Evidence Files | ไฟล์หลักฐาน

📄 **Required Documents** | **เอกสารที่ต้องมี**:
- `/evidence/procedures/incident-reporting-procedure.pdf` - Incident reporting procedure
- `/evidence/records/incident-log.xlsx` - Incident tracking log (last 12 months)
- `/evidence/records/incident-reports/` - Detailed incident reports (samples)
- `/evidence/training-materials/incident-reporting-training.pdf` - Training slides
- `/evidence/communications/incident-reporting-poster.pdf` - Poster for office (reminder)

---

## Summary | สรุป

**A.6 People Controls** are critical for managing the **human factor** in information security, especially for Certogo where employees may have access to **highly sensitive biometric data** 🔴.

**มาตรการควบคุมด้านบุคลากร A.6** มีความสำคัญอย่างยิ่งสำหรับการจัดการ **ปัจจัยมนุษย์** ในความมั่นคงปลอดภัยสารสนเทศ โดยเฉพาะสำหรับ Certogo ที่พนักงานอาจสามารถเข้าถึง **ข้อมูลชีวมิติที่ละเอียดอ่อนสูง** 🔴

**Key Highlights**:

1. **A.6.1 Screening**: Level 3 (highest) background checks for roles with biometric data access 🔴
2. **A.6.2 Employment Terms**: Security clauses in contracts, including PDPA obligations for biometric data
3. **A.6.3 Training** 🔴 **MOST CRITICAL**: Mandatory PDPA & biometric data handling training for all roles with PII access
4. **A.6.4 Disciplinary Process**: Level 4 (termination + legal action) for unauthorized biometric data access
5. **A.6.5 Termination**: 24-hour access revocation, data deletion attestation required
6. **A.6.6 NDAs**: All contractors sign NDA before accessing company data
7. **A.6.7 Remote Work**: VPN mandatory, no PII access on public Wi-Fi
8. **A.6.8 Incident Reporting**: 1-hour reporting deadline for data breaches, special procedures for E-KYC incidents 🔴

**Compliance Rate**: 100% (8/8 controls applicable and implemented)

---

**Document Version** | **เวอร์ชันเอกสาร**: 1.0
**Last Updated** | **อัปเดตล่าสุด**: 2025-01-20
**Next Review** | **ทบทวนครั้งต่อไป**: 2026-01-20

**Approval** | **การอนุมัติ**:
- [ ] CISO
- [ ] HR Director
- [ ] DPO
- [ ] CEO
