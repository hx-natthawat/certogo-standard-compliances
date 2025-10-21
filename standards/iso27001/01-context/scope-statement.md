# ISMS Scope Statement | ขอบเขตของระบบการจัดการความมั่นคงปลอดภัยสารสนเทศ

**Document Control | การควบคุมเอกสาร**

| Field | Value |
|-------|-------|
| **Document ID** | SCOPE-001 |
| **Version** | 1.0 |
| **Effective Date** | [To be filled - วันที่มีผลบังคับใช้] |
| **Review Date** | [Annual - ทบทวนทุกปี] |
| **Document Owner** | Chief Information Security Officer (CISO) |
| **Approved By** | Chief Executive Officer (CEO) |
| **Classification** | Internal Use Only - ใช้ภายในองค์กรเท่านั้น |
| **Related Standards** | ISO 27001:2022 Clause 4.3 |

---

## 1. Purpose | วัตถุประสงค์

This document defines the **scope** of Certogo's Information Security Management System (ISMS) in accordance with ISO 27001:2022 Clause 4.3. The scope establishes the boundaries and applicability of the ISMS, including:

- Business units and locations covered
- Information assets and systems protected
- Third-party services integrated (particularly E-KYC provider)
- Exclusions and limitations

**Thai | ไทย**: เอกสารนี้กำหนดขอบเขตของระบบการจัดการความมั่นคงปลอดภัยสารสนเทศ (ISMS) ของ Certogo ตามข้อกำหนด ISO 27001:2022 ข้อ 4.3

---

## 2. Organization Overview | ภาพรวมองค์กร

### 2.1 Legal Entity | นิติบุคคล

- **Organization Name | ชื่อองค์กร**: Certogo Co., Ltd. | บริษัท Certogo จำกัด
- **Business Registration | ทะเบียนธุรกิจ**: [Registration Number]
- **Industry Sector | อุตสาหกรรม**: Education Technology (EdTech) - Learning Management Systems
- **Business Type | ประเภทธุรกิจ**: B2B/B2C SaaS and PaaS provider

### 2.2 Business Description | ลักษณะธุรกิจ

Certogo operates a **cloud-based Learning Management System (LMS)** that provides:

**For B2B Customers (Organizations)**:
- Compliance training management (regulatory, occupational safety, industry-specific)
- Non-compliance training (soft skills, technical skills, onboarding)
- Certificate issuance and tracking
- Reporting and analytics
- Multi-tenant SaaS platform with white-labeling capabilities

**For B2C Users (Individual Learners)**:
- Direct access to training courses and certifications
- Self-paced learning
- E-KYC identity verification for regulated training (requires verified identity)

**Thai | ไทย**: Certogo ให้บริการระบบการจัดการการเรียนรู้บนคลาวด์ (LMS) สำหรับการฝึกอบรมทั้งด้านการปฏิบัติตามกฎระเบียบและทั่วไป พร้อมระบบยืนยันตัวตน E-KYC

### 2.3 Customer Base | ฐานลูกค้า

- **B2B Customers**: [Number] organizations across Thailand and ASEAN
  - Industry sectors: Banking, Healthcare, Manufacturing, Government, Energy
  - Typical size: 50-10,000 employees per organization

- **B2C Users**: [Number] individual learners
  - Primarily in Thailand (95%)
  - Age range: 18-65 years

---

## 3. ISMS Scope | ขอบเขต ISMS

### 3.1 In Scope | อยู่ในขอบเขต

The ISMS covers the following:

#### 3.1.1 Business Functions | หน้าที่ทางธุรกิจ

✅ **Core Business Functions**:
- Learning Management System (LMS) platform operation
- Course content management and delivery
- User authentication and authorization
- Certificate issuance and verification
- **E-KYC identity verification integration** 🔴 (via third-party provider)
- Customer support and help desk
- Billing and subscription management

✅ **Supporting Functions**:
- IT infrastructure management (cloud hosting, databases, networking)
- Software development and DevOps
- Information security operations and monitoring
- Data protection and privacy (PDPA compliance)
- Third-party supplier management (particularly E-KYC provider) 🔴
- Incident response and business continuity

❌ **Out of Scope**:
- HR functions unrelated to IT systems (payroll, benefits - unless PII processing)
- Marketing campaigns (unless involving customer PII)
- Physical office facilities (covered under separate facilities management - not ISMS)
- Customer-owned infrastructure (for PaaS deployments where customer manages infrastructure)

#### 3.1.2 Information Assets | สินทรัพย์สารสนเทศ

✅ **Data Assets**:
- **Customer data**: Organization details, user profiles, course enrollments, certificates
- **Personal Data (PII)**: Names, email addresses, phone numbers, ID card numbers
- **🔴 Sensitive Personal Data**: Biometric data (facial images, ID card scans) - **processed by E-KYC provider, NOT stored by Certogo**
- **Business confidential data**: Course content, pricing information, contracts
- **Intellectual property**: Source code, system architecture, proprietary algorithms
- **Transaction data**: Billing records, subscription histories
- **Audit and compliance data**: Logs, security records, PDPA records

✅ **System Assets**:
- LMS web application (frontend and backend)
- Mobile applications (iOS, Android)
- APIs (RESTful, GraphQL)
- Databases (PostgreSQL, MongoDB, Redis)
- File storage systems (S3, Azure Blob Storage)
- Authentication services (SSO, OAuth 2.0)
- **E-KYC integration APIs** 🔴
- Monitoring and logging systems (SIEM, APM)
- Development and CI/CD pipelines
- Backup and disaster recovery systems

✅ **Infrastructure Assets**:
- Cloud infrastructure (AWS, Azure, or GCP - specify provider)
  - **Primary region**: Thailand (Bangkok) for production data
  - **DR region**: Singapore (for disaster recovery backups)
- Network infrastructure (VPN, firewalls, load balancers)
- Development, staging, and production environments
- Employee workstations (laptops, desktops) with access to production

❌ **Out of Scope**:
- Customer-owned systems (for PaaS deployments)
- Third-party tools used only for marketing (not handling customer data)
- Personal devices without company data access

#### 3.1.3 Locations | สถานที่

✅ **Physical Locations**:
- **Headquarters**: [Address], Bangkok, Thailand
- **Data Centers**: Cloud provider data centers (Thailand region - Bangkok)
- **Disaster Recovery Site**: Cloud provider data centers (Singapore region)
- **Employee Remote Work Locations**: Thailand-based employees (work-from-home)

❌ **Out of Scope**:
- Customer locations (responsibility of customer for PaaS deployments)

#### 3.1.4 People | บุคลากร

✅ **Personnel Covered**:
- All Certogo employees ([Number] total):
  - Executive team (CEO, CTO, CISO, DPO, CFO)
  - Engineering team (developers, DevOps, QA)
  - IT operations team
  - Security team
  - Customer support team
  - Sales and account management
  - HR and administration
- Contractors with access to Certogo systems or customer data
- Third-party service providers with data access (E-KYC provider, cloud hosting, etc.)

❌ **Out of Scope**:
- Customer employees (B2B organizations) - managed by customer's own ISMS
- Individual learners (B2C users) - covered as data subjects, not as personnel

#### 3.1.5 Third-Party Services | บริการบุคคลที่สาม

✅ **Critical Third-Party Services** (covered under Supplier Security Policy):

1. **🔴 E-KYC Provider (Current: Appman Co., Ltd.)**:
   - Service: Digital identity verification (facial recognition, liveness detection, ID card OCR)
   - Data Processed: **Biometric data** (facial images, ID card scans) - PDPA Section 26 sensitive data
   - Integration: API-based, real-time verification
   - **CRITICAL**: E-KYC provider may change in the future - see 20-week migration procedure (A.5.22)

2. **Cloud Infrastructure Provider** ([AWS/Azure/GCP - specify]):
   - Service: IaaS (compute, storage, networking, databases)
   - Data Processed: All Certogo data (encrypted)
   - Region: Thailand (primary), Singapore (DR)

3. **Email Service Provider** ([Provider name]):
   - Service: Transactional emails (account notifications, password resets, certificates)
   - Data Processed: Email addresses, names

4. **Customer Support Platform** ([Provider name - if applicable]):
   - Service: Help desk ticketing, live chat
   - Data Processed: Customer names, emails, support request details

5. **Payment Gateway** ([Provider name - if applicable]):
   - Service: Subscription billing and payment processing
   - Data Processed: Payment card information (tokenized), billing details

**Supplier Security Requirements**:
- All Critical suppliers MUST sign Data Processing Agreements (DPAs)
- E-KYC provider MUST be ISO 27001 certified 🔴
- All suppliers subject to security assessments (see Supplier Security Policy POL-004)

❌ **Out of Scope**:
- Third-party services NOT handling customer data (e.g., marketing analytics tools with anonymized data only)

---

## 4. ISMS Boundaries | ขอบเขตของ ISMS

### 4.1 Geographical Boundaries | ขอบเขตทางภูมิศาสตร์

**Primary Operating Region**: Thailand

**Data Residency**:
- **Production data**: Thailand only (Bangkok region)
- **🔴 Biometric data**: Thailand ONLY (no cross-border transfer - PDPA requirement)
- **Disaster recovery backups**: Singapore (encrypted, ASEAN region)

**Reason for Thailand Data Residency** 🔴:
- PDPA Section 28 requires explicit consent or adequate protection for cross-border data transfer
- Biometric data (PDPA Section 26) is highly sensitive - Thailand-only storage minimizes compliance risk
- Customer expectations (Thai organizations prefer local data storage)

### 4.2 Organizational Boundaries | ขอบเขตขององค์กร

**Legal Entity**: Certogo Co., Ltd. only

**Departments Included**:
- All departments (no exclusions)

**Shared Responsibility** 🔄:
- **E-KYC Provider (Appman)**: Processes and stores biometric data on Certogo's behalf
  - Appman is a Data Processor under PDPA
  - Certogo is the Data Controller (ultimately responsible)
  - DPA defines security obligations

### 4.3 Technology Boundaries | ขอบเขตเทคโนโลยี

**Included Technologies**:
- All systems handling, processing, or storing customer data
- All systems supporting business operations (LMS platform, APIs, databases)
- All development, staging, and production environments
- All employee devices with access to production systems or customer data

**Excluded Technologies**:
- Marketing-only tools (no customer PII)
- Personal employee devices WITHOUT company data access
- Customer-owned infrastructure (PaaS deployments)

### 4.4 Process Boundaries | ขอบเขตกระบวนการ

**Included Processes**:
- **All stages of data lifecycle**: Collection → Storage → Use → Disclosure → Deletion
- **E-KYC process** 🔴:
  1. User initiates E-KYC verification (uploads ID card + selfie)
  2. Certogo sends request to E-KYC provider API
  3. E-KYC provider processes biometric data
  4. Certogo receives verification result (Pass/Fail) - NOT raw biometric data
  5. E-KYC provider deletes biometric data after 30 days
- **Software development lifecycle** (SDLC): Requirements → Design → Development → Testing → Deployment → Maintenance
- **Incident response**: Detection → Containment → Eradication → Recovery → Lessons Learned
- **Supplier management**: Selection → Onboarding → Monitoring → Offboarding (including E-KYC provider change procedure)

**Excluded Processes**:
- Customer training content creation (responsibility of customer or Certogo's content team - not ISMS unless involving sensitive data)

---

## 5. Regulatory and Legal Requirements | ข้อกำหนดทางกฎหมายและกฎระเบียบ

The ISMS is designed to ensure compliance with:

### 5.1 Thailand Regulations | กฎหมายไทย

- **🔴 Personal Data Protection Act B.E. 2562 (2019) - PDPA**:
  - Section 26: Sensitive Personal Data (biometric data)
  - Section 37: Data breach notification (72 hours to PDPC)
  - Section 40: Data Protection Officer (DPO) appointment
  - Penalties: Up to 5 million THB or 5% of annual revenue

- **Electronic Transactions Act B.E. 2544 (2001)**:
  - Digital signatures and electronic records

- **Computer Crime Act B.E. 2550 (2007)**:
  - Unauthorized access to computer systems
  - Data security requirements

### 5.2 International Standards | มาตรฐานสากล

- **ISO/IEC 27001:2022**: Information Security Management Systems (target certification)
- **ISO/IEC 27002:2022**: Information Security Controls (implementation guide)
- **ISO/IEC 27005:2022**: Information Security Risk Management

### 5.3 Contractual Obligations | ข้อผูกพันตามสัญญา

- **Data Processing Agreement (DPA) with E-KYC provider** 🔴:
  - Biometric data retention: Maximum 30 days
  - Data localization: Thailand only
  - Security requirements: ISO 27001 certification, AES-256 encryption, TLS 1.3
  - Breach notification: Within 24 hours
  - Certificate of deletion upon data deletion

- **Customer contracts (SLAs)**:
  - Availability: ≥ 99.5% uptime
  - Data protection: Encryption at rest and in transit
  - Incident notification: Critical incidents within 24 hours

---

## 6. Exclusions and Justifications | ข้อยกเว้นและเหตุผล

The following are **explicitly excluded** from the ISMS scope:

### 6.1 Physical Security of Office Premises

**Exclusion**: Physical access control to Certogo offices (badge systems, security guards, CCTV)

**Justification**:
- Physical security is managed by building management (rented office space)
- No production systems or customer data stored at office premises (100% cloud-hosted)
- ISO 27001 A.7 Physical Controls (14 controls) are NOT APPLICABLE for cloud-only operations

**Risk Mitigation**:
- Clear desk and clear screen policy enforced
- Visitor management procedures (sign-in, escort)
- Employee devices encrypted with full-disk encryption (FDE)

### 6.2 Customer-Owned Infrastructure (PaaS Deployments)

**Exclusion**: Infrastructure managed by B2B customers for PaaS (Platform-as-a-Service) deployments

**Justification**:
- Customer has administrative control over their infrastructure
- Certogo provides software platform only (application layer)
- Security responsibility is shared: Certogo (application security), Customer (infrastructure security)

**Boundary Definition**:
- Certogo responsibility: Application code, database schema, API security
- Customer responsibility: Cloud account, network configuration, OS patching

### 6.3 Personal Devices Without Company Data Access

**Exclusion**: Employee personal devices (phones, laptops, tablets) that do NOT have access to Certogo systems or customer data

**Justification**:
- No company data stored or accessed on personal devices
- BYOD (Bring Your Own Device) is NOT permitted for production access
- Company-issued devices required for all roles with data access

**Risk Mitigation**:
- Clear policy: Personal devices prohibited for work purposes
- VPN access restricted to company-issued devices only
- Multi-factor authentication (MFA) required for all production access

---

## 7. Interfaces with External Parties | การเชื่อมต่อกับบุคคลภายนอก

### 7.1 E-KYC Provider (Current: Appman Co., Ltd.) 🔴

**Interface Type**: API-based integration (RESTful APIs over HTTPS)

**Data Flow**:
1. **Certogo → E-KYC Provider**:
   - Inputs: ID card image, selfie (facial image), user consent timestamp
   - Protocol: HTTPS (TLS 1.3)
   - Authentication: OAuth 2.0 + JWT (API key rotated every 90 days)

2. **E-KYC Provider → Certogo**:
   - Output: Verification result (Pass/Fail), confidence score, match percentage
   - **Certogo does NOT receive raw biometric data** 🔴
   - Protocol: HTTPS (TLS 1.3)

**Security Controls**:
- API rate limiting (prevent abuse)
- Request/response logging (excluding biometric data)
- Monitoring and alerting (SLA: 99% availability)

**Data Processing Agreement (DPA)**:
- Appman acts as Data Processor
- Certogo acts as Data Controller
- Biometric data retention: 30 days maximum
- Data localization: Thailand only
- Certificate of deletion provided upon data deletion

**Provider Changeability** 🔴:
- See 20-week migration procedure: `/standards/iso27001/05-annex-a-controls/A.5-organizational-controls.md` Section A.5.22
- Certogo maintains capability to switch E-KYC providers if business or security requirements change

### 7.2 Cloud Infrastructure Provider

**Interface Type**: Cloud management console (web UI) + CLI + APIs

**Data Flow**:
- Certogo uploads encrypted data to cloud storage
- Cloud provider provides compute, storage, networking, and database services
- No direct access to data by cloud provider (encryption keys managed by Certogo)

**Security Controls**:
- Infrastructure-as-Code (IaC) for reproducible deployments
- Principle of least privilege (IAM roles)
- Cloud provider security certifications reviewed annually (ISO 27001, SOC 2)

### 7.3 B2B Customer Organizations

**Interface Type**: Web application (browser), APIs (for integrations), SSO (Single Sign-On)

**Data Flow**:
- Customers upload training content (courses, videos, documents)
- Customers manage their users (employees)
- Certogo processes user data and provides training delivery

**Security Controls**:
- Multi-tenant isolation (customer data segregated)
- Customer-specific encryption keys (for enterprise customers)
- SSO integration (SAML 2.0, OAuth 2.0)

### 7.4 B2C Individual Learners

**Interface Type**: Web application (browser), mobile apps (iOS, Android)

**Data Flow**:
- Users create accounts, enroll in courses, complete training
- **Users undergo E-KYC verification** (for regulated training requiring identity verification) 🔴

**Security Controls**:
- User authentication (email/password + optional MFA)
- Session management (timeout after 30 minutes of inactivity)
- Personal data minimization (collect only necessary data)

---

## 8. Dependencies and Critical Success Factors | การพึ่งพาและปัจจัยสำคัญต่อความสำเร็จ

### 8.1 Dependencies | การพึ่งพา

**Critical Dependencies** that could impact ISMS effectiveness:

1. **🔴 E-KYC Provider (Appman) Availability**:
   - If E-KYC provider is unavailable, identity verification fails
   - Impact: B2C users cannot complete E-KYC verification for regulated training
   - Mitigation: SLA monitoring (99% availability), incident escalation procedures, **provider change capability** (20-week migration)

2. **Cloud Infrastructure Provider Availability**:
   - If cloud provider has outage, LMS platform is unavailable
   - Impact: Business disruption for all customers
   - Mitigation: Multi-AZ deployment, disaster recovery site (Singapore), RTO < 4 hours

3. **Internet Connectivity**:
   - Cloud-based platform requires internet access
   - Impact: Users cannot access LMS during internet outage
   - Mitigation: Cloud provider guarantees (99.99% network uptime), multiple ISPs

4. **Third-Party Security Posture**:
   - If E-KYC provider or cloud provider is breached, Certogo customer data may be compromised
   - Impact: PDPA violations, reputational damage, customer churn
   - Mitigation: Supplier security assessments (ISO 27001 certification required), quarterly reviews, cyber insurance

### 8.2 Critical Success Factors | ปัจจัยสำคัญต่อความสำเร็จ

**Factors essential for ISMS success**:

1. **Executive Commitment**:
   - CEO approval of ISMS policy and resource allocation
   - CISO empowered to enforce security controls
   - DPO supported in PDPA compliance activities

2. **Employee Awareness**:
   - 100% completion of security awareness training (annually)
   - **PDPA and biometric data handling training** for roles with PII access 🔴
   - Culture of security (report incidents, follow policies)

3. **Adequate Resources**:
   - Sufficient budget for security tools (SIEM, EDR, encryption)
   - Adequate staffing (CISO, security team, DPO)
   - Time allocated for security activities (risk assessments, audits, training)

4. **Supplier Cooperation**:
   - E-KYC provider (Appman) complies with DPA requirements 🔴
   - Cloud provider maintains ISO 27001 certification
   - Timely incident notification from suppliers (24-hour SLA)

5. **Continuous Improvement**:
   - Internal audits conducted (quarterly focused, annually comprehensive)
   - Management reviews (annually minimum)
   - Corrective actions implemented promptly (Critical: 7 days, High: 30 days, Medium: 90 days)

---

## 9. Scope Review and Maintenance | การทบทวนและบำรุงรักษาขอบเขต

### 9.1 Review Schedule | กำหนดการทบทวน

This ISMS scope statement shall be reviewed:

- **Annually** (by CISO, approved by CEO) - scheduled for [Month]
- **Ad-hoc** when significant changes occur:
  - **E-KYC provider change** 🔴 (update Section 3.1.5, 7.1)
  - New business units or locations added
  - Major system changes (new platform, migration to new cloud provider)
  - Regulatory changes (PDPA updates, new ISO 27001 version)
  - Audit findings requiring scope clarification
  - Significant security incidents affecting scope understanding

### 9.2 Change Management | การจัดการการเปลี่ยนแปลง

**Process for Scope Changes**:

1. **Change Request**:
   - Requester submits change request to CISO (with justification)
   - Examples: "Add new subsidiary to scope", "Exclude legacy system (being decommissioned)"

2. **Impact Assessment** (by CISO + DPO):
   - Assess impact on:
     - Risk assessment (new risks introduced or risks mitigated?)
     - Statement of Applicability (SoA) (new controls needed?)
     - Policies and procedures (updates required?)
     - PDPA compliance (new data processing activities?)

3. **Approval**:
   - CISO recommends approve/deny
   - CEO approves scope changes

4. **Documentation Update**:
   - Update this Scope Statement
   - Update related documents (SoA, risk assessment, policies)
   - Version control (increment version, document change history)

5. **Communication**:
   - Notify all employees of scope changes (email, intranet)
   - Update ISMS documentation repository

6. **Audit Trail**:
   - Document change in management review minutes
   - Track in ISMS system (CISO Assistant or equivalent)

### 9.3 Version Control | การควบคุมเวอร์ชัน

| Version | Date | Author | Changes | Approved By |
|---------|------|--------|---------|-------------|
| 1.0 | [Date] | CISO | Initial version | CEO |
| | | | | |

**Change History**: Maintained in `/standards/iso27001/01-context/scope-statement-changelog.md`

---

## 10. Related Documents | เอกสารที่เกี่ยวข้อง

- **Information Security Policy** (POL-001)
- **Supplier Security Policy** (POL-004) - E-KYC provider requirements
- **PDPA Compliance Policy** (POL-003)
- **Statement of Applicability** (SoA) - All 93 Annex A controls
- **Risk Assessment** - 6 E-KYC specific risks (R-001 to R-012)
- **Internal and External Issues Analysis** - `/standards/iso27001/01-context/internal-external-issues.md`
- **Interested Parties and Requirements** - `/standards/iso27001/01-context/interested-parties.md`

---

## 11. Approval and Acknowledgment | การอนุมัติและการรับทราบ

### 11.1 Executive Approval | การอนุมัติโดยผู้บริหาร

This ISMS Scope Statement has been reviewed and approved by:

**CEO Signature** | **ลายเซ็น CEO**:

```
_________________________________________
[CEO Name]
Chief Executive Officer
Certogo Co., Ltd.

Date: _______________
```

**CISO Endorsement** | **ลายเซ็น CISO**:

```
_________________________________________
[CISO Name]
Chief Information Security Officer
Certogo Co., Ltd.

Date: _______________
```

### 11.2 Scope Acknowledgment | การรับทราบขอบเขต

**All employees must acknowledge understanding of the ISMS scope.**

**ข้าพเจ้ารับทราบขอบเขตของระบบการจัดการความมั่นคงปลอดภัยสารสนเทศ (ISMS) ของ Certogo**

```
Employee Name (Print): _________________________________

Employee Signature: ____________________________________

Department: ____________________________________________

Date: _______________
```

---

**END OF DOCUMENT | สิ้นสุดเอกสาร**

**Document Classification**: Internal Use Only
**Version**: 1.0
**Last Updated**: [Date]
**Next Review**: [Date + 1 year]
