# Internal and External Issues | ประเด็นภายในและภายนอก

**Document Control | การควบคุมเอกสาร**

| Field | Value |
|-------|-------|
| **Document ID** | CONTEXT-002 |
| **Version** | 1.0 |
| **Effective Date** | [To be filled - วันที่มีผลบังคับใช้] |
| **Review Date** | [Semi-annual - ทบทวนทุก 6 เดือน] |
| **Document Owner** | Chief Information Security Officer (CISO) |
| **Approved By** | Chief Executive Officer (CEO) |
| **Classification** | Internal Use Only - ใช้ภายในองค์กรเท่านั้น |
| **Related Standards** | ISO 27001:2022 Clause 4.1 |

---

## 1. Purpose | วัตถุประสงค์

This document identifies and analyzes the **internal and external issues** that are relevant to Certogo's purpose and strategic direction, and that affect the ability to achieve the intended outcomes of the Information Security Management System (ISMS).

ISO 27001:2022 Clause 4.1 requires organizations to determine external and internal issues that can impact:
- The organization's ability to achieve ISMS objectives
- The organization's strategic direction
- Stakeholder expectations

**Thai | ไทย**: เอกสารนี้ระบุและวิเคราะห์ประเด็นภายในและภายนอกที่เกี่ยวข้องกับวัตถุประสงค์และทิศทางเชิงกลยุทธ์ของ Certogo

---

## 2. External Issues | ประเด็นภายนอก

External issues are factors originating outside the organization that can affect the ISMS.

### 2.1 Legal and Regulatory Environment | สภาพแวดล้อมทางกฎหมายและกฎระเบียบ

#### Issue 2.1.1: Thailand PDPA Enforcement 🔴

**Description**:
- Thailand Personal Data Protection Act (PDPA) B.E. 2562 (2019) fully enforced since June 1, 2022
- PDPA Section 26 classifies **biometric data** as **Sensitive Personal Data** requiring explicit consent
- PDPA Section 37 requires **72-hour breach notification** to PDPC (Personal Data Protection Committee)
- Penalties: Up to 5 million THB or up to 5% of annual revenue (whichever is higher)

**Impact on ISMS**:
- ✅ **Positive**: Clear legal framework drives investment in data protection controls
- ❌ **Negative**: Non-compliance risk (financial penalties, reputational damage)
- 🔴 **Critical**: Biometric data processed by E-KYC provider must comply with PDPA Section 26

**ISMS Response**:
- PDPA Compliance Policy (POL-003) established
- Data Protection Officer (DPO) appointed
- DPIA (Data Protection Impact Assessment) conducted for E-KYC biometric processing
- 30-day biometric data retention limit enforced (contractual with E-KYC provider)
- Incident response procedure includes PDPC notification (72-hour SLA)

**Monitoring**: DPO tracks PDPA regulatory updates quarterly

---

#### Issue 2.1.2: ISO 27001 Certification Requirements

**Description**:
- ISO 27001:2022 is internationally recognized standard for ISMS
- Many B2B customers (especially in banking, healthcare, government sectors) require suppliers to be ISO 27001 certified
- Certification requires third-party audit by accredited Certification Body (CB)

**Impact on ISMS**:
- ✅ **Positive**: Competitive advantage (customers prefer certified suppliers)
- ✅ **Positive**: Structured framework for security management
- ❌ **Negative**: Cost of certification (initial audit: 500k-1M THB, annual surveillance: 200k-400k THB)
- ❌ **Negative**: Resource commitment (documentation, evidence collection, audit preparation)

**ISMS Response**:
- ISO 27001:2022 implementation project underway (target: 6-12 months)
- All 93 Annex A controls addressed in Statement of Applicability (SoA)
- Internal audit program established

**Monitoring**: CISO tracks certification progress quarterly

---

#### Issue 2.1.3: Cross-Border Data Transfer Restrictions

**Description**:
- PDPA Section 28 restricts cross-border transfer of Personal Data
- Data can only be transferred abroad if:
  - Destination country has adequate data protection (per PDPC whitelist), OR
  - Explicit consent from data subject, OR
  - Standard contractual clauses approved by PDPC

**Impact on ISMS**:
- 🔴 **Critical**: Biometric data MUST remain in Thailand (no cross-border transfer)
- ❌ **Negative**: Limits cloud provider options (must have Thailand data center)
- ✅ **Positive**: Differentiator (Thai customers prefer local data storage)

**ISMS Response**:
- **Biometric data**: Thailand-only storage (contractual requirement with E-KYC provider) 🔴
- **Production data**: Primary storage in Thailand (Bangkok region)
- **Disaster recovery backups**: Singapore (ASEAN region, encrypted, customer consent in Privacy Notice)

**Monitoring**: DPO reviews data residency quarterly

---

### 2.2 Technology and Cybersecurity Landscape | สภาพแวดล้อมด้านเทคโนโลยีและความมั่นคงปลอดภัยไซเบอร์

#### Issue 2.2.1: Increasing Cyber Threats (Ransomware, Phishing, DDoS)

**Description**:
- Global increase in ransomware attacks targeting SaaS platforms
- Phishing attacks targeting employees to gain credentials
- DDoS (Distributed Denial of Service) attacks disrupting online services

**Impact on ISMS**:
- ❌ **Negative**: Risk of data breach, service disruption, financial loss
- ❌ **Negative**: Increased cost of security tools (EDR, SIEM, DDoS protection)
- ✅ **Positive**: Drives continuous improvement of security posture

**ISMS Response**:
- Multi-layered defense: Firewall, IDS/IPS, SIEM, EDR (Endpoint Detection and Response)
- Security awareness training (annual, includes phishing simulations)
- Incident response procedure with defined escalation paths
- Cyber insurance coverage (including third-party breaches)
- DDoS protection via cloud provider

**Monitoring**: CISO reviews threat intelligence reports monthly

---

#### Issue 2.2.2: Supply Chain Security Risks (Third-Party Providers)

**Description**:
- Increasing attacks targeting third-party suppliers (e.g., SolarWinds, Kaseya incidents)
- **E-KYC provider processes highly sensitive biometric data** - breach at provider could impact Certogo 🔴

**Impact on ISMS**:
- 🔴 **Critical**: Biometric data breach at E-KYC provider could violate PDPA, trigger PDPC notification
- ❌ **Negative**: Certogo has limited control over third-party security posture
- ❌ **Negative**: Dependence on E-KYC provider availability (99% SLA)

**ISMS Response**:
- **Supplier Security Policy** (POL-004) with rigorous assessment requirements
- **E-KYC provider requirements** 🔴:
  - ISO 27001 certification (mandatory)
  - 100+ question security assessment (minimum 80% score)
  - Quarterly security reviews
  - Annual penetration test report review
  - Data Processing Agreement (DPA) with security and PDPA clauses
- **Provider change capability**: 20-week migration procedure documented (A.5.22)
- **Cyber insurance**: Covers third-party breaches

**Monitoring**: CISO conducts quarterly supplier reviews (Critical suppliers like E-KYC provider)

---

#### Issue 2.2.3: Rapid Technology Evolution (Cloud, AI, Biometrics)

**Description**:
- Cloud computing enables scalability but introduces shared responsibility for security
- Biometric authentication (E-KYC) improves security but introduces privacy risks
- AI/ML used for fraud detection but requires large datasets (potential privacy concerns)

**Impact on ISMS**:
- ✅ **Positive**: Modern technologies improve security and user experience
- ❌ **Negative**: Rapid change requires continuous learning and adaptation
- 🔴 **Critical**: Biometric technology requires strict PDPA compliance

**ISMS Response**:
- Cloud security controls aligned with CSA (Cloud Security Alliance) best practices
- Biometric data processing via certified third-party (E-KYC provider) - Certogo does NOT store biometric data
- Technology training for IT and security teams (quarterly updates)

**Monitoring**: CTO reviews technology trends quarterly

---

### 2.3 Market and Competitive Environment | สภาพแวดล้อมด้านตลาดและการแข่งขัน

#### Issue 2.3.1: Customer Demand for Security Certifications

**Description**:
- B2B customers (especially in regulated industries: banking, healthcare, government) increasingly require suppliers to have ISO 27001 certification
- RFPs (Request for Proposals) often list ISO 27001 as mandatory requirement

**Impact on ISMS**:
- ✅ **Positive**: ISO 27001 certification is competitive differentiator
- ❌ **Negative**: Without certification, Certogo may lose deals to certified competitors

**ISMS Response**:
- Prioritize ISO 27001:2022 certification (target: 6-12 months)
- Communicate security posture to customers (security questionnaires, SOC 2 report if available)

**Monitoring**: Sales team tracks certification requirements in RFPs quarterly

---

#### Issue 2.3.2: Economic Uncertainty

**Description**:
- Global economic slowdown may reduce customer training budgets
- SME (Small and Medium Enterprise) customers may cut costs, including LMS subscriptions

**Impact on ISMS**:
- ❌ **Negative**: Reduced revenue may limit ISMS budget (security tools, training, audits)
- ✅ **Positive**: Security incidents are costly - maintaining ISMS may save money long-term

**ISMS Response**:
- Right-size security investments (focus on high-impact controls)
- Open-source tools where appropriate (e.g., CISO Assistant for GRC)
- Multi-year contracts with suppliers to lock in pricing

**Monitoring**: CFO reviews ISMS budget vs. actuals quarterly

---

### 2.4 Environmental and Physical Factors | ปัจจัยด้านสิ่งแวดล้อมและกายภาพ

#### Issue 2.4.1: Natural Disasters (Floods, Earthquakes in Thailand)

**Description**:
- Thailand experiences annual flooding (monsoon season: July-October)
- Earthquakes rare but possible

**Impact on ISMS**:
- ❌ **Negative**: Physical office disruption (employee access limited)
- ✅ **Positive**: Cloud infrastructure (Thailand + Singapore regions) provides resilience
- ❌ **Negative**: Data center outage if natural disaster affects cloud provider

**ISMS Response**:
- **100% cloud-hosted** - no production systems at office premises
- **Multi-region deployment**: Thailand (primary), Singapore (DR)
- **RTO (Recovery Time Objective)**: < 4 hours for critical services
- **RPO (Recovery Point Objective)**: < 1 hour (maximum data loss)
- **Employee remote work capability** (work-from-home policy established)

**Monitoring**: CTO reviews disaster recovery test results annually

---

#### Issue 2.4.2: COVID-19 Pandemic and Remote Work

**Description**:
- COVID-19 pandemic accelerated remote work adoption
- Employees working from home with varying network security and device security

**Impact on ISMS**:
- ❌ **Negative**: Increased attack surface (home networks less secure than office)
- ❌ **Negative**: Challenges with physical security (clear desk policy harder to enforce)
- ✅ **Positive**: Forced improvement of remote access security (VPN, MFA)

**ISMS Response**:
- **VPN (Virtual Private Network)** mandatory for all production access
- **Multi-factor authentication (MFA)** required for all admin and employee access
- **Endpoint security**: Full-disk encryption (FDE), EDR, automatic patching
- **Remote work policy** with security requirements (secure Wi-Fi, clear screen, no public networks)

**Monitoring**: IT reviews VPN and MFA compliance monthly

---

## 3. Internal Issues | ประเด็นภายใน

Internal issues are factors within the organization that can affect the ISMS.

### 3.1 Organizational Structure and Culture | โครงสร้างองค์กรและวัฒนธรรม

#### Issue 3.1.1: Small Security Team (Limited Resources)

**Description**:
- Certogo has [X] employees total, with [Y] dedicated security team members
- CISO role may be combined with other responsibilities (e.g., CTO + CISO)
- Limited budget for security tools and training compared to large enterprises

**Impact on ISMS**:
- ❌ **Negative**: Resource constraints limit depth of security controls
- ❌ **Negative**: Single points of failure (if key security personnel leave)
- ✅ **Positive**: Agility and fast decision-making (small team, less bureaucracy)

**ISMS Response**:
- **Prioritize high-impact controls** (focus on Critical and High risks: biometric data, E-KYC provider security)
- **Leverage automation**: SIEM, automated patching, Infrastructure-as-Code (IaC)
- **Outsource where appropriate**: External auditors, penetration testing, security training
- **Cross-training**: Multiple employees trained on each critical function (knowledge sharing)

**Monitoring**: HR and CISO review staffing levels quarterly

---

#### Issue 3.1.2: Growing Security Awareness Culture

**Description**:
- Security awareness is improving across the organization
- Employees complete mandatory training annually
- Incident reporting rate increasing (positive sign - employees are vigilant)

**Impact on ISMS**:
- ✅ **Positive**: Human firewall (employees detect and report phishing, suspicious activity)
- ✅ **Positive**: Fewer security incidents caused by employee negligence
- ❌ **Negative**: Training time diverts from productive work (acceptable trade-off)

**ISMS Response**:
- **Mandatory security training**:
  - Tier 1: General awareness (1h, all employees, annually)
  - Tier 2: PDPA & biometric data handling 🔴 (2h, roles with PII access, annually)
  - Tier 3: Secure coding (4h, developers, annually)
- **Phishing simulations** (quarterly)
- **Security champions program** (volunteer employees in each department promote security)

**Monitoring**: HR tracks training completion rate (target: 100%)

---

### 3.2 Information Technology and Systems | เทคโนโลยีสารสนเทศและระบบ

#### Issue 3.2.1: Reliance on Cloud Infrastructure

**Description**:
- Certogo operates 100% on cloud infrastructure (AWS/Azure/GCP - specify)
- No on-premises servers or data centers
- Shared responsibility model: Cloud provider (infrastructure), Certogo (application, data)

**Impact on ISMS**:
- ✅ **Positive**: Scalability, high availability, automatic infrastructure patching (by cloud provider)
- ✅ **Positive**: Cloud provider is ISO 27001 and SOC 2 certified (inherits security controls)
- ❌ **Negative**: Dependence on cloud provider (outage impacts Certogo)
- ❌ **Negative**: Configuration errors by Certogo can expose data (misconfigured S3 buckets, etc.)

**ISMS Response**:
- **Cloud Security Posture Management (CSPM)** tools to detect misconfigurations
- **Infrastructure-as-Code (IaC)** for reproducible and auditable deployments
- **Multi-region deployment** (Thailand + Singapore) for resilience
- **Cloud provider SLA monitoring** (99.9% uptime target)

**Monitoring**: CTO reviews cloud security posture monthly

---

#### Issue 3.2.2: Integration with Third-Party E-KYC Provider 🔴

**Description**:
- Certogo integrates with Appman (current E-KYC provider) via API
- **E-KYC provider processes biometric data** on Certogo's behalf
- Certogo has **NO direct control** over E-KYC provider's security controls
- **E-KYC provider may change in the future** (business decision or provider performance issues)

**Impact on ISMS**:
- 🔴 **Critical**: Biometric data breach at E-KYC provider could violate PDPA and damage Certogo's reputation
- ❌ **Negative**: Dependence on E-KYC provider availability (99% SLA)
- ❌ **Negative**: Provider change is complex (20-week migration procedure)
- ✅ **Positive**: Certogo does NOT store biometric data (reduces risk)

**ISMS Response**:
- **Rigorous supplier management**:
  - E-KYC provider MUST be ISO 27001 certified
  - 100+ question security assessment
  - Quarterly security reviews
  - Data Processing Agreement (DPA) with PDPA-compliant clauses 🔴
- **Provider change readiness**:
  - 20-week migration procedure documented (A.5.22)
  - Provider-agnostic requirements (any E-KYC provider must meet same standards)
  - Supplier assessment framework reusable for new providers
- **Continuous monitoring**:
  - E-KYC service availability monitored (API health checks every 5 minutes)
  - Quarterly review of Appman's ISO 27001 certificate expiration

**Monitoring**: CISO conducts quarterly E-KYC provider reviews

---

#### Issue 3.2.3: Technical Debt in Legacy Systems

**Description**:
- Some components of LMS platform built on older technology stacks
- Legacy code may lack modern security features (e.g., parameterized queries, CSRF protection)
- Refactoring requires significant development effort

**Impact on ISMS**:
- ❌ **Negative**: Vulnerabilities in legacy code (SQL injection, XSS)
- ❌ **Negative**: Difficult to patch or upgrade (tight coupling, lack of tests)
- ✅ **Positive**: Recognized issue - refactoring roadmap exists

**ISMS Response**:
- **Prioritized refactoring**: High-risk components first (authentication, payment processing, E-KYC integration)
- **Compensating controls**: Web Application Firewall (WAF) to mitigate known vulnerabilities
- **Security testing**: SAST (Static Application Security Testing), DAST (Dynamic), penetration testing
- **Secure coding training**: Developers trained on OWASP Top 10

**Monitoring**: CTO tracks refactoring progress quarterly

---

### 3.3 Processes and Documentation | กระบวนการและเอกสาร

#### Issue 3.3.1: ISMS Documentation Maturity

**Description**:
- ISMS documentation recently created (Phase 1 complete: policies, SoA, risk assessment, procedures)
- Some documentation is comprehensive (8,000+ lines of policies)
- Evidence collection is ongoing (20% complete)

**Impact on ISMS**:
- ✅ **Positive**: Strong foundation for ISO 27001 certification
- ❌ **Negative**: Documentation needs to be socialized and operationalized (employees must read and follow)
- ❌ **Negative**: Evidence gaps need to be filled (signed policies, training records, audit reports)

**ISMS Response**:
- **Documentation rollout plan**:
  - CEO signs policies (convert markdown to PDF)
  - All employees acknowledge policies (track in HR system)
  - Training on key policies (Information Security, PDPA, Acceptable Use)
- **Evidence collection sprint**: Dedicate Q[X] to collecting all required evidence for audit
- **CISO Assistant** (optional GRC tool) for tracking compliance progress

**Monitoring**: CISO tracks documentation completion (target: 100% by [Date])

---

#### Issue 3.3.2: Incident Response Capability

**Description**:
- Incident response procedure documented
- Incident response team designated (CISO, CTO, DPO, IT Manager)
- Tabletop exercises NOT yet conducted (planned)

**Impact on ISMS**:
- ✅ **Positive**: Clear escalation paths and roles defined
- ❌ **Negative**: Untested procedure (may have gaps discovered during real incident)

**ISMS Response**:
- **Tabletop exercise** (simulate biometric data breach at E-KYC provider) 🔴 - planned for Q[X]
- **PDPC notification drill** (practice 72-hour notification requirement)
- **Incident response retainer** (external cybersecurity firm on standby for major incidents)

**Monitoring**: CISO schedules annual tabletop exercise

---

### 3.4 People and Competence | บุคลากรและความสามารถ

#### Issue 3.4.1: Cybersecurity Skills Gap

**Description**:
- Global shortage of cybersecurity professionals
- Difficult to hire and retain skilled security engineers in Thailand
- Certogo competes with larger organizations for talent

**Impact on ISMS**:
- ❌ **Negative**: Difficulty filling open security positions
- ❌ **Negative**: Risk of key person dependency (CISO or senior security engineer leaves)
- ✅ **Positive**: Opportunity to develop internal talent (upskilling programs)

**ISMS Response**:
- **Competitive compensation** for security roles
- **Training and development**: Certifications (CISSP, CISM, CEH), conferences, online courses
- **Knowledge management**: Document tribal knowledge, cross-training
- **Outsourcing**: External consultants for specialized tasks (penetration testing, DPIA)

**Monitoring**: HR tracks security team attrition rate (target: < 10% annually)

---

#### Issue 3.4.2: Data Protection Officer (DPO) Competence 🔴

**Description**:
- PDPA Section 40 requires appointment of Data Protection Officer (DPO)
- DPO must have expert knowledge of data protection law and practices
- Certogo DPO is [internal employee / external consultant - specify]

**Impact on ISMS**:
- ✅ **Positive**: DPO ensures PDPA compliance (especially for biometric data)
- ❌ **Negative**: Limited DPO resources (if internal, may have other responsibilities)
- 🔴 **Critical**: DPO must be competent to handle biometric data PDPA Section 26 requirements

**ISMS Response**:
- **DPO training**: PDPA certification (if available in Thailand), attend PDPC workshops
- **Legal support**: External legal counsel for complex PDPA questions
- **DPO authority**: Direct line to CEO, empowered to escalate PDPA violations

**Monitoring**: DPO competence reviewed annually (by CEO)

---

## 4. SWOT Analysis Summary | สรุปการวิเคราะห์ SWOT

### Strengths | จุดแข็ง
- ✅ Strong ISMS documentation (Phase 1 complete: 8,000+ lines of policies, 93 controls documented)
- ✅ Cloud-native architecture (scalable, resilient, inherits cloud provider security)
- ✅ Security-conscious leadership (CEO supports ISMS, adequate budget)
- ✅ Biometric data NOT stored by Certogo (reduces PDPA risk) 🔴

### Weaknesses | จุดอ่อน
- ❌ Small security team (limited resources)
- ❌ Technical debt in legacy systems (refactoring needed)
- ❌ Evidence collection ongoing (only 20% complete)
- ❌ Incident response procedure untested (tabletop exercise needed)

### Opportunities | โอกาส
- ✅ ISO 27001 certification as competitive differentiator
- ✅ PDPA compliance improves customer trust
- ✅ Open-source GRC tools (CISO Assistant) reduce costs
- ✅ Growing security awareness culture

### Threats | อุปสรรค
- ❌ Increasing cyber threats (ransomware, phishing, supply chain attacks)
- ❌ E-KYC provider breach risk (biometric data compromise) 🔴
- ❌ PDPA penalties (up to 5% of revenue)
- ❌ Economic uncertainty (customer budget cuts)

---

## 5. Monitoring and Review | การติดตามและทบทวน

### 5.1 Review Schedule | กำหนดการทบทวน

This Internal and External Issues analysis shall be reviewed:

- **Semi-annually** (every 6 months) - by CISO, approved by CEO
- **Ad-hoc** when significant changes occur:
  - Major regulatory changes (PDPA updates, new ISO 27001 version)
  - Significant external events (major cyber attack affecting industry, economic crisis)
  - Internal changes (organizational restructuring, E-KYC provider change 🔴)

### 5.2 Responsibility | ความรับผิดชอบ

- **CISO**: Leads the review, coordinates input from stakeholders
- **Stakeholders**: CEO, CTO, DPO, CFO, HR Manager provide input
- **CEO**: Approves final analysis

### 5.3 Integration with ISMS | การบูรณาการกับ ISMS

This analysis informs:
- **Risk Assessment**: External and internal issues drive risk identification
- **ISMS Objectives**: Objectives set to address key issues
- **Control Selection**: Controls chosen to mitigate threats and leverage opportunities
- **Management Review**: Issues discussed in annual management review

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
**Next Review**: [Date + 6 months]
