# PDPA Compliance Policy | นโยบายการปฏิบัติตามพ.ร.บ.คุ้มครองข้อมูลส่วนบุคคล

**Document Control | การควบคุมเอกสาร**

| Field | Value |
|-------|-------|
| **Document ID** | POL-003 |
| **Version** | 1.0 |
| **Effective Date** | [To be filled - วันที่มีผลบังคับใช้] |
| **Review Date** | [Annual - ทบทวนทุกปี] |
| **Document Owner** | Data Protection Officer (DPO) |
| **Approved By** | Chief Executive Officer (CEO) |
| **Classification** | Internal Use Only - ใช้ภายในองค์กรเท่านั้น |
| **Related Standards** | ISO 27001:2022 A.5.34, Thailand PDPA B.E. 2562 (2019) |

---

## 1. Purpose and Scope | วัตถุประสงค์และขอบเขต

### 1.1 Purpose | วัตถุประสงค์

This policy establishes Certogo's framework for compliance with the **Personal Data Protection Act B.E. 2562 (2019)** ("PDPA"), Thailand's comprehensive data privacy law. Given that Certogo processes **highly sensitive biometric data** through E-KYC integration, PDPA compliance is not just a legal requirement—it is critical to maintaining customer trust and avoiding severe penalties (up to 5% of annual revenue).

This policy ensures that:
- Personal Data is collected, used, and disclosed lawfully and fairly
- **Biometric data** (PDPA Section 26 sensitive data) receives the highest level of protection 🔴
- Data subjects' rights are respected and facilitated
- Third-party data processors (E-KYC providers) comply with PDPA requirements
- Certogo maintains accountability and transparency in data processing activities

**Thai | ไทย**: นโยบายนี้กำหนดกรอบการปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล พ.ศ. 2562

### 1.2 Scope | ขอบเขต

This policy applies to:

**Data Types | ประเภทข้อมูล**:

1. **🔴 SENSITIVE PERSONAL DATA (PDPA Section 26)** - Requires explicit consent:
   - **Biometric data**: Facial images, ID card scans (processed by E-KYC provider)
   - Note: Certogo does NOT store biometric data; it is processed by Appman E-KYC provider

2. **PERSONAL DATA (PDPA Section 6)** - Requires consent or legal basis:
   - Identification data: Full name, ID card number, passport number
   - Contact data: Email address, phone number, mailing address
   - Account data: Username, encrypted password, profile picture
   - Usage data: Course enrollments, progress tracking, certificates earned
   - Technical data: IP address, browser type, device ID, session logs

3. **NON-PERSONAL DATA** (Out of Scope):
   - Aggregated analytics (anonymized)
   - Public company information

**People | บุคคล**:
- All Certogo employees handling Personal Data
- Data Protection Officer (DPO)
- Third-party data processors (E-KYC provider, cloud hosting)
- B2B customers' administrators (acting as Data Controllers for their employees' data)
- B2C end users (Data Subjects)

**Processes | กระบวนการ**:
- Collection of Personal Data (registration, E-KYC verification)
- Use and disclosure (service delivery, compliance, marketing)
- Storage and retention (databases, backups)
- Deletion and destruction (data subject requests, retention expiry)
- Cross-border transfer (if any - currently none for biometric data)
- Data breach response

---

## 2. Legal Framework and Definitions | กรอบกฎหมายและคำนิยาม

### 2.1 PDPA Key Provisions

**PDPA B.E. 2562 (2019)** - Effective since June 1, 2022

**Key Sections Relevant to Certogo**:

| Section | Topic | Certogo Application |
|---------|-------|---------------------|
| **Section 6** | Definition of Personal Data | Name, email, phone, ID number, IP address |
| **Section 26** 🔴 | Sensitive Personal Data | **Biometric data** (facial images, ID scans) - requires **explicit consent** |
| **Section 19** | Consent requirements | Must obtain clear, informed consent before collection |
| **Section 21** | Purpose limitation | Data used only for disclosed purposes |
| **Section 23** | Data retention | Retain only as long as necessary for purpose |
| **Section 27** | Disclosure to third parties | Requires consent or legal basis; DPA with processors |
| **Section 28-35** | Data subject rights | Access, rectification, deletion, portability, objection |
| **Section 37** 🔴 | Data breach notification | **72 hours** to PDPC and affected individuals if high risk |
| **Section 41** | Penalties | Up to 5 million THB or up to 5% of annual revenue (whichever is higher) |

### 2.2 Key Definitions | คำจำกัดความสำคัญ

| Term | Definition (English) | คำจำกัดความ (ไทย) |
|------|---------------------|-------------------|
| **Personal Data** | Information relating to an identified or identifiable person | ข้อมูลเกี่ยวกับบุคคลที่สามารถระบุตัวตนได้ |
| **Sensitive Personal Data** 🔴 | PDPA Section 26: Biometric data, health data, religious beliefs, criminal records, etc. | ข้อมูลส่วนบุคคลที่มีความอ่อนไหว: ข้อมูลไบโอเมตริกซ์, ข้อมูลสุขภาพ, ฯลฯ |
| **Data Subject** | Individual whose Personal Data is processed | เจ้าของข้อมูลส่วนบุคคล |
| **Data Controller** | Entity determining purposes and means of processing (Certogo for B2C; B2B customers for their employees) | ผู้ควบคุมข้อมูลส่วนบุคคล |
| **Data Processor** | Entity processing data on behalf of Controller (E-KYC provider, cloud hosting) | ผู้ประมวลผลข้อมูลส่วนบุคคล |
| **Consent** | Voluntary, specific, informed, and unambiguous indication of Data Subject's wishes | ความยินยอม |
| **Explicit Consent** 🔴 | Required for Sensitive Personal Data; must be clear and separate from general consent | ความยินยอมโดยชัดแจ้ง (สำหรับข้อมูลอ่อนไหว) |

---

## 3. Roles and Responsibilities | บทบาทและความรับผิดชอบ

### 3.1 Data Protection Officer (DPO) | เจ้าหน้าที่คุ้มครองข้อมูลส่วนบุคคล

**Appointment**: Mandatory under PDPA Section 40 (for organizations processing Sensitive Personal Data)

**Contact Information**:
- Name: [DPO Name]
- Email: privacy@certogo.com
- Phone: [DPO Phone]

**Responsibilities**:
- Oversee PDPA compliance program
- Conduct Data Protection Impact Assessments (DPIA) for high-risk processing 🔴
- Manage data subject rights requests (within 30-day deadline)
- Coordinate data breach response and PDPC notifications
- Review and approve Data Processing Agreements (DPAs) with third parties
- Train employees on PDPA requirements (annually)
- Liaise with Personal Data Protection Committee (PDPC) if needed
- Maintain Record of Processing Activities (ROPA)
- Report PDPA compliance status to CEO (quarterly)

### 3.2 Chief Executive Officer (CEO)

**Responsibilities**:
- Ultimate accountability for PDPA compliance
- Approve this PDPA Compliance Policy
- Allocate resources for PDPA program (DPO, tools, training)
- Approve high-risk data processing activities (DPIA required)
- Approve data breach notifications to PDPC

### 3.3 Chief Information Security Officer (CISO)

**Responsibilities**:
- Implement technical and organizational security measures (PDPA Section 37)
- Ensure encryption of Sensitive Personal Data (biometric data) 🔴
- Monitor third-party data processors (E-KYC provider security)
- Lead data breach investigation and containment
- Coordinate with DPO on security-related PDPA requirements

### 3.4 Chief Technology Officer (CTO)

**Responsibilities**:
- Design systems with data protection by design and by default (PDPA principle)
- Implement data retention and automated deletion systems
- Ensure data localization (biometric data stored in Thailand only) 🔴
- Facilitate data subject rights (automated data export, deletion)

### 3.5 Legal / Compliance Team

**Responsibilities**:
- Review contracts with third-party data processors (DPA compliance)
- Advise on legal basis for data processing
- Coordinate with external legal counsel on PDPA matters
- Monitor PDPA regulatory changes

### 3.6 Human Resources (HR)

**Responsibilities**:
- Process employee Personal Data in compliance with PDPA
- Conduct PDPA training for all employees (annually)
- Maintain training records

### 3.7 Marketing Team

**Responsibilities**:
- Obtain proper consent for marketing communications
- Manage consent withdrawal requests (opt-out)
- Ensure marketing materials include privacy information

### 3.8 Customer Support Team

**Responsibilities**:
- Receive and forward data subject rights requests to DPO (within 24 hours)
- Assist customers with privacy-related inquiries
- Escalate data breach reports to CISO and DPO immediately

### 3.9 All Employees | พนักงานทุกคน

**Responsibilities**:
- Complete mandatory PDPA training (annually)
- Handle Personal Data only for authorized business purposes
- **NEVER access, copy, or share biometric data** 🔴
- Report suspected data breaches or PDPA violations immediately (within 1 hour)
- Protect credentials and devices (prevent unauthorized access to Personal Data)

---

## 4. Data Processing Principles | หลักการประมวลผลข้อมูล

Certogo shall process Personal Data in accordance with PDPA principles:

### 4.1 Lawfulness, Fairness, and Transparency | ความชอบด้วยกฎหมาย ความเป็นธรรม และความโปร่งใส

**Requirement**: Process data lawfully, fairly, and in a transparent manner.

**Certogo Implementation**:
- ✅ Publish clear **Privacy Notice** on website and mobile app
- ✅ Use plain language (Thai and English) to explain data processing
- ✅ Obtain valid consent before collecting Personal Data
- ✅ Provide contact information for privacy inquiries (privacy@certogo.com)

**Privacy Notice Must Include** (PDPA Section 23):
- Purpose of data collection
- Data retention period
- Data recipients (third parties, e.g., E-KYC provider)
- Data subject rights
- Consent withdrawal procedures
- DPO contact information

### 4.2 Purpose Limitation | การจำกัดวัตถุประสงค์

**Requirement**: Collect data for specified, explicit, and legitimate purposes only.

**Certogo Purposes**:

| Purpose | Data Collected | Legal Basis |
|---------|----------------|-------------|
| **Account creation and authentication** | Name, email, phone, password | Contract performance (PDPA Section 24(1)) |
| **E-KYC identity verification** 🔴 | ID card number, facial image, ID card scan | **Explicit consent** (PDPA Section 26) |
| **Course delivery and progress tracking** | Course enrollments, quiz scores, certificates | Contract performance |
| **Customer support** | Support tickets, chat logs | Contract performance + Legitimate interest |
| **Marketing communications** (optional) | Email, phone | **Consent** (must be separate from service consent) |
| **Legal compliance** (e.g., accounting) | Transaction records, invoices | Legal obligation (PDPA Section 24(2)) |
| **Security and fraud prevention** | IP address, device ID, access logs | Legitimate interest (PDPA Section 24(5)) |

**Prohibited Uses**:
- ❌ Use biometric data for purposes other than identity verification
- ❌ Sell or rent Personal Data to third parties
- ❌ Use Personal Data for purposes not disclosed in Privacy Notice

### 4.3 Data Minimization | การเก็บข้อมูลเท่าที่จำเป็น

**Requirement**: Collect only data that is adequate, relevant, and limited to what is necessary.

**Certogo Implementation**:
- ✅ Collect only minimum data required for each purpose
- ✅ **Do NOT store biometric data** on Certogo servers 🔴 (processed by E-KYC provider only)
- ✅ Receive only E-KYC verification result (Pass/Fail), not raw biometric data
- ✅ Optional fields clearly marked (e.g., marketing consent is optional)

**Examples**:
- For account creation: Name, email (required); Phone (optional unless needed for 2FA)
- For E-KYC: ID card image, selfie (required for verification, deleted after 30 days)
- For course delivery: Course enrollment data (required); Profile picture (optional)

### 4.4 Accuracy | ความถูกต้อง

**Requirement**: Ensure Personal Data is accurate and kept up to date.

**Certogo Implementation**:
- ✅ Allow users to update their profile information anytime (self-service)
- ✅ Validate email addresses (verification email sent upon registration)
- ✅ Periodically prompt users to review and update information (annually)
- ✅ Facilitate rectification requests (Data Subject Right - see Section 5.2)

### 4.5 Storage Limitation | การจำกัดระยะเวลาการเก็บรักษา

**Requirement**: Retain data only as long as necessary for the purpose.

**Certogo Data Retention Schedule** 🔴:

| Data Type | Retention Period | Deletion Method | Legal Basis |
|-----------|------------------|-----------------|-------------|
| **Biometric data** (at E-KYC provider) 🔴 | **30 days** from verification | **Automated deletion** + certificate | PDPA Section 26 + DPA requirement |
| **E-KYC verification result** (Pass/Fail) | **90 days** from verification | Automated deletion | Business need + PDPA compliance |
| **Active user account data** | While account is active + 90 days after closure | Manual deletion upon request or automated | Contract performance |
| **Course enrollment and certificates** | **7 years** from course completion | Automated deletion | Legal obligation (accounting law) |
| **Marketing consent records** | Until consent withdrawn + 1 year | Automated deletion | PDPA Section 19 (proof of consent) |
| **Security logs (access, authentication)** | **1 year** | Automated deletion | Legitimate interest (security) |
| **Support tickets** | **2 years** from ticket closure | Automated deletion | Legitimate interest (quality improvement) |
| **Deleted account data (backup)** | **30 days** in backups, then purged | Backup rotation | Technical necessity |

**Retention Policy Enforcement**:
- ✅ Automated deletion scripts run daily (check retention expiry)
- ✅ Quarterly audit of data retention compliance (DPO review)
- ✅ Exception handling: If legal hold required (e.g., litigation), suspend deletion with DPO approval

**CRITICAL**: Biometric Data Retention 🔴
- Appman E-KYC provider MUST delete biometric data after 30 days (contractual requirement)
- Certogo DPO shall verify deletion quarterly (request certificate of deletion or audit logs)
- Failure to delete = PDPA Section 26 violation + breach of DPA

### 4.6 Integrity and Confidentiality (Security) | ความปลอดภัย

**Requirement**: Process data in a manner that ensures appropriate security (PDPA Section 37).

**Certogo Security Measures** (See also: Information Security Policy POL-001):

**Technical Controls**:
- ✅ **Encryption at rest**: AES-256 for database (all Personal Data)
- ✅ **Encryption in transit**: TLS 1.3 for all API communications
- ✅ **Biometric data encryption** (at E-KYC provider): AES-256 at rest, TLS 1.3 in transit 🔴
- ✅ Access control: Role-based access control (RBAC), principle of least privilege
- ✅ Multi-factor authentication (MFA): Required for all admin and employee access
- ✅ Audit logging: All access to Personal Data logged (1-year retention)
- ✅ Database backups: Encrypted, tested quarterly

**Organizational Controls**:
- ✅ Background screening for employees with access to Sensitive Personal Data 🔴
- ✅ PDPA training (annually for all employees)
- ✅ Confidentiality agreements (all employees sign NDA)
- ✅ Clear desk and clear screen policy
- ✅ Disciplinary action for PDPA violations (up to termination)

**Third-Party Controls**:
- ✅ Data Processing Agreements (DPA) with all data processors (E-KYC provider, cloud hosting)
- ✅ Supplier security assessments (ISO 27001 certification required for Critical suppliers)
- ✅ Annual security reviews of E-KYC provider

### 4.7 Accountability | ความรับผิดชอบ

**Requirement**: Data Controller is responsible for and must demonstrate compliance with PDPA.

**Certogo Accountability Measures**:
- ✅ Appoint Data Protection Officer (DPO)
- ✅ Maintain Record of Processing Activities (ROPA) - updated quarterly
- ✅ Conduct Data Protection Impact Assessments (DPIA) for high-risk processing 🔴
- ✅ Document consent records (who, when, what purpose, how obtained)
- ✅ Maintain data processing inventory (systems, data types, purposes, retention)
- ✅ Regular PDPA compliance audits (internal: quarterly; external: annually)
- ✅ This PDPA Compliance Policy reviewed and approved by CEO annually

---

## 5. Data Subject Rights | สิทธิของเจ้าของข้อมูลส่วนบุคคล

PDPA grants Data Subjects the following rights (PDPA Sections 28-35):

### 5.1 Right to Be Informed | สิทธิในการได้รับทราบ

**What**: Data Subjects have the right to know how their data is collected, used, and shared.

**Certogo Implementation**:
- ✅ Display Privacy Notice before collecting data (registration page, E-KYC flow)
- ✅ Privacy Notice available on website: certogo.com/privacy (Thai and English)
- ✅ Notify users of Privacy Notice updates (email + in-app notification)

### 5.2 Right of Access | สิทธิในการเข้าถึงข้อมูล

**What**: Data Subjects can request a copy of their Personal Data.

**Certogo Process**:
1. **Request Submission**:
   - Data Subject emails privacy@certogo.com or uses in-app "Request My Data" form
   - Provide: Name, email, ID card number (for identity verification)

2. **Identity Verification** (within 3 days):
   - DPO verifies identity (check email, ID card number, or send OTP)
   - If identity cannot be verified, request additional proof

3. **Data Export** (within 30 days per PDPA Section 28):
   - IT Team exports data in machine-readable format (JSON or CSV)
   - Include: Profile data, course history, certificates, support tickets
   - **Exclude**: Biometric data (not stored by Certogo; request from Appman if needed) 🔴
   - Deliver via secure email (encrypted ZIP with password sent separately)

4. **Response**:
   - Free of charge for first request per year
   - Subsequent requests within same year: 500 THB fee (cost recovery)

**SLA**: 30 days from verified request (PDPA deadline)

### 5.3 Right to Rectification | สิทธิในการแก้ไขข้อมูล

**What**: Data Subjects can request correction of inaccurate or incomplete data.

**Certogo Process**:
- **Self-Service** (Preferred):
  - Users can update profile information directly (name, email, phone) via account settings
  - Changes logged in audit trail

- **DPO-Assisted**:
  - For data that cannot be self-updated (e.g., ID card number if incorrect after E-KYC)
  - Email privacy@certogo.com with correction request
  - DPO verifies and approves within 30 days

### 5.4 Right to Erasure ("Right to be Forgotten") | สิทธิในการลบข้อมูล 🔴

**What**: Data Subjects can request deletion of their Personal Data.

**Certogo Process**:

**1. Request Submission**:
   - Email privacy@certogo.com or use in-app "Delete My Account" button
   - Provide reason (optional but helpful): "No longer using service", "Withdraw consent", etc.

**2. Eligibility Assessment** (within 7 days):
   - DPO assesses if deletion is legally required or if exceptions apply

   **Deletion REQUIRED if**:
   - Data no longer necessary for original purpose
   - Data Subject withdraws consent (and no other legal basis exists)
   - Data was unlawfully processed

   **Deletion MAY BE REFUSED if** (PDPA Section 33):
   - Legal obligation to retain (e.g., accounting records - 7 years)
   - Legal claims (ongoing litigation)
   - Legitimate interest outweighs deletion (rare, must justify)

**3. Deletion Execution** (within 30 days):

   **What Gets Deleted**:
   - ✅ Profile data (name, email, phone)
   - ✅ Course progress data (if no legal retention requirement)
   - ✅ Marketing consent records (after 1-year proof-of-consent period)
   - ✅ **Biometric data at E-KYC provider** (DPO requests certificate of deletion from Appman) 🔴

   **What Gets ANONYMIZED** (not deleted):
   - ✅ Certificates (if 7-year retention required): Remove PII, keep anonymized record
   - ✅ Audit logs (if security investigation ongoing): Pseudonymize

   **What Gets RETAINED** (with justification):
   - ✅ Transaction records (if within 7-year accounting retention)
   - ✅ Data needed for legal defense (if litigation pending)

**4. Confirmation**:
   - DPO sends confirmation email: "Your data has been deleted on [Date]"
   - Provide summary of what was deleted vs. retained (with legal justification)

**5. Third-Party Deletion** 🔴:
   - DPO notifies E-KYC provider (Appman) to delete biometric data
   - Request certificate of deletion within 30 days
   - If certificate not provided, escalate to CISO (potential DPA breach)

**SLA**: 30 days from request (PDPA deadline)

**Special Case - Biometric Data Deletion** 🔴:
- Biometric data is automatically deleted after 30 days (per retention schedule)
- If Data Subject requests earlier deletion, DPO contacts Appman immediately (expedite deletion)
- Certificate of deletion provided to Data Subject upon request

### 5.5 Right to Data Portability | สิทธิในการโอนย้ายข้อมูล

**What**: Data Subjects can receive their data in a structured, commonly used format and transmit to another controller.

**Certogo Process**:
- Export data in JSON or CSV format (same as Right of Access)
- Includes: Profile, course enrollments, certificates, progress data
- Delivered via secure email or API (if receiving organization has integration capability)
- Free of charge
- **SLA**: 30 days

### 5.6 Right to Object | สิทธิในการคัดค้าน

**What**: Data Subjects can object to processing based on legitimate interest (e.g., marketing).

**Certogo Process**:

**Marketing Objection** (Easy opt-out):
- Click "Unsubscribe" link in marketing emails (processed immediately)
- Update preferences in account settings ("Marketing Communications" toggle)
- Email privacy@certogo.com with objection

**Other Processing Objection**:
- Email privacy@certogo.com with specific objection
- DPO assesses within 15 days:
  - If objection valid (no overriding legitimate interest), stop processing
  - If Certogo has compelling legitimate interest, explain to Data Subject

**SLA**: 15 days for assessment, 30 days for implementation

### 5.7 Right to Restrict Processing | สิทธิในการระงับการใช้ข้อมูล

**What**: Data Subjects can request temporary suspension of processing (e.g., while disputing accuracy).

**Certogo Process**:
- Email privacy@certogo.com with restriction request
- DPO places account in "Restricted" status (no marketing, limited use)
- Maintain data but do not process except for storage or legal claims
- **SLA**: 7 days to implement restriction, 30 days to resolve underlying issue

### 5.8 Right to Withdraw Consent | สิทธิในการถอนความยินยอม

**What**: Data Subjects can withdraw consent at any time (for consent-based processing).

**Certogo Process**:

**Marketing Consent Withdrawal**:
- Click "Unsubscribe" in email (immediate effect)
- Toggle off in account settings

**E-KYC Consent Withdrawal** 🔴:
- More complex (E-KYC already completed)
- Email privacy@certogo.com
- DPO explains consequences: "Withdrawing E-KYC consent means we cannot verify your identity for future sensitive operations (e.g., certificate issuance for regulated training). Your account may have limited functionality."
- If Data Subject confirms withdrawal:
  - Delete biometric data at E-KYC provider (request certificate)
  - Mark account as "E-KYC consent withdrawn" (limited functionality)

**SLA**: 7 days to process withdrawal

---

## 6. Data Subject Rights Request Handling (Summary) | การจัดการคำขอใช้สิทธิ

### 6.1 Request Channels | ช่องทางการขอใช้สิทธิ

Data Subjects can submit requests via:
1. **Email**: privacy@certogo.com (monitored by DPO)
2. **In-App**: Account Settings → Privacy → "Request My Data" / "Delete My Account"
3. **Website Form**: certogo.com/privacy-request
4. **Mail**: Certogo Co., Ltd., [Address], Attn: Data Protection Officer

### 6.2 Request Handling Workflow

```
Data Subject Request
         ↓
Customer Support receives → Forward to DPO (within 24 hours)
         ↓
DPO logs request in ISMS system (tracking number issued)
         ↓
Identity Verification (within 3 days)
         ↓
Eligibility Assessment (within 7 days)
         ↓
Execute Request (within 30 days total)
         ↓
Confirmation to Data Subject (email + tracking number)
```

### 6.3 Service Level Agreements (SLAs)

| Right | Response SLA | Notes |
|-------|-------------|-------|
| Right to Be Informed | Immediate (Privacy Notice always available) | - |
| Right of Access | 30 days | Free for 1st request/year |
| Right to Rectification | 30 days (self-service: immediate) | - |
| Right to Erasure 🔴 | 30 days | Biometric data: expedited if requested |
| Right to Data Portability | 30 days | - |
| Right to Object | 15 days (assessment), 30 days (implementation) | - |
| Right to Restrict Processing | 7 days (implementation), 30 days (resolution) | - |
| Right to Withdraw Consent | 7 days | Marketing: immediate |

**If SLA Cannot Be Met**:
- DPO notifies Data Subject with explanation and revised timeline (maximum extension: +30 days)
- Document reason for delay

### 6.4 Request Tracking

**DPO maintains register** (`/evidence/records/data-subject-requests.xlsx`):

| Columns | Description |
|---------|-------------|
| Request ID | Unique identifier (DSR-2024-001, DSR-2024-002, ...) |
| Date Received | YYYY-MM-DD |
| Data Subject Name | Name (anonymized in reports) |
| Request Type | Access / Erasure / Rectification / Object / ... |
| Status | Pending / In Progress / Completed / Rejected |
| Completion Date | YYYY-MM-DD |
| SLA Met | Yes / No (if No, document reason) |
| Notes | Free text |

**Quarterly Reporting**:
- DPO reports to CEO: Number of requests, SLA compliance %, common request types
- Identify process improvements

---

## 7. Consent Management | การจัดการความยินยอม

### 7.1 Consent Requirements (PDPA Section 19)

**Valid consent must be**:
- **Voluntary**: No coercion or negative consequences for refusal (exception: necessary for contract)
- **Specific**: Clear purpose stated (not bundled with unrelated purposes)
- **Informed**: Data Subject understands what they're consenting to
- **Unambiguous**: Clear affirmative action (not pre-ticked boxes or silence)

**Explicit Consent** (PDPA Section 26) 🔴:
- Required for Sensitive Personal Data (biometric data)
- Must be separate from general consent
- Clear warning about sensitivity of data

### 7.2 Certogo Consent Collection

**Account Registration**:
```
☐ I agree to the Terms of Service and Privacy Notice (required for account creation)
```
**Legal Basis**: Contract performance (PDPA Section 24(1))

**E-KYC Verification** 🔴:
```
☐ I explicitly consent to Certogo collecting and sharing my ID card image and
  facial image with Appman Co., Ltd. (our E-KYC provider) for the sole purpose
  of identity verification. This data is SENSITIVE PERSONAL DATA under PDPA
  Section 26. The biometric data will be deleted after 30 days.

  I understand I can withdraw this consent at any time by emailing privacy@certogo.com,
  but this may limit my account functionality.
```
**Legal Basis**: Explicit consent (PDPA Section 26)

**Marketing Communications**:
```
☐ (Optional) I consent to receiving marketing emails, SMS, and notifications about
  new courses, promotions, and updates from Certogo. I can unsubscribe anytime.
```
**Legal Basis**: Consent (PDPA Section 19)

**Consent Storage**:
- Timestamp of consent (ISO 8601 format)
- IP address (for audit trail)
- Consent text (exact wording shown to user)
- Consent version (if Privacy Notice updated, version number)

**Consent Withdrawal**:
- Easy mechanism (unsubscribe link, account settings toggle)
- Processed within 7 days
- Confirmation email sent

### 7.3 Consent for Minors (Under 20 in Thailand)

**PDPA Section 20**: Parental consent required for minors (under 20 years old).

**Certogo Approach**:
- Account registration requires age declaration
- If user indicates age < 20:
  - Request parental consent (parent email + verification link)
  - Parent receives email: "Your child [Name] is registering for Certogo. Click here to consent."
  - Account activated only after parental consent received
  - **E-KYC for minors**: Require parent's explicit consent (separate checkbox) 🔴

**Age Verification**:
- Self-declaration during registration (honor system for low-risk scenarios)
- For high-risk (E-KYC with biometric data): Verify age via ID card scan (if ID shows age < 20, require parental consent)

---

## 8. Third-Party Data Processors | ผู้ประมวลผลข้อมูลบุคคลที่สาม

### 8.1 Data Processor Requirements

**All data processors MUST**:
- Sign Data Processing Agreement (DPA) before processing Personal Data
- Comply with PDPA requirements (same level of protection as Certogo)
- Process data only on Certogo's instructions
- Implement appropriate security measures (encryption, access control)
- Notify Certogo of data breaches within 24 hours 🔴
- Assist with Data Subject rights requests
- Delete or return data upon termination

### 8.2 Current Data Processors

| Processor | Service | Data Processed | DPA Status | Review Frequency |
|-----------|---------|----------------|------------|------------------|
| **Appman Co., Ltd.** 🔴 | E-KYC identity verification | **Biometric data** (facial images, ID scans), ID card number, name | ✅ Signed | **Quarterly** |
| [Cloud Provider] | Infrastructure hosting | All Certogo data (encrypted) | ✅ Signed | Annual |
| [Email Service] | Transactional and marketing emails | Email addresses, names | ✅ Signed | Annual |

**DPA Template**: See Supplier Security Policy (POL-004) Appendix A

### 8.3 E-KYC Provider (Appman) - Specific Requirements 🔴

Given that Appman processes **Sensitive Personal Data** (biometric data), additional controls apply:

**Contractual Requirements** (DPA):
- ✅ **Purpose limitation**: Biometric data used ONLY for identity verification
- ✅ **Data retention**: Maximum 30 days, automated deletion
- ✅ **Data localization**: Biometric data stored in Thailand only (no cross-border transfer)
- ✅ **Sub-processor approval**: Appman must obtain Certogo's written consent before engaging sub-processors
- ✅ **Security**: ISO 27001 certified, AES-256 encryption, TLS 1.3, MFA, audit logs
- ✅ **Data breach notification**: Within 24 hours (vs. 72 hours for non-biometric)
- ✅ **Certificate of deletion**: Provided upon termination or upon request
- ✅ **Audit rights**: Certogo may audit Appman's biometric data handling (annually)

**Monitoring**:
- Quarterly security reviews (DPO + CISO)
- Annual ISO 27001 certificate validation
- Annual penetration test report review

**Data Subject Rights**:
- If Data Subject requests access to biometric data: Certogo forwards request to Appman (within 3 days)
- If Data Subject requests deletion of biometric data: Certogo instructs Appman to delete immediately (certificate provided)

### 8.4 Sub-Processors

**PDPA Section 27**: Data Processor may engage sub-processors only with Data Controller's consent.

**Certogo Requirement**:
- All sub-processors must be disclosed in DPA (Appendix: "List of Sub-Processors")
- Appman must notify Certogo 30 days before adding new sub-processors
- Certogo may object to new sub-processors (Appman must not engage if Certogo objects)
- Sub-processors must have same PDPA obligations (flow-down clauses in contracts)

---

## 9. Cross-Border Data Transfer | การส่งข้อมูลข้ามพรมแดน

### 9.1 PDPA Requirements (PDPA Section 28)

**Cross-border transfer allowed ONLY if**:
1. Destination country has adequate data protection standards (per PDPC whitelist), OR
2. Data Controller obtains explicit consent from Data Subject, OR
3. Transfer necessary for contract performance, OR
4. Standard contractual clauses approved by PDPC

### 9.2 Certogo Current Status

**Biometric Data** 🔴:
- ✅ **NO cross-border transfer** (stored in Thailand only at Appman's Thailand data center)
- ✅ Contractual requirement in DPA (data localization clause)

**Non-Biometric Personal Data**:
- ✅ Primary storage: Thailand (cloud provider's Thailand region)
- 🔶 Backups: May be replicated to ASEAN regions for disaster recovery (Singapore)
  - Legal Basis: Consent (disclosed in Privacy Notice)
  - Protection: Encrypted, same security standards

**Cloud Provider**:
- If cloud provider is global (AWS, Azure, GCP):
  - Certogo configures **Thailand region** for production data
  - Backups may go to **Singapore region** (ASEAN - similar PDPA-like laws)
  - Standard contractual clauses in cloud provider agreement

**Future Changes**:
- If cross-border transfer needed (e.g., new cloud provider outside ASEAN):
  - Conduct Data Protection Impact Assessment (DPIA)
  - Obtain PDPC-approved standard contractual clauses
  - Update Privacy Notice and obtain consent (if required)

---

## 10. Data Breach Response | การตอบสนองต่อการรั่วไหลของข้อมูล 🔴

### 10.1 PDPA Breach Notification Requirements (PDPA Section 37)

**Data Controller MUST notify**:
1. **Personal Data Protection Committee (PDPC)**: Within **72 hours** of discovery (if breach likely to affect rights and freedoms)
2. **Affected Data Subjects**: **Without undue delay** (if high risk to rights and freedoms)

**Penalties for Non-Compliance**:
- Failure to notify: Up to 1 million THB (PDPA Section 79)
- Negligent data breach: Up to 5 million THB or 5% of annual revenue (Section 41)

### 10.2 What Constitutes a "Data Breach"?

**Data Breach** = Unauthorized or unlawful access, collection, use, disclosure, alteration, or destruction of Personal Data.

**Examples**:
- 🔴 **Critical**: Biometric data breach (any amount), PII breach (> 1,000 records)
- 🟠 **High**: PII breach (100-1,000 records), unauthorized access to database
- 🟡 **Medium**: PII breach (< 100 records), accidental email sent to wrong recipient
- 🟢 **Low**: Suspected breach (investigated, no actual compromise)

### 10.3 Data Breach Response Procedure

**Phase 1: Detection and Reporting (Hour 0-1)**

1. **Incident Detection**:
   - Automated alerts (SIEM, IDS)
   - Employee report
   - Customer report
   - Third-party notification (E-KYC provider)

2. **Immediate Reporting**:
   - **ALL suspected breaches MUST be reported to CISO and DPO within 1 hour**
   - Report via: security@certogo.com, Slack #security-incidents, or phone [CISO number]

3. **Initial Triage**:
   - CISO classifies severity (Critical, High, Medium, Low)
   - Alert CEO if Critical (biometric data) or High

**Phase 2: Investigation and Containment (Hour 1-24)**

4. **Incident Team Activation**:
   - CISO (lead), DPO, CTO, Legal, affected department head
   - Create incident war room (physical or virtual)

5. **Investigation**:
   - Determine: What data was compromised? How many individuals? Root cause?
   - Review logs, interview personnel, analyze systems
   - **For biometric breach** 🔴: Immediately contact Appman, request detailed incident report

6. **Containment**:
   - Isolate affected systems (take offline if necessary)
   - Revoke compromised credentials
   - Block attacker access (firewall rules, IP blocking)
   - Preserve evidence (forensic imaging, log collection)

**Phase 3: PDPC and Data Subject Notification (Hour 24-72)**

7. **Breach Assessment** (by DPO + Legal):
   - **Does breach meet PDPC notification threshold?**
     - ✅ Yes, if: Biometric data compromised (any amount) 🔴
     - ✅ Yes, if: PII breach likely to affect rights and freedoms (> 100 records or sensitive context)
     - ❌ No, if: Minimal risk (e.g., encrypted data, no decryption key compromised)

8. **PDPC Notification** (if required) - Within 72 hours:
   - **Method**: Submit via PDPC online portal (https://www.pdpc.or.th) or email
   - **Content** (PDPA Section 37):
     - Description of breach (what happened, when, how)
     - Categories and approximate number of affected individuals
     - Categories and approximate number of Personal Data records
     - Likely consequences of breach
     - Measures taken or proposed to address breach
     - Contact point for more information (DPO name, email, phone)
   - **Approval**: CEO must approve PDPC notification before submission

9. **Data Subject Notification** (if high risk):
   - **Method**: Email to affected individuals (use secure channel if possible)
   - **Timing**: Without undue delay (ideally within 72 hours, no later than 7 days)
   - **Content**:
     - Clear description of breach (plain language, Thai and English)
     - Data that was compromised
     - Likely consequences (e.g., "Your email and name may be used for phishing attacks")
     - Remediation steps (e.g., "Change your password immediately", "Monitor your accounts")
     - Certogo's response actions (what we're doing to fix it)
     - Contact information for questions (DPO email, phone, support hotline)
     - Apology and commitment to prevent future breaches

   **Template Email** (Biometric Breach) 🔴:
   ```
   Subject: [URGENT] Security Incident Notification - Certogo

   Dear [Name],

   We are writing to inform you of a security incident that may have affected your
   personal data, specifically your biometric data (facial image and ID card scan)
   processed during E-KYC identity verification.

   **What Happened**: [Brief description, e.g., "Our E-KYC provider, Appman,
   experienced a data breach on [Date]..."]

   **What Data Was Affected**: Your facial image and ID card scan submitted for
   identity verification on [Date].

   **What We Are Doing**:
   - We have confirmed that the breach has been contained as of [Date].
   - We are working with Appman to ensure all affected biometric data is immediately deleted.
   - We have engaged cybersecurity experts to investigate and prevent future incidents.

   **What You Should Do**:
   - Be vigilant for potential identity fraud (monitor your financial accounts).
   - If you receive suspicious communications claiming to be from Certogo, verify
     by contacting us directly at privacy@certogo.com.

   **Your Rights**: You have the right to file a complaint with the Personal Data
   Protection Committee (PDPC) at https://www.pdpc.or.th if you believe your rights
   have been violated.

   We sincerely apologize for this incident. Protecting your personal data is our
   highest priority.

   If you have any questions, please contact our Data Protection Officer:
   - Email: privacy@certogo.com
   - Phone: [DPO Phone]

   Sincerely,
   [CEO Name]
   Chief Executive Officer
   Certogo Co., Ltd.
   ```

10. **Public Disclosure** (if warranted):
    - For major breaches (> 10,000 affected individuals or biometric data): Issue public statement
    - Post on Certogo website: certogo.com/security-incident
    - Coordinate with PR team (messaging, FAQ)

**Phase 4: Remediation and Recovery (Day 3-30)**

11. **Remediation**:
    - Fix root cause (patch vulnerability, improve controls)
    - Enhance monitoring (add new detection rules)
    - Review and update security controls

12. **Regulatory Cooperation**:
    - Respond to PDPC inquiries (if any)
    - Provide progress updates to PDPC

13. **Customer Support**:
    - Set up dedicated hotline/email for affected individuals
    - Track and respond to inquiries (SLA: 24 hours)

**Phase 5: Post-Incident Review (Day 30-60)**

14. **Lessons Learned**:
    - Conduct post-incident review meeting (CISO, DPO, CEO, incident team)
    - Document: What went well, what didn't, root cause, improvements needed

15. **Policy and Procedure Updates**:
    - Update security controls (preventive and detective)
    - Update incident response procedure (if gaps identified)
    - Update PDPA Compliance Policy (if needed)

16. **Affected Individuals Follow-Up**:
    - Send follow-up email (30 days after): "The incident has been fully resolved. Here's what we've done..."
    - Offer support (e.g., credit monitoring for identity theft risk - if applicable)

### 10.4 Third-Party Breach (E-KYC Provider Incident) 🔴

**If Appman notifies Certogo of biometric data breach**:

**Immediate Actions** (Hour 0-1):
- CISO and DPO alerted
- CEO alerted (biometric data = Critical)
- Incident logged

**Investigation** (Hour 1-24):
- Request detailed incident report from Appman (within 6 hours)
- Determine: Was Certogo customer data affected? How many individuals?
- Assess if breach was due to Appman's negligence (DPA violation)

**PDPC Notification** (Hour 24-72):
- **Certogo is STILL responsible** as Data Controller (cannot delegate PDPC notification to Appman)
- Notify PDPC within 72 hours (even though breach occurred at processor)
- Content: "Our data processor, Appman Co., Ltd., experienced a breach affecting [X] individuals' biometric data..."

**Data Subject Notification**:
- Same as above (Certogo sends notification, not Appman)

**Contractual Remedies**:
- Review DPA indemnification clause (Appman may be liable for damages)
- Assess if breach warrants termination of contract (if due to gross negligence)
- Consider switching E-KYC providers (initiate 20-week migration procedure)

---

## 11. Data Protection Impact Assessment (DPIA) | การประเมินผลกระทบด้านการคุ้มครองข้อมูล 🔴

### 11.1 When DPIA is Required (PDPA Section 37/1)

DPIA is mandatory BEFORE processing that is "likely to result in high risk to rights and freedoms", such as:
- **Sensitive Personal Data processing** (biometric data) 🔴
- Large-scale systematic monitoring
- Automated decision-making with legal/significant effects
- Processing of vulnerable individuals' data (children, elderly)

### 11.2 Certogo DPIA Scenarios

**MANDATORY DPIA**:
1. **E-KYC Biometric Data Processing** 🔴 (already conducted)
2. **New E-KYC provider onboarding** (before switching from Appman)
3. **New feature using biometric data** (e.g., facial recognition for course access)
4. **Profiling or automated decision-making** (if implemented)

**OPTIONAL DPIA** (recommended):
- Major system architecture changes (new cloud provider)
- Large-scale marketing campaigns (bulk PII processing)

### 11.3 DPIA Process

**Step 1: Describe Processing Activity**:
- What: E-KYC identity verification using facial recognition and ID card OCR
- Why: Verify user identity for compliance training (regulated industries require verified identity)
- How: User uploads ID card image and selfie → Appman processes → Returns Pass/Fail
- Data: Biometric data (facial image, ID card scan), ID card number, name

**Step 2: Assess Necessity and Proportionality**:
- Is processing necessary for the purpose? Yes (identity verification requires biometric comparison)
- Is there a less intrusive alternative? No (manual verification is less secure and scalable)

**Step 3: Identify Risks**:
- **Risk 1**: Biometric data breach at E-KYC provider
  - Likelihood: Low (Appman is ISO 27001 certified, encrypted storage)
  - Impact: Critical (PDPA Section 26 violation, reputational damage, PDPC fines)
  - Risk Level: High

- **Risk 2**: Unauthorized use of biometric data (purpose creep)
  - Likelihood: Low (contractual purpose limitation with Appman)
  - Impact: High (PDPA violation, loss of trust)
  - Risk Level: Medium

- **Risk 3**: Biometric data retention beyond 30 days
  - Likelihood: Low (automated deletion, quarterly audits)
  - Impact: High (PDPA Section 26 violation)
  - Risk Level: Medium

**Step 4: Identify Mitigation Measures**:
- **For Risk 1** (Breach):
  - Appman ISO 27001 certified
  - DPA with security requirements (encryption, access control, breach notification)
  - Quarterly security reviews
  - Cyber insurance (covers third-party breaches)

- **For Risk 2** (Unauthorized Use):
  - DPA with purpose limitation clause
  - Annual review of Appman's data usage (audit logs)
  - No sub-processors without Certogo's approval

- **For Risk 3** (Retention):
  - Automated deletion after 30 days (contractual requirement)
  - Quarterly verification (certificate of deletion requested)
  - DPO audit of Appman's deletion logs

**Step 5: Residual Risk Assessment**:
- Risk 1: High → Medium (after mitigations)
- Risk 2: Medium → Low
- Risk 3: Medium → Low

**Step 6: Decision**:
- ✅ Proceed with processing (residual risks acceptable)
- ❌ Do not proceed (risks too high, even after mitigations) - N/A

**Step 7: Approval**:
- DPO prepares DPIA report
- CEO reviews and approves
- If high residual risk remains, may consult PDPC (optional, not mandatory in Thailand PDPA)

**Step 8: Documentation**:
- DPIA report filed in `/evidence/records/dpia/`
- Reviewed annually or upon significant changes

**DPIA Template**: Available at `/standards/iso27001/06-templates/dpia-template.md` (to be created)

---

## 12. Record of Processing Activities (ROPA) | บันทึกกิจกรรมการประมวลผลข้อมูล

### 12.1 PDPA Requirement

PDPA Section 39: Data Controllers must maintain records of processing activities.

### 12.2 Certogo ROPA

**Maintained by**: DPO
**Location**: `/evidence/records/ropa.xlsx`
**Update Frequency**: Quarterly (or whenever new processing activity added)

**ROPA Contents** (per PDPA Section 39):

| Column | Description | Example |
|--------|-------------|---------|
| **Processing Activity** | Name of processing | "E-KYC Identity Verification" |
| **Purpose** | Why processing occurs | "Verify user identity for regulated compliance training" |
| **Legal Basis** | PDPA justification | "Explicit consent (PDPA Section 26)" |
| **Data Categories** | Types of data | "Biometric data (facial image, ID scan), ID card number, name" |
| **Data Subjects** | Who the data is about | "Certogo B2C users (adults 20+)" |
| **Recipients** | Who receives data | "Appman Co., Ltd. (E-KYC processor)" |
| **Retention Period** | How long data is kept | "30 days (biometric data at Appman), 90 days (verification result at Certogo)" |
| **Security Measures** | How data is protected | "AES-256 encryption at rest, TLS 1.3 in transit, ISO 27001 certified processor" |
| **Cross-Border Transfer** | Data sent abroad? | "No - Thailand only" |
| **DPIA Required** | High-risk processing? | "Yes - DPIA conducted on [Date]" |
| **Last Updated** | ROPA entry update date | "YYYY-MM-DD" |

**Additional Processing Activities to Document**:
1. E-KYC Identity Verification (above)
2. User Account Management (registration, login)
3. Course Delivery and Progress Tracking
4. Certificate Issuance
5. Marketing Communications
6. Customer Support
7. Employee Data Processing (HR)

---

## 13. Training and Awareness | การฝึกอบรมและการสร้างการรับรู้

### 13.1 Mandatory PDPA Training

**Tier 2: PDPA & Biometric Data Handling** 🔴 (from A.6 People Controls)

**Mandatory for**: All employees with access to Personal Data (Developers, DevOps, Security Team, Customer Support, HR, Marketing)

**Frequency**: Annually + upon hire

**Duration**: 2 hours

**Topics**:
1. **PDPA Overview**:
   - What is PDPA and why it matters
   - Personal Data vs. Sensitive Personal Data
   - Penalties for violations (up to 5% revenue)

2. **Data Processing Principles**:
   - Purpose limitation, data minimization, accuracy, retention, security

3. **Biometric Data Handling** 🔴 **CRITICAL**:
   - What is biometric data? (facial images, fingerprints, ID card scans)
   - Why is it highly sensitive? (PDPA Section 26)
   - **Certogo's E-KYC process**:
     - Customer uploads ID card and selfie
     - Appman processes and verifies
     - Certogo receives only verification result (not raw biometric data)
   - **Employee responsibilities**:
     - Never access biometric data directly (stored at Appman)
     - If you see biometric data in logs, report immediately to CISO + DPO
     - Do not screenshot or copy biometric data
   - **Data retention**: Biometric data deleted after 30 days

4. **Data Subject Rights**:
   - 8 rights (access, erasure, rectification, etc.)
   - How to handle requests (forward to DPO within 24 hours)
   - SLAs (30 days for most requests)

5. **Consent Management**:
   - How to obtain valid consent (specific, informed, unambiguous)
   - Explicit consent for biometric data
   - Consent withdrawal (easy opt-out)

6. **Data Breach Reporting**:
   - What constitutes a breach
   - Reporting requirement: Within 1 hour to CISO + DPO
   - Penalties for failure to report

7. **Third-Party Data Sharing**:
   - Never share Personal Data with third parties without DPA
   - E-KYC provider (Appman) has DPA in place

8. **Practical Scenarios** (Quiz):
   - Scenario 1: Customer asks to delete their account → Action?
   - Scenario 2: You accidentally see biometric data in logs → Action?
   - Scenario 3: Marketing wants to use customer emails for campaign → Action?

**Training Delivery**:
- Online course (LMS platform - Certogo's own)
- In-person workshop (for new hires)

**Assessment**:
- Quiz at end of training (minimum 80% pass rate)
- Failed quiz: Re-take training

**Training Records**:
- HR maintains records (who, when, score)
- DPO reviews quarterly (ensure 100% completion)

### 13.2 Executive Briefing

**Audience**: CEO, CISO, CTO, DPO, CFO, Legal

**Frequency**: Annually + upon significant PDPA regulatory changes

**Topics**:
- PDPA compliance status update
- Data breach trends and preparedness
- DPIA results for new high-risk processing
- Budget needs for PDPA program

---

## 14. Compliance Monitoring and Audits | การตรวจสอบและการตรวจสอบความสอดคล้อง

### 14.1 Internal PDPA Audits

**Frequency**: Quarterly (focused), Annually (comprehensive)

**Quarterly Audits** (by DPO):
- Review Data Subject rights requests (SLA compliance, trends)
- Verify biometric data deletion at Appman (request quarterly report or certificate)
- Check consent records (valid, documented)
- Review ROPA updates (any new processing activities?)

**Annual Comprehensive Audit** (by independent internal auditor):
- Review ALL PDPA requirements (Sections 19-41)
- Test data breach response (tabletop exercise)
- Review DPAs with all processors
- Verify training completion (100% of employees)
- Check DPIA for high-risk processing
- Assess PDPC notification readiness

**Audit Report**:
- Findings documented (compliant, non-compliant, areas for improvement)
- Action plans for non-compliance (owner, deadline)
- Submitted to CEO and Board

### 14.2 External Audits

**ISO 27001 Certification Audit**:
- Includes PDPA compliance review (A.5.34 Privacy and protection of PII)
- Annually (surveillance audit)

**PDPC Audit** (if triggered):
- PDPC may audit Certogo if complaint filed or breach reported
- DPO prepares documentation (ROPA, DPIAs, policies, consent records)
- Cooperate fully with PDPC

### 14.3 Key Performance Indicators (KPIs)

| KPI | Target | Measurement |
|-----|--------|-------------|
| **Data Subject rights request SLA compliance** | 100% | Monthly |
| **PDPA training completion rate** | 100% | Quarterly |
| **Biometric data deletion compliance** (Appman) | 100% within 30 days | Quarterly verification |
| **Data breaches (biometric data)** | 0 | Continuous |
| **PDPC complaints or fines** | 0 | Continuous |
| **DPA coverage** (all processors have signed DPA) | 100% | Quarterly |
| **Consent withdrawal processing time** | ≤ 7 days (average) | Monthly |

**KPI Review**: DPO reports to CEO quarterly

---

## 15. Policy Review and Updates | การทบทวนและปรับปรุงนโยบาย

### 15.1 Review Schedule

This policy shall be reviewed:
- **Annually** (by DPO, approved by CEO)
- **Ad-hoc** when:
  - PDPA regulations updated (PDPC issues new guidance)
  - Major data breach occurs
  - New high-risk processing activity (requires DPIA)
  - E-KYC provider change 🔴
  - Internal/external audit findings require policy updates

### 15.2 Version Control

| Version | Date | Author | Changes | Approved By |
|---------|------|--------|---------|-------------|
| 1.0 | [Date] | DPO | Initial version | CEO |
| | | | | |

**Change History**: `/standards/iso27001/02-policies/pdpa-compliance-policy-changelog.md`

---

## 16. Related Documents | เอกสารที่เกี่ยวข้อง

- **Information Security Policy** (POL-001)
- **Supplier Security Policy** (POL-004) - DPA template
- **Incident Response Policy** (POL-005)
- **Privacy Notice** (public-facing) - certogo.com/privacy
- **Terms of Service** - certogo.com/terms
- **Data Processing Agreement Template** - POL-004 Appendix A
- **Data Subject Rights Request Form** - certogo.com/privacy-request
- **DPIA Template** - `/standards/iso27001/06-templates/dpia-template.md`
- **Record of Processing Activities (ROPA)** - `/evidence/records/ropa.xlsx`

---

## 17. Contact Information | ข้อมูลการติดต่อ

**Data Protection Officer (DPO)**:
- Name: [DPO Name]
- Email: privacy@certogo.com
- Phone: [DPO Phone]
- Office: [Location]

**For Data Subject Rights Requests**:
- Email: privacy@certogo.com
- Web Form: certogo.com/privacy-request
- Mail: Certogo Co., Ltd., [Address], Attn: Data Protection Officer

**For Data Breach Reporting** (Employees):
- Email: security@certogo.com (CISO)
- CC: privacy@certogo.com (DPO)
- Slack: #security-incidents
- Phone: [CISO Phone] (24/7)

**Personal Data Protection Committee (PDPC)**:
- Website: https://www.pdpc.or.th
- Phone: 02-141-6993
- Email: pdpc@mdes.go.th

---

## Approval and Acknowledgment | การอนุมัติและการรับทราบ

### Executive Approval

**CEO Signature** | **ลายเซ็น CEO**:

```
_________________________________________
[CEO Name]
Chief Executive Officer
Certogo Co., Ltd.

Date: _______________
```

**DPO Endorsement** | **ลายเซ็น DPO**:

```
_________________________________________
[DPO Name]
Data Protection Officer
Certogo Co., Ltd.

Date: _______________
```

### Employee Acknowledgment

**I acknowledge that I have read, understood, and agree to comply with this PDPA Compliance Policy.**

**ข้าพเจ้ารับทราบว่าได้อ่าน เข้าใจ และตกลงที่จะปฏิบัติตามนโยบายการปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคลนี้**

```
Employee Name (Print): _________________________________

Employee Signature: ____________________________________

Date: _______________
```

---

**END OF POLICY | สิ้นสุดนโยบาย**

**Document Classification**: Internal Use Only
**Version**: 1.0
**Last Updated**: [Date]
**Next Review**: [Date + 1 year]
