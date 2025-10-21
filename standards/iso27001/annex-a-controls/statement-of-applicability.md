# Statement of Applicability (SoA)
# แถลงการณ์การประยุกต์ใช้มาตรการควบคุม

## Document Information | ข้อมูลเอกสาร

- **Organization** | องค์กร: Certogo Platform
- **ISMS Scope** | ขอบเขต ISMS: Certogo LMS Platform and 3rd Party E-KYC Integration Services
- **Standard** | มาตรฐาน: ISO/IEC 27001:2022
- **Version** | เวอร์ชัน: 1.0
- **Date** | วันที่: 2025-01-20
- **Status** | สถานะ: Draft | ร่าง

---

## Important Notice | ประกาศสำคัญ

⚠️ **Third-Party Service Integration** | **การเชื่อมต่อบริการบุคคลที่สาม**

This SoA covers Certogo's core LMS platform and the **current integration with Appman E-KYC solution**.

แถลงการณ์ฉบับนี้ครอบคลุมแพลตฟอร์ม LMS หลักของ Certogo และ **การเชื่อมต่อกับระบบ E-KYC ของ Appman ในปัจจุบัน**

**Key Considerations** | **ข้อควรพิจารณาสำคัญ**:

1. **E-KYC Provider May Change** | **ผู้ให้บริการ E-KYC อาจเปลี่ยนแปลง**
   - Current provider: Appman Co., Ltd.
   - ผู้ให้บริการปัจจุบัน: บริษัท แอพแมน จำกัด
   - This SoA will require updates if E-KYC provider changes
   - แถลงการณ์นี้จะต้องได้รับการปรับปรุงหากผู้ให้บริการ E-KYC มีการเปลี่ยนแปลง

2. **Supplier Security Assessment Required** | **ต้องมีการประเมินความปลอดภัยของซัพพลายเออร์**
   - Per Control A.5.19: Information security in supplier relationships
   - ตามมาตรการควบคุม A.5.19: ความมั่นคงปลอดภัยสารสนเทศในความสัมพันธ์กับซัพพลายเออร์
   - New E-KYC providers must undergo security assessment before integration
   - ผู้ให้บริการ E-KYC รายใหม่ต้องผ่านการประเมินความปลอดภัยก่อนการเชื่อมต่อ

3. **Version Control** | **การควบคุมเวอร์ชัน**
   - This SoA version applies to: Appman E-KYC v2.0 (as per manual dated)
   - แถลงการณ์เวอร์ชันนี้ใช้กับ: Appman E-KYC v2.0 (ตามคู่มือที่ระบุไว้)
   - Review required when E-KYC service/provider changes
   - ต้องทบทวนเมื่อบริการ/ผู้ให้บริการ E-KYC มีการเปลี่ยนแปลง

---

## ISMS Scope Definition | การกำหนดขอบเขต ISMS

### In-Scope Services | บริการที่อยู่ในขอบเขต

#### 1. Certogo LMS Platform (Core) | แพลตฟอร์ม LMS ของ Certogo (หลัก)
- ✅ **Fully Managed by Certogo** | **บริหารจัดการโดย Certogo เต็มรูปแบบ**
- User authentication and authorization | การยืนยันตัวตนและการอนุญาต
- Course content management | การจัดการเนื้อหาหลักสูตร
- Training delivery and tracking | การจัดส่งและติดตามการอบรม
- Certificate issuance | การออกใบรับรอง
- Compliance reporting | การรายงานการปฏิบัติตาม
- User data management | การจัดการข้อมูลผู้ใช้

#### 2. E-KYC Integration Services (3rd Party) | บริการเชื่อมต่อ E-KYC (บุคคลที่สาม)
- ⚠️ **Currently Provided by Appman Co., Ltd. (Subject to Change)**
- ⚠️ **ให้บริการโดย บริษัท แอพแมน จำกัด ในปัจจุบัน (อาจมีการเปลี่ยนแปลง)**

**Current E-KYC Features** | **คุณสมบัติ E-KYC ปัจจุบัน**:
- ID card verification (OCR) | การตรวจสอบบัตรประชาชน (OCR)
- Facial recognition | การจดจำใบหน้า
- Liveness detection | การตรวจสอบความเป็นมนุษย์
- Document authentication | การยืนยันตัวตนจากเอกสาร
- Multi-document support | รองรับเอกสารหลายประเภท
- API integration | การเชื่อมต่อผ่าน API

**Certogo's Responsibility** | **ความรับผิดชอบของ Certogo**:
- ✅ Secure API integration with E-KYC provider
- ✅ การเชื่อมต่อ API อย่างปลอดภัยกับผู้ให้บริการ E-KYC
- ✅ Data transmission security (TLS/SSL)
- ✅ ความปลอดภัยในการส่งข้อมูล (TLS/SSL)
- ✅ Access control to E-KYC admin functions
- ✅ การควบคุมการเข้าถึงฟังก์ชันผู้ดูแลระบบ E-KYC
- ✅ Supplier security monitoring
- ✅ การติดตามความปลอดภัยของซัพพลายเออร์

**E-KYC Provider's Responsibility** | **ความรับผิดชอบของผู้ให้บริการ E-KYC**:
- ⚠️ Biometric data security | ความปลอดภัยของข้อมูลชีวมิติ
- ⚠️ OCR processing security | ความปลอดภัยในการประมวลผล OCR
- ⚠️ Infrastructure security | ความปลอดภัยของโครงสร้างพื้นฐาน
- ⚠️ Their own ISO 27001 compliance | การปฏิบัติตาม ISO 27001 ของผู้ให้บริการเอง

### Out of Scope | นอกขอบเขต

❌ End-user client devices | อุปกรณ์ของผู้ใช้งาน
❌ Public internet infrastructure | โครงสร้างพื้นฐานอินเทอร์เน็ตสาธารณะ
❌ E-KYC provider's internal ISMS (managed separately by provider)
❌ ระบบ ISMS ภายในของผู้ให้บริการ E-KYC (บริหารโดยผู้ให้บริการแยกต่างหาก)

---

## ISO 27001:2022 Annex A Controls Applicability
## การประยุกต์ใช้มาตรการควบคุมภาคผนวก A ของ ISO 27001:2022

**Legend** | **สัญลักษณ์**:
- ✅ **Applicable** | **ใช้ได้** - Control is implemented
- 🔶 **Partially Applicable** | **ใช้ได้บางส่วน** - Control applies with limitations
- ❌ **Not Applicable** | **ไม่ใช้ได้** - Control doesn't apply to scope
- 🔄 **Shared Control** | **ควบคุมร่วมกัน** - Shared between Certogo and 3rd party provider

---

## A.5 Organizational Controls | มาตรการควบคุมด้านองค์กร

### A.5.1 Policies for Information Security | นโยบายความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Information Security Policy covers both LMS and E-KYC integration
- นโยบายความมั่นคงปลอดภัยครอบคลุมทั้ง LMS และการเชื่อมต่อ E-KYC
- Policy requires all 3rd party providers to maintain equivalent security standards
- นโยบายกำหนดให้ผู้ให้บริการบุคคลที่สามทุกรายต้องรักษามาตรฐานความปลอดภัยที่เทียบเท่า

**Evidence** | **หลักฐาน**: `evidence/policies/information-security-policy.pdf`

**Justification** | **เหตุผล**:
Core requirement for ISMS implementation
ข้อกำหนดหลักสำหรับการดำเนินการ ISMS

---

### A.5.2 Information Security Roles and Responsibilities | บทบาทและความรับผิดชอบด้านความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- **CISO** | **หัวหน้าฝ่ายความมั่นคงปลอดภัยสารสนเทศ**: Overall ISMS responsibility
- **LMS Security Team** | **ทีมความปลอดภัย LMS**: Platform security management
- **Integration Team** | **ทีมเชื่อมต่อระบบ**: E-KYC integration security
- **Supplier Management** | **การจัดการซัพพลายเออร์**: 3rd party security monitoring

**Evidence** | **หลักฐาน**: `evidence/records/roles-responsibilities-matrix.xlsx`

---

### A.5.3 Segregation of Duties | การแบ่งแยกหน้าที่

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Separation between LMS admin and E-KYC admin roles
- แยกบทบาทระหว่างผู้ดูแลระบบ LMS และผู้ดูแลระบบ E-KYC
- Different teams for development, operation, and audit
- ทีมต่างหากสำหรับการพัฒนา การปฏิบัติการ และการตรวจสอบ

**Evidence** | **หลักฐาน**: `evidence/records/access-control-matrix.xlsx`

---

### A.5.4 Management Responsibilities | ความรับผิดชอบของฝ่ายบริหาร

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Management commitment to ISMS
- ฝ่ายบริหารมุ่งมั่นต่อ ISMS
- Regular management review meetings
- ประชุมทบทวนฝ่ายบริหารอย่างสม่ำเสมอ
- Resource allocation for security
- การจัดสรรทรัพยากรเพื่อความปลอดภัย

**Evidence** | **หลักฐาน**: `evidence/records/management-review-minutes.pdf`

---

### A.5.5 Contact with Authorities | การติดต่อกับหน่วยงานที่มีอำนาจ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Established contacts with:
  - PDPC (Personal Data Protection Committee) | คณะกรรมการคุ้มครองข้อมูลส่วนบุคคล
  - ThaiCERT | ศูนย์ประสานงานการแก้ไขปัญหาความมั่นคงปลอดภัยทางคอมพิวเตอร์แห่งประเทศไทย
  - Local law enforcement | หน่วยงานบังคับใช้กฎหมายท้องถิ่น

**Evidence** | **หลักฐาน**: `evidence/procedures/authority-contact-list.pdf`

---

### A.5.6 Contact with Special Interest Groups | การติดต่อกับกลุ่มผู้มีส่วนได้ส่วนเสียพิเศษ

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- Membership in Thai Cloud Computing Association (optional)
- สมาชิกสมาคมคลาวด์คอมพิวติ้งแห่งประเทศไทย (ตามความเหมาะสม)
- Security forums participation
- การมีส่วนร่วมในเวทีด้านความปลอดภัย

**Justification** | **เหตุผล**:
Limited to industry-specific groups relevant to LMS and E-KYC
จำกัดเฉพาะกลุ่มเฉพาะอุตสาหกรรมที่เกี่ยวข้องกับ LMS และ E-KYC

---

### A.5.7 Threat Intelligence | ข่าวกรองภัยคุกคาม

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- **E-KYC Specific Threats** | **ภัยคุกคามเฉพาะ E-KYC**:
  - Deepfake attacks | การโจมตีด้วย Deepfake
  - Document forgery | การปลอมแปลงเอกสาร
  - Biometric spoofing | การปลอมแปลงข้อมูลชีวมิติ

- **LMS Specific Threats** | **ภัยคุกคามเฉพาะ LMS**:
  - Certificate fraud | การปลอมแปลงใบรับรอง
  - Unauthorized access to training records | การเข้าถึงบันทึกการอบรมโดยไม่ได้รับอนุญาต

- Monitoring security advisories from E-KYC provider
- ติดตามคำแนะนำด้านความปลอดภัยจากผู้ให้บริการ E-KYC

**Evidence** | **หลักฐาน**: `evidence/records/threat-intelligence-log.xlsx`

**Note** | **หมายเหตุ**:
⚠️ Certogo relies on E-KYC provider for biometric-specific threat intelligence
⚠️ Certogo พึ่งพาผู้ให้บริการ E-KYC สำหรับข่าวกรองภัยคุกคามเฉพาะด้านชีวมิติ

---

### A.5.8 Information Security in Project Management | ความมั่นคงปลอดภัยสารสนเทศในการจัดการโครงการ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Security requirements integrated in project lifecycle
- ข้อกำหนดด้านความปลอดภัยบูรณาการในวงจรชีวิตโครงการ
- **Special consideration for E-KYC provider migration projects**
- **พิจารณาเป็นพิเศษสำหรับโครงการการย้ายผู้ให้บริการ E-KYC**
- Security impact assessment for new integrations
- การประเมินผลกระทบด้านความปลอดภัยสำหรับการเชื่อมต่อใหม่

**Evidence** | **หลักฐาน**: `evidence/procedures/secure-project-management.pdf`

---

### A.5.9 Inventory of Information and Other Associated Assets | ทะเบียนสารสนเทศและสินทรัพย์อื่นๆ ที่เกี่ยวข้อง

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:

**Certogo-Owned Assets** | **สินทรัพย์ที่ Certogo เป็นเจ้าของ**:
- LMS application servers | เซิร์ฟเวอร์แอปพลิเคชัน LMS
- Database servers | เซิร์ฟเวอร์ฐานข้อมูล
- User training records | บันทึกการอบรมผู้ใช้
- Certificate templates | แม่แบบใบรับรอง
- E-KYC admin interface | ส่วนติดต่อผู้ดูแลระบบ E-KYC

**3rd Party Assets (Appman E-KYC)** | **สินทรัพย์บุคคลที่สาม (Appman E-KYC)**:
- ⚠️ E-KYC API endpoints | ปลายทาง API ของ E-KYC
- ⚠️ Facial recognition engine | เครื่องมือจดจำใบหน้า
- ⚠️ OCR processing systems | ระบบประมวลผล OCR
- ⚠️ Biometric databases (managed by provider)
- ⚠️ ฐานข้อมูลชีวมิติ (บริหารโดยผู้ให้บริการ)

**Evidence** | **หลักฐาน**: `evidence/records/asset-inventory.xlsx`

**Note** | **หมายเหตุ**:
⚠️ Asset inventory must be updated when E-KYC provider changes
⚠️ ต้องปรับปรุงทะเบียนสินทรัพย์เมื่อผู้ให้บริการ E-KYC เปลี่ยนแปลง

---

### A.5.10 Acceptable Use of Information and Other Associated Assets | การใช้สารสนเทศและสินทรัพย์อื่นๆ ที่ยอมรับได้

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Acceptable Use Policy for Certogo staff
- นโยบายการใช้งานที่ยอมรับได้สำหรับพนักงาน Certogo
- Restrictions on E-KYC data usage (only for identity verification)
- ข้อจำกัดการใช้ข้อมูล E-KYC (เฉพาะการยืนยันตัวตนเท่านั้น)
- Prohibition of biometric data retention beyond legal requirements
- ห้ามเก็บรักษาข้อมูลชีวมิตินอกเหนือจากข้อกำหนดทางกฎหมาย

**Evidence** | **หลักฐาน**: `evidence/policies/acceptable-use-policy.pdf`

---

### A.5.11 Return of Assets | การส่งคืนสินทรัพย์

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Employee termination procedures
- ขั้นตอนการเลิกจ้างพนักงาน
- **Contractor offboarding (includes E-KYC integration consultants)**
- **การส่งมอบงานของผู้รับเหมา (รวมที่ปรึกษาการเชื่อมต่อ E-KYC)**
- Access revocation procedures
- ขั้นตอนการเพิกถอนการเข้าถึง

**Evidence** | **หลักฐาน**: `evidence/procedures/asset-return-procedure.pdf`

---

### A.5.12 Classification of Information | การจัดประเภทสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:

**Data Classification Levels** | **ระดับการจัดประเภทข้อมูล**:

1. **Public** | **สาธารณะ**:
   - Course catalog | แค็ตตาล็อกหลักสูตร
   - Marketing materials | สื่อการตลาด

2. **Internal** | **ภายใน**:
   - Internal training materials | สื่อการอบรมภายใน
   - System documentation | เอกสารระบบ

3. **Confidential** | **ความลับ**:
   - User training records | บันทึกการอบรมผู้ใช้
   - Certificate data | ข้อมูลใบรับรอง
   - E-KYC admin credentials | ข้อมูลประจำตัวผู้ดูแลระบบ E-KYC

4. **Highly Confidential** | **ความลับสูงสุด**:
   - **Personal Data (PDPA Sensitive)** | **ข้อมูลส่วนบุคคล (ข้อมูลอ่อนไหวตาม PDPA)**
     - Biometric data (facial images) | ข้อมูลชีวมิติ (ภาพใบหน้า)
     - ID card information | ข้อมูลบัตรประชาชน
     - KYC verification results | ผลการยืนยันตัวตน KYC

**Evidence** | **หลักฐาน**: `evidence/policies/data-classification-policy.pdf`

**Special Note on E-KYC Data** | **หมายเหตุพิเศษเกี่ยวกับข้อมูล E-KYC**:
⚠️ All biometric and PII data from E-KYC processes classified as "Highly Confidential"
⚠️ ข้อมูลชีวมิติและข้อมูลส่วนบุคคลทั้งหมดจากกระบวนการ E-KYC จัดเป็น "ความลับสูงสุด"

---

### A.5.13 Labelling of Information | การติดฉลากสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Document headers with classification labels
- หัวเอกสารพร้อมฉลากการจัดประเภท
- Email classification tags
- แท็กการจัดประเภทอีเมล
- **E-KYC data exports marked as "CONFIDENTIAL - BIOMETRIC DATA"**
- **การส่งออกข้อมูล E-KYC ติดเครื่องหมาย "ความลับ - ข้อมูลชีวมิติ"**

**Evidence** | **หลักฐาน**: `evidence/procedures/information-labelling-standard.pdf`

---

### A.5.14 Information Transfer | การถ่ายโอนสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- **E-KYC API Communication**:
  - TLS 1.3 encryption mandatory | การเข้ารหัส TLS 1.3 บังคับ
  - API key authentication | การยืนยันตัวตนด้วย API key
  - Rate limiting | การจำกัดอัตรา

- **LMS Data Transfer**:
  - SFTP for bulk data transfers | SFTP สำหรับการถ่ายโอนข้อมูลจำนวนมาก
  - Encrypted email for certificates | อีเมลเข้ารหัสสำหรับใบรับรอง

**Evidence** | **หลักฐาน**: `evidence/procedures/secure-data-transfer.pdf`

---

### A.5.15 Access Control | การควบคุมการเข้าถึง

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Role-Based Access Control (RBAC) | การควบคุมการเข้าถึงตามบทบาท
- **Separate access controls for**:
  - LMS administrators | ผู้ดูแลระบบ LMS
  - E-KYC administrators | ผู้ดูแลระบบ E-KYC
  - Integration team | ทีมเชื่อมต่อระบบ
  - Auditors | ผู้ตรวจสอบ

**Evidence** | **หลักฐาน**: `evidence/procedures/access-control-policy.pdf`

---

### A.5.16 Identity Management | การจัดการเอกลักษณ์

**Status** | **สถานะ**: 🔄 **Shared Control**

**Implementation** | **การดำเนินการ**:

**Certogo Responsibility** | **ความรับผิดชอบของ Certogo**:
- ✅ LMS user identity management
- ✅ การจัดการเอกลักษณ์ผู้ใช้ LMS
- ✅ E-KYC admin user provisioning
- ✅ การจัดเตรียมผู้ใช้ผู้ดูแลระบบ E-KYC

**E-KYC Provider Responsibility** | **ความรับผิดชอบของผู้ให้บริการ E-KYC**:
- ⚠️ End-user identity verification process
- ⚠️ กระบวนการยืนยันตัวตนผู้ใช้ปลายทาง
- ⚠️ Biometric identity matching
- ⚠️ การจับคู่เอกลักษณ์ชีวมิติ

**Evidence** | **หลักฐาน**: `evidence/procedures/identity-management-procedure.pdf`

---

### A.5.17 Authentication Information | สารสนเทศการพิสูจน์ตัวตน

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Strong password policy | นโยบายรหัสผ่านที่เข้มแข็ง
- Multi-Factor Authentication (MFA) for admin access
- การยืนยันตัวตนหลายปัจจัย (MFA) สำหรับการเข้าถึงผู้ดูแลระบบ
- **E-KYC API key rotation policy**
- **นโยบายการหมุนเวียน API key ของ E-KYC**
- Secure credential storage (HashiCorp Vault or equivalent)
- การจัดเก็บข้อมูลประจำตัวอย่างปลอดภัย (HashiCorp Vault หรือเทียบเท่า)

**Evidence** | **หลักฐาน**: `evidence/procedures/authentication-policy.pdf`

---

### A.5.18 Access Rights | สิทธิการเข้าถึง

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Principle of least privilege | หลักการของสิทธิพิเศษน้อยที่สุด
- Regular access rights review (quarterly)
- การทบทวนสิทธิการเข้าถึงเป็นประจำ (รายไตรมาส)
- **Immediate revocation of access upon E-KYC provider change**
- **การเพิกถอนการเข้าถึงทันทีเมื่อมีการเปลี่ยนผู้ให้บริการ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/records/access-rights-review-log.xlsx`

---

### A.5.19 Information Security in Supplier Relationships | ความมั่นคงปลอดภัยสารสนเทศในความสัมพันธ์กับซัพพลายเออร์

**Status** | **สถานะ**: ✅ **Applicable** ⚠️ **CRITICAL FOR E-KYC**

**Implementation** | **การดำเนินการ**:

**Current Supplier** | **ซัพพลายเออร์ปัจจุบัน**: Appman Co., Ltd.

**Supplier Security Assessment** | **การประเมินความปลอดภัยซัพพลายเออร์**:
- ✅ Verification of ISO 27001 certification
- ✅ การตรวจสอบการรับรอง ISO 27001
- ✅ CSA-STAR Level 2 verification
- ✅ การตรวจสอบ CSA-STAR Level 2
- ✅ Annual security audit of supplier
- ✅ การตรวจสอบความปลอดภัยซัพพลายเออร์ประจำปี
- ✅ Contractual security requirements
- ✅ ข้อกำหนดด้านความปลอดภัยตามสัญญา

**Required for New E-KYC Providers** | **ข้อกำหนดสำหรับผู้ให้บริการ E-KYC รายใหม่**:
- 🔴 **Mandatory pre-contract security assessment**
- 🔴 **การประเมินความปลอดภัยก่อนทำสัญญาบังคับ**
- 🔴 **ISO 27001 or equivalent certification required**
- 🔴 **ต้องมีการรับรอง ISO 27001 หรือเทียบเท่า**
- 🔴 **PDPA compliance verification**
- 🔴 **การตรวจสอบการปฏิบัติตาม PDPA**
- 🔴 **Data Processing Agreement (DPA) mandatory**
- 🔴 **ข้อตกลงการประมวลผลข้อมูล (DPA) บังคับ**

**Evidence** | **หลักฐาน**:
- `evidence/records/supplier-security-assessment-appman.pdf`
- `evidence/contracts/appman-service-agreement.pdf` (redacted)
- `evidence/contracts/data-processing-agreement-template.pdf`

---

### A.5.20 Addressing Information Security within Supplier Agreements | การจัดการความมั่นคงปลอดภัยสารสนเทศในข้อตกลงกับซัพพลายเออร์

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:

**Current Agreement with Appman** | **ข้อตกลงปัจจุบันกับ Appman**:
- Service Level Agreement (SLA): 99.9% uptime
- Security incident notification: Within 24 hours
- การแจ้งเหตุการณ์ด้านความปลอดภัย: ภายใน 24 ชั่วโมง
- Data breach notification: Immediate
- การแจ้งการละเมิดข้อมูล: ทันที
- Right to audit: Annual security audit rights
- สิทธิในการตรวจสอบ: สิทธิตรวจสอบความปลอดภัยประจำปี

**Mandatory Clauses for Any E-KYC Provider** | **ข้อบังคับสำหรับผู้ให้บริการ E-KYC ทุกราย**:
- 🔴 Data ownership: Certogo retains ownership
- 🔴 ความเป็นเจ้าของข้อมูล: Certogo เป็นเจ้าของข้อมูล
- 🔴 Data deletion: Within 30 days of contract termination
- 🔴 การลบข้อมูล: ภายใน 30 วันหลังสิ้นสุดสัญญา
- 🔴 Subprocessor restrictions: Require approval
- 🔴 ข้อจำกัดผู้ประมวลผลช่วง: ต้องได้รับอนุมัติ
- 🔴 Data localization: Thailand data center preferred
- 🔴 การจัดเก็บข้อมูลในประเทศ: ศูนย์ข้อมูลในประเทศไทยที่ต้องการ

**Evidence** | **หลักฐาน**: `evidence/contracts/supplier-security-requirements.pdf`

---

### A.5.21 Managing Information Security in the ICT Supply Chain | การจัดการความมั่นคงปลอดภัยสารสนเทศในห่วงโซ่อุปทาน ICT

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- Primary focus on E-KYC provider supply chain
- มุ่งเน้นหลักที่ห่วงโซ่อุปทานของผู้ให้บริการ E-KYC
- Requirement for E-KYC provider to disclose subprocessors
- ข้อกำหนดให้ผู้ให้บริการ E-KYC เปิดเผยผู้ประมวลผลช่วง
- **Current Appman subprocessors**: [List to be documented]
- **ผู้ประมวลผลช่วงของ Appman ปัจจุบัน**: [รายการที่จะจัดทำเอกสาร]

**Justification** | **เหตุผล**:
Limited control over E-KYC provider's supply chain; reliance on contractual terms
การควบคุมห่วงโซ่อุปทานของผู้ให้บริการ E-KYC มีจำกัด อาศัยข้อกำหนดตามสัญญา

---

### A.5.22 Monitoring, Review and Change Management of Supplier Services | การติดตาม ทบทวน และจัดการการเปลี่ยนแปลงบริการซัพพลายเออร์

**Status** | **สถานะ**: ✅ **Applicable** ⚠️ **CRITICAL**

**Implementation** | **การดำเนินการ**:

**Regular Monitoring** | **การติดตามเป็นประจำ**:
- ✅ Monthly E-KYC service performance review
- ✅ การทบทวนประสิทธิภาพบริการ E-KYC รายเดือน
- ✅ Quarterly security compliance check
- ✅ การตรวจสอบการปฏิบัติตามด้านความปลอดภัยรายไตรมาส
- ✅ Annual supplier audit
- ✅ การตรวจสอบซัพพลายเออร์ประจำปี

**Change Management for E-KYC Provider** | **การจัดการการเปลี่ยนแปลงสำหรับผู้ให้บริการ E-KYC**:

🔴 **MANDATORY PROCESS IF CHANGING E-KYC PROVIDER** | **กระบวนการบังคับหากเปลี่ยนผู้ให้บริการ E-KYC**:

1. **Pre-Change Assessment** | **การประเมินก่อนการเปลี่ยนแปลง**:
   - Security assessment of new provider | การประเมินความปลอดภัยของผู้ให้บริการรายใหม่
   - Gap analysis against current capabilities | การวิเคราะห์ช่องว่างกับความสามารถปัจจุบัน
   - Risk assessment | การประเมินความเสี่ยง

2. **Migration Plan** | **แผนการย้ายระบบ**:
   - Data migration security | ความปลอดภัยในการย้ายข้อมูล
   - Parallel run period | ระยะเวลาทำงานคู่ขนาน
   - Rollback plan | แผนย้อนกลับ

3. **Post-Change Review** | **การทบทวนหลังการเปลี่ยนแปลง**:
   - Security validation | การตรวจสอบความปลอดภัย
   - Performance verification | การตรวจสอบประสิทธิภาพ
   - Update of this SoA | การปรับปรุง SoA ฉบับนี้

4. **Old Provider Off-boarding** | **การปิดการใช้งานผู้ให้บริการเดิม**:
   - Data deletion verification | การตรวจสอบการลบข้อมูล
   - Access revocation | การเพิกถอนการเข้าถึง
   - Certificate of destruction | ใบรับรองการทำลายข้อมูล

**Evidence** | **หลักฐาน**:
- `evidence/procedures/supplier-monitoring-procedure.pdf`
- `evidence/procedures/ekyc-provider-change-management.pdf` ⚠️ **CRITICAL DOCUMENT**

---

### A.5.23 Information Security for Use of Cloud Services | ความมั่นคงปลอดภัยสารสนเทศสำหรับการใช้บริการคลาวด์

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:

**Certogo LMS** (Primary Cloud Services):
- Infrastructure: AWS / Azure / GCP [Specify]
- โครงสร้างพื้นฐาน: AWS / Azure / GCP [ระบุ]
- CSA-STAR certified cloud provider
- ผู้ให้บริการคลาวด์ที่ได้รับการรับรอง CSA-STAR

**Appman E-KYC** (3rd Party Cloud):
- ⚠️ Cloud infrastructure managed by Appman
- ⚠️ โครงสร้างพื้นฐานคลาวด์บริหารโดย Appman
- CSA-STAR Level 2 certified (as documented)
- ได้รับการรับรอง CSA-STAR Level 2 (ตามที่บันทึกไว้)

**Shared Responsibility Model** | **โมเดลความรับผิดชอบร่วม**:
- Certogo: Application layer security | ความปลอดภัยชั้นแอปพลิเคชัน
- Cloud Provider: Infrastructure security | ความปลอดภัยโครงสร้างพื้นฐาน
- E-KYC Provider: E-KYC service security | ความปลอดภัยบริการ E-KYC

**Evidence** | **หลักฐาน**: `evidence/records/cloud-service-agreements.pdf`

---

## A.6 People Controls | มาตรการควบคุมด้านบุคลากร

### A.6.1 Screening | การคัดกรอง

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Background checks for all employees with access to:
  - LMS databases | ฐานข้อมูล LMS
  - E-KYC admin functions | ฟังก์ชันผู้ดูแลระบบ E-KYC
  - Personal data | ข้อมูลส่วนบุคคล

- **Enhanced screening for E-KYC integration team**
- **การคัดกรองเพิ่มเติมสำหรับทีมเชื่อมต่อ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/procedures/employee-screening-procedure.pdf`

---

### A.6.2 Terms and Conditions of Employment | ข้อกำหนดและเงื่อนไขการจ้างงาน

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Employment contracts include:
  - Confidentiality clauses | ข้อความการรักษาความลับ
  - Data protection obligations | ภาระผูกพันการคุ้มครองข้อมูล
  - **Specific prohibitions on unauthorized E-KYC data access**
  - **ข้อห้ามเฉพาะในการเข้าถึงข้อมูล E-KYC โดยไม่ได้รับอนุญาต**

**Evidence** | **หลักฐาน**: `evidence/templates/employment-contract-template.pdf` (redacted)

---

### A.6.3 Information Security Awareness, Education and Training | การสร้างความตระหนัก การศึกษา และการฝึกอบรมด้านความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:

**General Security Training** (All Staff):
- Annual security awareness training via Certogo LMS
- การอบรมสร้างความตระหนักด้านความปลอดภัยประจำปีผ่าน Certogo LMS
- PDPA compliance training | การอบรมการปฏิบัติตาม PDPA
- Phishing simulation exercises | แบบฝึกหัดจำลองฟิชชิ่ง

**Specialized Training** (E-KYC Team):
- 🔴 **Biometric data handling**
- 🔴 **การจัดการข้อมูลชีวมิติ**
- 🔴 **E-KYC fraud detection**
- 🔴 **การตรวจจับการฉ้อโกง E-KYC**
- 🔴 **Secure API integration practices**
- 🔴 **แนวปฏิบัติการเชื่อมต่อ API อย่างปลอดภัย**

**Evidence** | **หลักฐาน**:
- `evidence/records/security-training-completion.xlsx`
- Training completion certificates from Certogo LMS

**Note**: Leveraging own LMS platform for security training demonstrates control effectiveness
**หมายเหตุ**: การใช้แพลตฟอร์ม LMS ของเราเองสำหรับการฝึกอบรมด้านความปลอดภัยแสดงให้เห็นถึงประสิทธิผลของการควบคุม

---

### A.6.4 Disciplinary Process | กระบวนการทางวินัย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Formal disciplinary process for security violations
- กระบวนการทางวินัยอย่างเป็นทางการสำหรับการละเมิดความปลอดภัย
- **Zero-tolerance for unauthorized E-KYC data access**
- **ไม่ยอมให้มีการเข้าถึงข้อมูล E-KYC โดยไม่ได้รับอนุญาต**

**Evidence** | **หลักฐาน**: `evidence/procedures/disciplinary-procedure.pdf`

---

### A.6.5 Responsibilities after Termination or Change of Employment | ความรับผิดชอบหลังการเลิกจ้างหรือการเปลี่ยนแปลงการจ้างงาน

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Exit interview checklist | รายการตรวจสอบการสัมภาษณ์เมื่อออกจากงาน
- Immediate access revocation (LMS + E-KYC admin)
- การเพิกถอนการเข้าถึงทันที (LMS + ผู้ดูแลระบบ E-KYC)
- Return of assets | การส่งคืนสินทรัพย์
- Continued confidentiality obligations
- ภาระผูกพันการรักษาความลับต่อเนื่อง

**Evidence** | **หลักฐาน**: `evidence/procedures/employee-termination-checklist.pdf`

---

### A.6.6 Confidentiality or Non-Disclosure Agreements | ข้อตกลงการรักษาความลับหรือการไม่เปิดเผย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- NDAs signed by:
  - All employees | พนักงานทุกคน
  - Contractors | ผู้รับเหมา
  - **E-KYC integration consultants**
  - **ที่ปรึกษาการเชื่อมต่อ E-KYC**
  - Auditors | ผู้ตรวจสอบ

**Evidence** | **หลักฐาน**: `evidence/templates/nda-template.pdf`

---

### A.6.7 Remote Working | การทำงานทางไกล

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- VPN requirement for remote access | ข้อกำหนด VPN สำหรับการเข้าถึงระยะไกล
- Multi-factor authentication | การยืนยันตัวตนหลายปัจจัย
- **Restrictions on E-KYC admin access from remote locations**
- **ข้อจำกัดการเข้าถึงผู้ดูแลระบบ E-KYC จากสถานที่ระยะไกล**
- Encrypted device requirement | ข้อกำหนดอุปกรณ์เข้ารหัส

**Evidence** | **หลักฐาน**: `evidence/policies/remote-working-policy.pdf`

---

### A.6.8 Information Security Event Reporting | การรายงานเหตุการณ์ด้านความมั่นคงปลอดภัยสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- 24/7 incident reporting hotline | สายด่วนรายงานเหตุการณ์ตลอด 24 ชั่วโมง
- Email: security@certogo.com
- **Mandatory reporting of E-KYC anomalies**
- **การรายงานความผิดปกติของ E-KYC บังคับ**
- Integration with E-KYC provider's incident response
- บูรณาการกับการตอบสนองเหตุการณ์ของผู้ให้บริการ E-KYC

**Evidence** | **หลักฐาน**: `evidence/procedures/incident-reporting-procedure.pdf`

---

## A.7 Physical Controls | มาตรการควบคุมด้านกายภาพ

### A.7.1 Physical Security Perimeters | ขอบเขตความปลอดภัยทางกายภาพ

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:

**Certogo Office**:
- ✅ Access control to office premises
- ✅ การควบคุมการเข้าถึงสถานที่สำนักงาน
- ✅ Visitor management system
- ✅ ระบบจัดการผู้มาเยือน

**Data Center** (Cloud):
- ⚠️ Physical security managed by cloud provider (AWS/Azure/GCP)
- ⚠️ ความปลอดภัยทางกายภาพบริหารโดยผู้ให้บริการคลาวด์
- ⚠️ SOC 2 Type II compliance verified
- ⚠️ ตรวจสอบการปฏิบัติตาม SOC 2 Type II แล้ว

**E-KYC Infrastructure**:
- ⚠️ Physical security managed by Appman/cloud provider
- ⚠️ ความปลอดภัยทางกายภาพบริหารโดย Appman/ผู้ให้บริการคลาวด์

**Justification** | **เหตุผล**:
Limited direct control; reliance on cloud provider attestations
การควบคุมโดยตรงมีจำกัด อาศัยการรับรองของผู้ให้บริการคลาวด์

**Evidence** | **หลักฐาน**:
- `evidence/records/cloud-provider-soc2-report.pdf`
- `evidence/records/office-access-control-log.xlsx`

---

### A.7.2 Physical Entry | การเข้าทางกายภาพ

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- Badge access to Certogo office | การเข้าถึงสำนักงาน Certogo ด้วยบัตร
- Visitor escort policy | นโยบายการคุมตัวผู้มาเยือน
- ⚠️ Data center access managed by cloud provider
- ⚠️ การเข้าถึงศูนย์ข้อมูลบริหารโดยผู้ให้บริการคลาวด์

**Justification** | **เหตุผล**: Cloud-based infrastructure
**เหตุผล**: โครงสร้างพื้นฐานบนคลาวด์

---

### A.7.3 Securing Offices, Rooms and Facilities | การรักษาความปลอดภัยสำนักงาน ห้อง และสิ่งอำนวยความสะดวก

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Locked server room for on-premise equipment
- ห้องเซิร์ฟเวอร์ล็อคสำหรับอุปกรณ์ในสถานที่
- Clean desk policy | นโยบายโต๊ะทำงานสะอาด
- Secure document storage | การจัดเก็บเอกสารอย่างปลอดภัย

**Evidence** | **หลักฐาน**: `evidence/procedures/physical-security-procedures.pdf`

---

### A.7.4 Physical Security Monitoring | การติดตามความปลอดภัยทางกายภาพ

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- CCTV at office entrance | กล้องวงจรปิดที่ทางเข้าสำนักงาน
- ⚠️ Cloud data center monitoring by provider
- ⚠️ การติดตามศูนย์ข้อมูลคลาวด์โดยผู้ให้บริการ

**Justification** | **เหตุผล**: Cloud-based infrastructure
**เหตุผล**: โครงสร้างพื้นฐานบนคลาวด์

---

### A.7.5 Protecting Against Physical and Environmental Threats | การป้องกันภัยคุกคามทางกายภาพและสิ่งแวดล้อม

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- Fire suppression systems at office | ระบบดับเพลิงที่สำนักงาน
- ⚠️ Environmental controls at data center (cloud provider responsibility)
- ⚠️ การควบคุมสิ่งแวดล้อมที่ศูนย์ข้อมูล (ความรับผิดชอบของผู้ให้บริการคลาวด์)

**Justification** | **เหตุผล**: Cloud-based infrastructure
**เหตุผล**: โครงสร้างพื้นฐานบนคลาวด์

---

### A.7.6 Working in Secure Areas | การทำงานในพื้นที่ปลอดภัย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Restricted access to server room | การเข้าถึงห้องเซิร์ฟเวอร์จำกัด
- **Dedicated workstations for E-KYC admin access** (non-portable)
- **เวิร์กสเตชันเฉพาะสำหรับการเข้าถึงผู้ดูแลระบบ E-KYC** (ไม่สามารถเคลื่อนย้ายได้)

**Evidence** | **หลักฐาน**: `evidence/procedures/secure-area-access-procedure.pdf`

---

### A.7.7 Clear Desk and Clear Screen | โต๊ะทำงานและหน้าจอที่ว่างเปล่า

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Mandatory screen lock after 5 minutes idle
- ล็อคหน้าจอบังคับหลังจากไม่มีการใช้งาน 5 นาที
- Secure document disposal (shredding)
- การทำลายเอกสารอย่างปลอดภัย (เครื่องย่อยกระดาษ)
- **No printouts of E-KYC data allowed**
- **ห้ามพิมพ์ข้อมูล E-KYC**

**Evidence** | **หลักฐาน**: `evidence/policies/clear-desk-policy.pdf`

---

### A.7.8 Equipment Siting and Protection | การจัดวางและการป้องกันอุปกรณ์

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- Server racks secured in locked room
- ชั้นวางเซิร์ฟเวอร์ปลอดภัยในห้องล็อค
- ⚠️ Cloud infrastructure (provider managed)
- ⚠️ โครงสร้างพื้นฐานคลาวด์ (ผู้ให้บริการบริหาร)

**Justification** | **เหตุผล**: Minimal on-premise equipment
**เหตุผล**: อุปกรณ์ในสถานที่น้อยที่สุด

---

### A.7.9 Security of Assets Off-Premises | ความปลอดภัยของสินทรัพย์นอกสถานที่

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Laptop encryption mandatory | การเข้ารหัสแล็ปท็อปบังคับ
- Mobile Device Management (MDM) | การจัดการอุปกรณ์เคลื่อนที่
- **Prohibition of E-KYC data on portable devices**
- **ห้ามมีข้อมูล E-KYC บนอุปกรณ์พกพา**

**Evidence** | **หลักฐาน**: `evidence/procedures/mobile-device-policy.pdf`

---

### A.7.10 Storage Media | สื่อบันทึกข้อมูล

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Encrypted backup media | สื่อสำรองข้อมูลเข้ารหัส
- Secure storage cabinet | ตู้เก็บข้อมูลปลอดภัย
- **E-KYC data not stored on removable media**
- **ไม่เก็บข้อมูล E-KYC บนสื่อถอดได้**

**Evidence** | **หลักฐาน**: `evidence/procedures/media-handling-procedure.pdf`

---

### A.7.11 Supporting Utilities | สาธารณูปโภคสนับสนุน

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- UPS for on-premise servers | UPS สำหรับเซิร์ฟเวอร์ในสถานที่
- ⚠️ Cloud infrastructure redundancy (provider managed)
- ⚠️ ความซ้ำซ้อนของโครงสร้างพื้นฐานคลาวด์ (ผู้ให้บริการบริหาร)

**Justification** | **เหตุผล**: Cloud-based infrastructure
**เหตุผล**: โครงสร้างพื้นฐานบนคลาวด์

---

### A.7.12 Cabling Security | ความปลอดภัยของสายเคเบิล

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- Structured cabling in locked conduits (office)
- สายเคเบิลมีโครงสร้างในท่อล็อค (สำนักงาน)
- ⚠️ Data center cabling (cloud provider)
- ⚠️ สายเคเบิลศูนย์ข้อมูล (ผู้ให้บริการคลาวด์)

**Justification** | **เหตุผล**: Cloud-based infrastructure
**เหตุผล**: โครงสร้างพื้นฐานบนคลาวด์

---

### A.7.13 Equipment Maintenance | การบำรุงรักษาอุปกรณ์

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- Scheduled maintenance for on-premise equipment
- การบำรุงรักษาตามกำหนดการสำหรับอุปกรณ์ในสถานที่
- ⚠️ Cloud infrastructure maintenance (provider managed)
- ⚠️ การบำรุงรักษาโครงสร้างพื้นฐานคลาวด์ (ผู้ให้บริการบริหาร)

**Evidence** | **หลักฐาน**: `evidence/records/equipment-maintenance-log.xlsx`

---

### A.7.14 Secure Disposal or Re-use of Equipment | การทำลายหรือนำอุปกรณ์กลับมาใช้ใหม่อย่างปลอดภัย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Data wiping procedures (NIST 800-88)
- ขั้นตอนการลบข้อมูล (NIST 800-88)
- Physical destruction of storage media containing E-KYC data
- การทำลายทางกายภาพของสื่อบันทึกข้อมูลที่มีข้อมูล E-KYC
- Certificate of destruction | ใบรับรองการทำลาย

**Evidence** | **หลักฐาน**:
- `evidence/procedures/secure-disposal-procedure.pdf`
- `evidence/records/disposal-certificates/`

---

## A.8 Technological Controls | มาตรการควบคุมด้านเทคโนโลยี

### A.8.1 User Endpoint Devices | อุปกรณ์ปลายทางของผู้ใช้

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Antivirus on all endpoints | ป้องกันไวรัสบนปลายทางทั้งหมด
- Full disk encryption | การเข้ารหัสดิสก์เต็ม
- Mobile Device Management (MDM) | การจัดการอุปกรณ์เคลื่อนที่
- **Dedicated secure workstations for E-KYC admin**
- **เวิร์กสเตชันปลอดภัยเฉพาะสำหรับผู้ดูแลระบบ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/procedures/endpoint-security-standard.pdf`

---

### A.8.2 Privileged Access Rights | สิทธิการเข้าถึงพิเศษ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Separate admin accounts | บัญชีผู้ดูแลระบบแยกต่างหาก
- Privileged Access Management (PAM) tool
- เครื่องมือการจัดการการเข้าถึงพิเศษ
- **Just-In-Time (JIT) access for E-KYC admin functions**
- **การเข้าถึงแบบ Just-In-Time (JIT) สำหรับฟังก์ชันผู้ดูแลระบบ E-KYC**
- All privileged actions logged | การดำเนินการพิเศษทั้งหมดถูกบันทึก

**Evidence** | **หลักฐาน**: `evidence/procedures/privileged-access-management.pdf`

---

### A.8.3 Information Access Restriction | การจำกัดการเข้าถึงสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Role-Based Access Control (RBAC) | การควบคุมการเข้าถึงตามบทบาท
- **E-KYC Data Access Tiers** | **ระดับการเข้าถึงข้อมูล E-KYC**:
  1. No Access (default) | ไม่มีการเข้าถึง (ค่าเริ่มต้น)
  2. Read-Only (auditors) | อ่านอย่างเดียว (ผู้ตรวจสอบ)
  3. Admin Access (E-KYC team only, with approval)
     การเข้าถึงผู้ดูแลระบบ (ทีม E-KYC เท่านั้น พร้อมการอนุมัติ)

**Evidence** | **หลักฐาน**: `evidence/records/access-control-matrix.xlsx`

---

### A.8.4 Access to Source Code | การเข้าถึงซอร์สโค้ด

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Git repository access control | การควบคุมการเข้าถึงพื้นที่เก็บ Git
- Code review required for all changes
- ต้องมีการทบทวนโค้ดสำหรับการเปลี่ยนแปลงทั้งหมด
- **E-KYC integration code in separate repository with restricted access**
- **โค้ดการเชื่อมต่อ E-KYC ในพื้นที่เก็บแยกต่างหากด้วยการเข้าถึงจำกัด**

**Evidence** | **หลักฐาน**: `evidence/procedures/source-code-management.pdf`

---

### A.8.5 Secure Authentication | การพิสูจน์ตัวตนอย่างปลอดภัย

**Status** | **สถานะ**: ✅ **Applicable** 🔄 **Shared Control**

**Implementation** | **การดำเนินการ**:

**Certogo LMS Authentication** | **การพิสูจน์ตัวตน Certogo LMS**:
- ✅ Multi-Factor Authentication (MFA) for admin
- ✅ การยืนยันตัวตนหลายปัจจัย (MFA) สำหรับผู้ดูแลระบบ
- ✅ Password complexity requirements
- ✅ ข้อกำหนดความซับซ้อนของรหัสผ่าน
- ✅ Password expiry: 90 days
- ✅ รหัสผ่านหมดอายุ: 90 วัน

**E-KYC End-User Authentication** (Managed by Appman):
- ⚠️ ID card verification (OCR) | การตรวจสอบบัตรประชาชน (OCR)
- ⚠️ Facial recognition | การจดจำใบหน้า
- ⚠️ Liveness detection | การตรวจสอบความเป็นมนุษย์
- ⚠️ Multi-document verification | การตรวจสอบเอกสารหลายประเภท

**E-KYC API Authentication** (Certogo Managed):
- ✅ API key authentication | การยืนยันตัวตนด้วย API key
- ✅ Key rotation every 90 days | การหมุนเวียนคีย์ทุก 90 วัน
- ✅ IP whitelisting | การอนุญาต IP

**Evidence** | **หลักฐาน**:
- `evidence/procedures/authentication-policy.pdf`
- `evidence/procedures/ekyc-api-security.pdf`

**Note on E-KYC Provider Change** | **หมายเหตุเกี่ยวกับการเปลี่ยนผู้ให้บริการ E-KYC**:
⚠️ New E-KYC providers must support equivalent or stronger biometric authentication methods
⚠️ ผู้ให้บริการ E-KYC รายใหม่ต้องรองรับวิธีการพิสูจน์ตัวตนทางชีวมิติที่เทียบเท่าหรือแข็งแกร่งกว่า

---

### A.8.6 Capacity Management | การจัดการความจุ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Auto-scaling for cloud infrastructure
- การปรับขนาดอัตโนมัติสำหรับโครงสร้างพื้นฐานคลาวด์
- Performance monitoring | การติดตามประสิทธิภาพ
- **Capacity planning for E-KYC API calls**
- **การวางแผนความจุสำหรับการเรียก API ของ E-KYC**
  - Monitor API rate limits | ติดตามขีดจำกัดอัตรา API
  - Plan for peak verification periods | วางแผนสำหรับช่วงเวลายืนยันตัวตนสูงสุด

**Evidence** | **หลักฐาน**: `evidence/records/capacity-management-reports.pdf`

---

### A.8.7 Protection Against Malware | การป้องกันมัลแวร์

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Endpoint protection | การป้องกันปลายทาง
- Email filtering | การกรองอีเมล
- Web filtering | การกรองเว็บ
- **Malware scanning for uploaded documents in E-KYC process**
- **การสแกนมัลแวร์สำหรับเอกสารที่อัปโหลดในกระบวนการ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/procedures/malware-protection-policy.pdf`

---

### A.8.8 Management of Technical Vulnerabilities | การจัดการช่องโหว่ทางเทคนิค

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Monthly vulnerability scans | การสแกนช่องโหว่รายเดือน
- Patch management process | กระบวนการจัดการแพตช์
- **Coordination with E-KYC provider for shared vulnerability disclosure**
- **การประสานงานกับผู้ให้บริการ E-KYC สำหรับการเปิดเผยช่องโหว่ร่วมกัน**

**Evidence** | **หลักฐาน**:
- `evidence/records/vulnerability-scan-reports/`
- `evidence/procedures/patch-management-procedure.pdf`

---

### A.8.9 Configuration Management | การจัดการการกำหนดค่า

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Infrastructure as Code (Terraform/Ansible)
- โครงสร้างพื้นฐานเป็นโค้ด (Terraform/Ansible)
- Configuration baselines | เส้นฐานการกำหนดค่า
- **E-KYC API endpoint configurations version-controlled**
- **การกำหนดค่าปลายทาง API ของ E-KYC ควบคุมเวอร์ชัน**

**Evidence** | **หลักฐาน**: `evidence/procedures/configuration-management-procedure.pdf`

---

### A.8.10 Information Deletion | การลบสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable** 🔴 **CRITICAL FOR E-KYC**

**Implementation** | **การดำเนินการ**:

**LMS Data Deletion**:
- User-initiated account deletion
- การลบบัญชีโดยผู้ใช้
- Data retention policy: 7 years (compliance records)
- นโยบายการเก็บรักษาข้อมูล: 7 ปี (บันทึกการปฏิบัติตาม)

**E-KYC Data Deletion** 🔴:
- **Biometric data deletion**: Within 30 days after verification (unless legal hold)
- **การลบข้อมูลชีวมิติ**: ภายใน 30 วันหลังการยืนยัน (เว้นแต่มีคำสั่งทางกฎหมาย)
- **ID card images**: Deleted after verification unless user consent for retention
- **ภาพบัตรประชาชน**: ลบหลังการยืนยันเว้นแต่ผู้ใช้ยินยอมให้เก็บรักษา
- **Coordinated deletion with E-KYC provider**
- **การลบประสานกับผู้ให้บริการ E-KYC**
  - Certogo sends deletion request via API
  - Certogo ส่งคำขอลบผ่าน API
  - Provider confirms deletion within 7 days
  - ผู้ให้บริการยืนยันการลบภายใน 7 วัน
  - Certificate of deletion provided
  - ให้ใบรับรองการลบ

**Evidence** | **หลักฐาน**:
- `evidence/procedures/data-deletion-policy.pdf`
- `evidence/procedures/ekyc-data-deletion-procedure.pdf` 🔴 **CRITICAL**
- `evidence/records/deletion-certificates/`

**Note on Provider Change** | **หมายเหตุเกี่ยวกับการเปลี่ยนผู้ให้บริการ**:
⚠️ When changing E-KYC providers, all biometric data with old provider must be deleted within 30 days and certified
⚠️ เมื่อเปลี่ยนผู้ให้บริการ E-KYC ต้องลบข้อมูลชีวมิติทั้งหมดกับผู้ให้บริการเดิมภายใน 30 วันและต้องมีใบรับรอง

---

### A.8.11 Data Masking | การปกปิดข้อมูล

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- **E-KYC Data Masking in Logs**:
  - ID card numbers: Show only last 4 digits (e.g., XXXX-XXXX-XX34-56)
  - หมายเลขบัตรประชาชน: แสดงเฉพาะ 4 หลักสุดท้าย
  - Facial recognition scores: Logged without images
  - คะแนนการจดจำใบหน้า: บันทึกโดยไม่มีภาพ

- **LMS Data Masking**:
  - Email masking in reports (e.g., j***@example.com)
  - การปกปิดอีเมลในรายงาน

**Evidence** | **หลักฐาน**: `evidence/procedures/data-masking-standard.pdf`

---

### A.8.12 Data Leakage Prevention | การป้องกันการรั่วไหลของข้อมูล

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- DLP tools deployed | ติดตั้งเครื่องมือ DLP
- **E-KYC Data Restrictions**:
  - 🔴 **No email of biometric data allowed**
  - 🔴 **ห้ามส่งข้อมูลชีวมิติทางอีเมล**
  - 🔴 **No USB/removable media transfer**
  - 🔴 **ห้ามถ่ายโอนผ่าน USB/สื่อถอดได้**
  - 🔴 **API-only data access**
  - 🔴 **การเข้าถึงข้อมูลผ่าน API เท่านั้น**

**Evidence** | **หลักฐาน**: `evidence/procedures/data-leakage-prevention-policy.pdf`

---

### A.8.13 Information Backup | การสำรองสารสนเทศ

**Status** | **สถานะ**: ✅ **Applicable** 🔶 **Partially Shared**

**Implementation** | **การดำเนินการ**:

**Certogo LMS Backups**:
- ✅ Daily incremental backups | การสำรองข้อมูลเพิ่มเติมรายวัน
- ✅ Weekly full backups | การสำรองข้อมูลเต็มรูปแบบรายสัปดาห์
- ✅ Encrypted backup storage | การจัดเก็บสำรองข้อมูลเข้ารหัส
- ✅ Regular restore testing (quarterly)
- ✅ การทดสอบการกู้คืนเป็นประจำ (รายไตรมาส)

**E-KYC Data Backups**:
- ⚠️ **Minimal backup retention due to privacy requirements**
- ⚠️ **การเก็บรักษาสำรองข้อมูลน้อยที่สุดเนื่องจากข้อกำหนดความเป็นส่วนตัว**
- ⚠️ Biometric data backups managed by E-KYC provider
- ⚠️ การสำรองข้อมูลชีวมิติบริหารโดยผู้ให้บริการ E-KYC
- ✅ Verification results (non-biometric) backed up by Certogo
- ✅ ผลการยืนยัน (ไม่ใช่ชีวมิติ) สำรองโดย Certogo

**Evidence** | **หลักฐาน**:
- `evidence/procedures/backup-procedure.pdf`
- `evidence/records/backup-restore-test-log.xlsx`

---

### A.8.14 Redundancy of Information Processing Facilities | ความซ้ำซ้อนของสิ่งอำนวยความสะดวกการประมวลผลสารสนเทศ

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- ⚠️ Multi-region cloud deployment (LMS)
- ⚠️ การปรับใช้คลาวด์หลายภูมิภาค (LMS)
- ⚠️ E-KYC provider redundancy (Appman responsibility)
- ⚠️ ความซ้ำซ้อนของผู้ให้บริการ E-KYC (ความรับผิดชอบของ Appman)

**Justification** | **เหตุผล**:
Reliance on cloud provider and E-KYC provider redundancy
อาศัยความซ้ำซ้อนของผู้ให้บริการคลาวด์และผู้ให้บริการ E-KYC

---

### A.8.15 Logging | การบันทึก

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:

**LMS Logging**:
- ✅ User authentication events | เหตุการณ์การยืนยันตัวตนผู้ใช้
- ✅ Admin actions | การดำเนินการของผู้ดูแลระบบ
- ✅ Certificate issuance | การออกใบรับรอง

**E-KYC Logging** 🔴:
- ✅ **API calls to E-KYC provider** (with rate limits)
- ✅ **การเรียก API ไปยังผู้ให้บริการ E-KYC** (พร้อมขีดจำกัดอัตรา)
- ✅ **Verification attempts and results** (success/fail)
- ✅ **ความพยายามยืนยันและผลลัพธ์** (สำเร็จ/ล้มเหลว)
- ✅ **Admin access to E-KYC dashboard**
- ✅ **การเข้าถึงผู้ดูแลระบบไปยังแดชบอร์ด E-KYC**
- ⚠️ **No biometric data in logs** (privacy requirement)
- ⚠️ **ไม่มีข้อมูลชีวมิติในบันทึก** (ข้อกำหนดความเป็นส่วนตัว)

**Log Retention**:
- Security logs: 1 year | บันทึกความปลอดภัย: 1 ปี
- E-KYC transaction logs: 7 years (PDPA compliance)
- บันทึกธุรกรรม E-KYC: 7 ปี (การปฏิบัติตาม PDPA)

**Evidence** | **หลักฐาน**: `evidence/procedures/logging-policy.pdf`

---

### A.8.16 Monitoring Activities | การติดตามกิจกรรม

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- SIEM tool deployment | การปรับใช้เครื่องมือ SIEM
- Real-time alerting | การแจ้งเตือนแบบเรียลไทม์
- **E-KYC Anomaly Detection**:
  - Unusual verification failure rates
  - อัตราความล้มเหลวในการยืนยันที่ผิดปกติ
  - Multiple verification attempts from same user
  - ความพยายามยืนยันหลายครั้งจากผู้ใช้รายเดียวกัน
  - API abuse detection
  - การตรวจจับการใช้ API ในทางที่ผิด

**Evidence** | **หลักฐาน**: `evidence/procedures/security-monitoring-procedure.pdf`

---

### A.8.17 Clock Synchronization | การประสานเวลา

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- NTP server synchronization | การประสานกับเซิร์ฟเวอร์ NTP
- Time zone: UTC for all systems | เขตเวลา: UTC สำหรับระบบทั้งหมด
- **Critical for E-KYC audit trails**
- **สำคัญสำหรับบันทึกการตรวจสอบ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/procedures/time-synchronization-policy.pdf`

---

### A.8.18 Use of Privileged Utility Programs | การใช้โปรแกรมสาธารณูปโภคพิเศษ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Restricted access to system utilities
- การเข้าถึงเครื่องมือระบบจำกัด
- All usage logged | การใช้งานทั้งหมดถูกบันทึก
- **Database admin tools for E-KYC data require approval**
- **เครื่องมือผู้ดูแลฐานข้อมูลสำหรับข้อมูล E-KYC ต้องได้รับอนุมัติ**

**Evidence** | **หลักฐาน**: `evidence/procedures/privileged-utility-usage-policy.pdf`

---

### A.8.19 Installation of Software on Operational Systems | การติดตั้งซอฟต์แวร์บนระบบปฏิบัติการ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Change management process | กระบวนการจัดการการเปลี่ยนแปลง
- Testing in staging environment | การทดสอบในสภาพแวดล้อมจัดเตรียม
- **E-KYC SDK/library updates require security review**
- **การปรับปรุง SDK/ไลบรารี E-KYC ต้องมีการทบทวนความปลอดภัย**

**Evidence** | **หลักฐาน**: `evidence/procedures/change-management-procedure.pdf`

---

### A.8.20 Networks Security | ความปลอดภัยเครือข่าย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Network segmentation | การแบ่งส่วนเครือข่าย
- Firewall rules | กฎไฟร์วอลล์
- **E-KYC API endpoints in separate network zone**
- **ปลายทาง API ของ E-KYC ในโซนเครือข่ายแยกต่างหาก**
- IDS/IPS deployment | การปรับใช้ IDS/IPS

**Evidence** | **หลักฐาน**: `evidence/procedures/network-security-architecture.pdf`

---

### A.8.21 Security of Network Services | ความปลอดภัยของบริการเครือข่าย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Service-level agreements with network providers
- ข้อตกลงระดับบริการกับผู้ให้บริการเครือข่าย
- DDoS protection | การป้องกัน DDoS
- **API gateway for E-KYC services**
- **เกตเวย์ API สำหรับบริการ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/contracts/network-service-agreements.pdf`

---

### A.8.22 Segregation of Networks | การแบ่งแยกเครือข่าย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Production/Development/Testing network separation
- การแบ่งแยกเครือข่ายการผลิต/การพัฒนา/การทดสอบ
- **E-KYC integration in separate VLAN**
- **การเชื่อมต่อ E-KYC ใน VLAN แยกต่างหาก**
- DMZ for external-facing services | DMZ สำหรับบริการที่หันหน้าออกภายนอก

**Evidence** | **หลักฐาน**: `evidence/diagrams/network-segmentation-diagram.pdf`

---

### A.8.23 Web Filtering | การกรองเว็บ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Web filtering on all endpoints | การกรองเว็บบนปลายทางทั้งหมด
- Malicious site blocking | การบล็อกไซต์ที่เป็นอันตราย
- **Whitelist for E-KYC provider domains**
- **รายการอนุญาตสำหรับโดเมนผู้ให้บริการ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/procedures/web-filtering-policy.pdf`

---

### A.8.24 Use of Cryptography | การใช้การเข้ารหัส

**Status** | **สถานะ**: ✅ **Applicable** 🔴 **CRITICAL**

**Implementation** | **การดำเนินการ**:

**Data at Rest**:
- ✅ AES-256 encryption for databases
- ✅ การเข้ารหัส AES-256 สำหรับฐานข้อมูล
- ✅ Encrypted backups | การสำรองข้อมูลเข้ารหัส

**Data in Transit**:
- ✅ TLS 1.3 for all connections | TLS 1.3 สำหรับการเชื่อมต่อทั้งหมด
- 🔴 **TLS 1.3 mandatory for E-KYC API** (no fallback)
- 🔴 **TLS 1.3 บังคับสำหรับ API ของ E-KYC** (ไม่มีการถอยกลับ)

**Key Management**:
- ✅ Hardware Security Module (HSM) or KMS
- ✅ โมดูลความปลอดภัยฮาร์ดแวร์ (HSM) หรือ KMS
- ✅ Key rotation: Annually | การหมุนเวียนคีย์: ประจำปี

**E-KYC Specific**:
- 🔴 **Biometric data encrypted at application level before storage**
- 🔴 **ข้อมูลชีวมิติเข้ารหัสที่ระดับแอปพลิเคชันก่อนการจัดเก็บ**
- 🔴 **Separate encryption keys for E-KYC data**
- 🔴 **คีย์การเข้ารหัสแยกต่างหากสำหรับข้อมูล E-KYC**

**Evidence** | **หลักฐาน**: `evidence/procedures/cryptography-policy.pdf`

---

### A.8.25 Secure Development Life Cycle | วงจรชีวิตการพัฒนาอย่างปลอดภัย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Security requirements in design phase
- ข้อกำหนดด้านความปลอดภัยในขั้นตอนการออกแบบ
- Code review mandatory | การทบทวนโค้ดบังคับ
- Static Application Security Testing (SAST)
- การทดสอบความปลอดภัยแอปพลิเคชันแบบคงที่
- **Security review for E-KYC integration code changes**
- **การทบทวนความปลอดภัยสำหรับการเปลี่ยนแปลงโค้ดการเชื่อมต่อ E-KYC**

**Evidence** | **หลักฐาน**: `evidence/procedures/secure-sdlc-policy.pdf`

---

### A.8.26 Application Security Requirements | ข้อกำหนดความปลอดภัยแอปพลิเคชัน

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- OWASP Top 10 compliance | การปฏิบัติตาม OWASP Top 10
- Input validation | การตรวจสอบความถูกต้องของข้อมูลนำเข้า
- **E-KYC API input sanitization**
- **การทำความสะอาดข้อมูลนำเข้า API ของ E-KYC**
- Output encoding | การเข้ารหัสข้อมูลออก

**Evidence** | **หลักฐาน**: `evidence/procedures/application-security-requirements.pdf`

---

### A.8.27 Secure System Architecture and Engineering Principles | สถาปัตยกรรมระบบที่ปลอดภัยและหลักการวิศวกรรม

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Defense in depth | การป้องกันหลายชั้น
- Least privilege principle | หลักการของสิทธิพิเศษน้อยที่สุด
- **E-KYC integration architecture review**
- **การทบทวนสถาปัตยกรรมการเชื่อมต่อ E-KYC**
- Zero trust network architecture
- สถาปัตยกรรมเครือข่ายไม่ไว้วางใจ

**Evidence** | **หลักฐาน**: `evidence/diagrams/system-architecture-diagram.pdf`

---

### A.8.28 Secure Coding | การเขียนโค้ดอย่างปลอดภัย

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Secure coding guidelines | แนวทางการเขียนโค้ดอย่างปลอดภัย
- Developer training | การฝึกอบรมนักพัฒนา
- **E-KYC API wrapper library with built-in security controls**
- **ไลบรารีตัวห่อ API ของ E-KYC พร้อมการควบคุมความปลอดภัยในตัว**

**Evidence** | **หลักฐาน**: `evidence/procedures/secure-coding-standards.pdf`

---

### A.8.29 Security Testing in Development and Acceptance | การทดสอบความปลอดภัยในการพัฒนาและการยอมรับ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Automated security testing in CI/CD pipeline
- การทดสอบความปลอดภัยอัตโนมัติในไปป์ไลน์ CI/CD
- Dynamic Application Security Testing (DAST)
- การทดสอบความปลอดภัยแอปพลิเคชันแบบไดนามิก
- **Penetration testing of E-KYC integration annually**
- **การทดสอบการเจาะระบบการเชื่อมต่อ E-KYC ประจำปี**

**Evidence** | **หลักฐาน**: `evidence/records/penetration-test-reports/`

---

### A.8.30 Outsourced Development | การพัฒนาจากภายนอก

**Status** | **สถานะ**: 🔶 **Partially Applicable**

**Implementation** | **การดำเนินการ**:
- NDA with external developers | NDA กับนักพัฒนาภายนอก
- Code ownership clauses | ข้อความความเป็นเจ้าของโค้ด
- **Security requirements for E-KYC integration consultants**
- **ข้อกำหนดด้านความปลอดภัยสำหรับที่ปรึกษาการเชื่อมต่อ E-KYC**

**Justification** | **เหตุผล**:
Minimal outsourced development; primarily internal team
การพัฒนาจากภายนอกน้อยที่สุด ส่วนใหญ่เป็นทีมภายใน

---

### A.8.31 Separation of Development, Test and Production Environments | การแบ่งแยกสภาพแวดล้อมการพัฒนา การทดสอบ และการผลิต

**Status** | **สถานะ**: ✅ **Applicable** 🔴 **CRITICAL FOR E-KYC**

**Implementation** | **การดำเนินการ**:

**Environment Separation**:
- ✅ Development | การพัฒนา
- ✅ Staging/UAT | การจัดเตรียม/UAT
- ✅ Production | การผลิต

**E-KYC Specific** 🔴:
- 🔴 **Separate E-KYC API keys for each environment**
- 🔴 **คีย์ API ของ E-KYC แยกต่างหากสำหรับแต่ละสภาพแวดล้อม**
- 🔴 **Synthetic test data in dev/staging (no real biometrics)**
- 🔴 **ข้อมูลทดสอบสังเคราะห์ในการพัฒนา/จัดเตรียม (ไม่มีข้อมูลชีวมิติจริง)**
- 🔴 **Production E-KYC access restricted to production environment only**
- 🔴 **การเข้าถึง E-KYC การผลิตจำกัดเฉพาะสภาพแวดล้อมการผลิตเท่านั้น**

**Evidence** | **หลักฐาน**: `evidence/procedures/environment-separation-policy.pdf`

---

### A.8.32 Change Management | การจัดการการเปลี่ยนแปลง

**Status** | **สถานะ**: ✅ **Applicable** 🔴 **CRITICAL FOR E-KYC PROVIDER CHANGE**

**Implementation** | **การดำเนินการ**:

**Standard Change Management**:
- ✅ Change request process | กระบวนการขอเปลี่ยนแปลง
- ✅ Change Advisory Board (CAB) approval
- ✅ การอนุมัติจากคณะกรรมการที่ปรึกษาการเปลี่ยนแปลง (CAB)
- ✅ Testing and rollback plans
- ✅ การทดสอบและแผนย้อนกลับ

**E-KYC Provider Change Management** 🔴 **CRITICAL**:

**IF CHANGING E-KYC PROVIDER** | **หากเปลี่ยนผู้ให้บริการ E-KYC**:

1. **Pre-Change Phase** (4-8 weeks) | **ขั้นตอนก่อนการเปลี่ยนแปลง**:
   - ✅ Security assessment of new provider
   - ✅ การประเมินความปลอดภัยของผู้ให้บริการรายใหม่
   - ✅ Data migration plan approval
   - ✅ การอนุมัติแผนการย้ายข้อมูล
   - ✅ Contract termination notice to old provider (30-90 days)
   - ✅ แจ้งการยกเลิกสัญญากับผู้ให้บริการเดิม (30-90 วัน)
   - ✅ API compatibility testing
   - ✅ การทดสอบความเข้ากันได้ของ API

2. **Migration Phase** (2-4 weeks) | **ขั้นตอนการย้ายระบบ**:
   - ✅ Parallel run with both providers
   - ✅ ทำงานคู่ขนานกับผู้ให้บริการทั้งสอง
   - ✅ Gradual traffic shift (10% → 50% → 100%)
   - ✅ การเปลี่ยนปริมาณการใช้งานแบบค่อยเป็นค่อยไป
   - ✅ Performance and accuracy validation
   - ✅ การตรวจสอบประสิทธิภาพและความแม่นยำ

3. **Post-Change Phase** (4 weeks) | **ขั้นตอนหลังการเปลี่ยนแปลง**:
   - ✅ Old provider data deletion
   - ✅ การลบข้อมูลของผู้ให้บริการเดิม
   - ✅ Access revocation to old provider systems
   - ✅ การเพิกถอนการเข้าถึงระบบผู้ให้บริการเดิม
   - 🔴 **Update this SoA document**
   - 🔴 **ปรับปรุงเอกสาร SoA นี้**
   - ✅ Post-implementation review
   - ✅ การทบทวนหลังการดำเนินการ

**Evidence** | **หลักฐาน**:
- `evidence/procedures/change-management-procedure.pdf`
- `evidence/procedures/ekyc-provider-change-procedure.pdf` 🔴 **CRITICAL**

---

### A.8.33 Test Information | สารสนเทศทดสอบ

**Status** | **สถานะ**: ✅ **Applicable** 🔴 **CRITICAL**

**Implementation** | **การดำเนินการ**:

**General Test Data**:
- ✅ Synthetic user data for testing
- ✅ ข้อมูลผู้ใช้สังเคราะห์สำหรับการทดสอบ
- ✅ Production data never used in dev/test
- ✅ ไม่เคยใช้ข้อมูลการผลิตในการพัฒนา/ทดสอบ

**E-KYC Test Data** 🔴:
- 🔴 **Absolutely NO real biometric data in test environments**
- 🔴 **ห้ามใช้ข้อมูลชีวมิติจริงในสภาพแวดล้อมทดสอบโดยเด็ดขาด**
- 🔴 **Synthetic facial images for testing (AI-generated, non-existent persons)**
- 🔴 **ภาพใบหน้าสังเคราะห์สำหรับการทดสอบ (สร้างด้วย AI, บุคคลที่ไม่มีอยู่จริง)**
- 🔴 **Test ID cards with clearly marked "TEST" watermark**
- 🔴 **บัตรประชาชนทดสอบมีเครื่องหมาย "TEST" อย่างชัดเจน**
- ✅ E-KYC provider sandbox environment used
- ✅ ใช้สภาพแวดล้อม sandbox ของผู้ให้บริการ E-KYC

**Evidence** | **หลักฐาน**: `evidence/procedures/test-data-management-policy.pdf`

---

### A.8.34 Protection of Information Systems during Audit Testing | การป้องกันระบบสารสนเทศระหว่างการทดสอบการตรวจสอบ

**Status** | **สถานะ**: ✅ **Applicable**

**Implementation** | **การดำเนินการ**:
- Read-only access for auditors | การเข้าถึงอ่านอย่างเดียวสำหรับผู้ตรวจสอบ
- Audit testing in isolated environment
- การทดสอบการตรวจสอบในสภาพแวดล้อมแยก
- **E-KYC audit logs access (anonymized)**
- **การเข้าถึงบันทึกการตรวจสอบ E-KYC (นิรนาม)**

**Evidence** | **หลักฐาน**: `evidence/procedures/audit-testing-procedure.pdf`

---

## Summary Statistics | สถิติสรุป

### Control Applicability Overview | ภาพรวมการประยุกต์ใช้มาตรการควบคุม

| Category | Total | Applicable (✅) | Partially (🔶) | Not Applicable (❌) | Shared (🔄) |
|----------|-------|----------------|---------------|-------------------|------------|
| A.5 (Organizational) | 23 | 20 | 2 | 0 | 1 |
| A.6 (People) | 8 | 8 | 0 | 0 | 0 |
| A.7 (Physical) | 14 | 4 | 10 | 0 | 0 |
| A.8 (Technological) | 34 | 28 | 4 | 0 | 2 |
| **TOTAL** | **93** | **74** | **16** | **0** | **3** |

**Compliance Rate** | **อัตราการปฏิบัติตาม**: **94.6%** (Fully or Partially Applicable)

---

## Critical Controls for E-KYC Integration | มาตรการควบคุมสำคัญสำหรับการเชื่อมต่อ E-KYC

🔴 **Must-Maintain Controls** (Even if E-KYC provider changes):

1. **A.5.19** - Supplier Security Assessment | การประเมินความปลอดภัยซัพพลายเออร์
2. **A.5.20** - Supplier Agreement Security | ความปลอดภัยในข้อตกลงซัพพลายเออร์
3. **A.5.22** - Supplier Monitoring & Change Management | การติดตามและจัดการการเปลี่ยนแปลงซัพพลายเออร์
4. **A.8.5** - Secure Authentication | การพิสูจน์ตัวตนอย่างปลอดภัย
5. **A.8.10** - Information Deletion | การลบสารสนเทศ
6. **A.8.11** - Data Masking | การปกปิดข้อมูล
7. **A.8.12** - Data Leakage Prevention | การป้องกันการรั่วไหลของข้อมูล
8. **A.8.24** - Use of Cryptography | การใช้การเข้ารหัส
9. **A.8.31** - Environment Separation | การแบ่งแยกสภาพแวดล้อม
10. **A.8.32** - Change Management | การจัดการการเปลี่ยนแปลง
11. **A.8.33** - Test Information Security | ความปลอดภัยสารสนเทศทดสอบ

---

## Document Approval | การอนุมัติเอกสาร

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **CISO** | [TBD] | _____________ | ________ |
| **Management Representative** | [TBD] | _____________ | ________ |
| **ISMS Coordinator** | [TBD] | _____________ | ________ |

---

## Revision History | ประวัติการแก้ไข

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-01-20 | [TBD] | Initial draft with Appman E-KYC v2.0 |

---

## Next Review Date | วันที่ทบทวนครั้งถัดไป

**Scheduled Review** | **กำหนดทบทวน**: 2026-01-20 (Annual)

**Trigger for Immediate Review** | **เหตุการณ์ที่ต้องทบทวนทันที**:
- 🔴 **E-KYC provider change** | **การเปลี่ยนผู้ให้บริการ E-KYC**
- 🔴 Major system architecture change | การเปลี่ยนแปลงสถาปัตยกรรมระบบครั้งใหญ่
- 🔴 New PDPA/data protection regulation | กฎระเบียบคุ้มครองข้อมูล/PDPA ใหม่
- 🔴 Significant security incident | เหตุการณ์ด้านความปลอดภัยที่สำคัญ

---

**END OF STATEMENT OF APPLICABILITY**
**จบแถลงการณ์การประยุกต์ใช้มาตรการควบคุม**
