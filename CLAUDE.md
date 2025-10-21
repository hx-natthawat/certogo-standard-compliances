# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## Project Overview

This repository contains **ISO 27001:2022 compliance documentation** for **Certogo Co., Ltd.**, a B2B/B2C SaaS/PaaS Learning Management System (LMS) platform that integrates with **Appman E-KYC services** for identity verification using biometric data.

**Critical Context**: The E-KYC provider (currently Appman) processes highly sensitive biometric data (facial images, ID card scans) subject to Thailand's PDPA (Personal Data Protection Act B.E. 2562). **The E-KYC provider may change in the future**, so all documentation must account for provider changeability.

**Target**: ISO 27001:2022 certification within 6-12 months
**Current Status**: Phase 1 Complete (Documentation: 100%), Overall: 40% ready

---

## Architecture & Document Structure

### Two-Tier Document System

This repository uses **separation of concerns** between documentation and evidence:

1. **`/standards/iso27001/`** - Master documentation (version-controlled markdown)
   - What was designed/planned
   - Templates and guides
   - Updated during development

2. **`/evidence/`** - Operational evidence (signed PDFs, records)
   - What was executed/implemented
   - Signed policies with CEO approval
   - Audit records and proof of compliance
   - What auditors physically review

### ISO 27001 Clause-Aligned Structure

The `/standards/iso27001/` directory mirrors ISO 27001:2022 structure:

```
01-context/          # Clause 4 - Context of organization
02-policies/         # Clause 5.2 - Information security policies (3 completed)
03-planning/         # Clause 6 - Risk assessment & treatment
04-procedures/       # Clause 8 - Operational procedures
05-annex-a-controls/ # Annex A - All 93 controls implementation guides
06-templates/        # Supporting templates (audit checklists, etc.)
07-ciso-assistant/   # GRC tool integration
```

**Key Files**:
- `README.md` - Main documentation hub, current status
- `TODO.md` - Prioritized task tracking (4 priority levels)
- `05-annex-a-controls/statement-of-applicability.md` - **MANDATORY** for ISO 27001 (all 93 controls)

---

## Critical Domain Concepts

### E-KYC Provider Changeability 🔴

**THE MOST IMPORTANT REQUIREMENT**: All documentation must address that Appman (current E-KYC provider) may be replaced in the future.

**How to Address**:
1. Use "current E-KYC provider: Appman" instead of just "Appman"
2. Reference the **20-week migration procedure** (in A.5.22 Organizational Controls)
3. Mark E-KYC controls with 🔴 or 🔄 (shared responsibility)
4. Include provider-agnostic security requirements (100+ question assessment)
5. Note documentation update triggers when provider changes

**Files with Migration Procedures**:
- `/standards/iso27001/05-annex-a-controls/A.5-organizational-controls.md` (Section A.5.22 - detailed 5-phase procedure)
- `/standards/iso27001/02-policies/supplier-security-policy.md` (Section 3.3 - high-level overview)

### Biometric Data Handling 🔴

**PDPA Section 26 Sensitive Data**: Facial images and ID card scans require:
- **Explicit consent** (separate from general consent)
- **30-day maximum retention** at E-KYC provider
- **Thailand data localization** (no cross-border transfer)
- **72-hour breach notification** to PDPC (Personal Data Protection Committee)
- **Certificate of deletion** upon data deletion

**Critical Files**:
- `/standards/iso27001/02-policies/pdpa-compliance-policy.md` (3,100 lines)
- `/standards/iso27001/03-planning/risk-assessment-template.md` (6 E-KYC risks: R-001 to R-012)

### Shared Responsibility Model

**Certogo** (Data Controller):
- Receives only E-KYC verification result (Pass/Fail)
- **Does NOT store biometric data**
- Responsible for supplier security assessment and monitoring

**Appman** (Data Processor):
- Processes and stores biometric data (max 30 days)
- Must be ISO 27001 certified
- Subject to quarterly security reviews

### Bilingual Requirement 🇹🇭

**ALL documentation MUST be bilingual (Thai/English)**:
- Format: "**Term** | **คำศัพท์ไทย**"
- English: Technical terms, ISO compliance keywords (for international auditors)
- Thai: Local understanding (for Thai auditors from certification bodies)

**Example**:
```markdown
## Risk Assessment | การประเมินความเสี่ยง

**Confidentiality** | **ความลับ**
```

---

## Working with This Repository

### Creating New Policies

**Location**: `/standards/iso27001/02-policies/`

**Template Structure** (see existing policies):
1. **Document Control** table (ID, version, owner, approver)
2. **Purpose and Scope** (bilingual)
3. **Roles and Responsibilities** (CEO, CISO, DPO, CTO, etc.)
4. **Policy Details** (specific requirements)
5. **E-KYC Integration Requirements** 🔴 (if applicable)
6. **Approval Signatures** section (CEO, CISO, DPO as relevant)

**Mandatory Policies** (3 completed, 6 remaining):
- ✅ Information Security Policy (POL-001) - 2,100 lines
- ✅ Supplier Security Policy (POL-004) - 2,800 lines
- ✅ PDPA Compliance Policy (POL-003) - 3,100 lines
- ⏳ Access Control Policy (POL-002)
- ⏳ Incident Response Policy (POL-005)
- ⏳ Business Continuity Policy (POL-006)
- ⏳ Asset Management Policy (POL-007)
- ⏳ Cryptography Policy (POL-008)
- ⏳ Acceptable Use Policy (POL-009)

**After Creating**: Move signed PDF version to `/evidence/policies/POL-XXX-[name]-signed.pdf`

### Creating New Procedures

**Location**: `/standards/iso27001/04-procedures/`

**Critical Procedures Needed**:
- **Data Deletion Procedure** 🔴 (for biometric data - 30-day retention)
- **E-KYC Provider Change Procedure** 🔴 (reference A.5.22 for details)
- **Incident Response Procedure**
- **Backup and Recovery Procedure**
- **Change Management Procedure**

**Format**: Similar to policies but more operational (step-by-step instructions)

### Updating Risk Assessment

**File**: `/standards/iso27001/03-planning/risk-assessment-template.md`

**6 E-KYC Specific Risks**:
- **R-001** 🔴: Biometric data breach at E-KYC provider (Critical)
- **R-002**: E-KYC service outage (High)
- **R-005**: Loss of E-KYC provider certifications (High)
- **R-009**: Unauthorized sub-processing (Medium)
- **R-011** 🔴: E-KYC provider change disruption (High)
- **R-012** 🔴: Biometric data deletion failure (High)

**Risk Scoring**:
- Likelihood: 1-5 scale (1=Rare, 5=Almost Certain)
- Impact: 1-5 scale across 6 dimensions (Confidentiality, Integrity, Availability, Financial, Reputational, Legal)
- Risk Level: Likelihood × Impact = 1-25
  - Critical (16-25) 🔴: Zero tolerance
  - High (10-15) 🟠: Treat within 30 days
  - Medium (5-9) 🟡: Treat within 90 days
  - Low (1-4) 🟢: May accept with justification

### Updating Statement of Applicability (SoA)

**File**: `/standards/iso27001/05-annex-a-controls/statement-of-applicability.md`

**MANDATORY ISO 27001 document** covering all 93 Annex A controls.

**Status Indicators**:
- ✅ **Fully Applicable**: Control implemented by Certogo
- 🔶 **Partially Applicable**: Shared with E-KYC provider (mark with 🔄)
- ❌ **Not Applicable**: Not relevant (justify)
- 🔴 **Critical**: E-KYC or biometric data related
- 🔄 **Shared**: Both Certogo and Appman responsible

**When to Update**:
- E-KYC provider changes (update provider name in controls)
- New security controls implemented
- Risk assessment changes

---

## Key Terminology

| Term | Meaning | Thai |
|------|---------|------|
| **PDPA** | Thailand Personal Data Protection Act B.E. 2562 (2019) | พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล |
| **PDPC** | Personal Data Protection Committee (regulator) | สำนักงานคณะกรรมการคุ้มครองข้อมูลส่วนบุคคล |
| **DPA** | Data Processing Agreement (contract with data processors) | สัญญาการประมวลผลข้อมูล |
| **DPIA** | Data Protection Impact Assessment (required for biometric data) | การประเมินผลกระทบด้านการคุ้มครองข้อมูล |
| **ROPA** | Record of Processing Activities (PDPA requirement) | บันทึกกิจกรรมการประมวลผลข้อมูล |
| **SoA** | Statement of Applicability (93 controls) | แถลงการณ์การประยุกต์ใช้ |
| **ISMS** | Information Security Management System | ระบบการจัดการความมั่นคงปลอดภัยสารสนเทศ |
| **CB** | Certification Body (auditor organization) | หน่วยรับรอง |
| **CISO** | Chief Information Security Officer | หัวหน้าเจ้าหน้าที่ความมั่นคงปลอดภัยสารสนเทศ |
| **DPO** | Data Protection Officer (PDPA requirement) | เจ้าหน้าที่คุ้มครองข้อมูลส่วนบุคคล |

---

## Document Conventions

### Priority Markers
- 🔴 **Critical**: Biometric data, E-KYC provider, PDPA Section 26
- 🟠 **High**: PII, supplier security, risk treatment
- 🟡 **Medium**: General security controls
- 🟢 **Low**: Nice-to-have improvements

### Status Markers
- ✅ **Complete**: Fully implemented/documented
- 🔄 **In Progress**: Currently being worked on
- ⏳ **Planned**: Identified but not started
- ❌ **Not Applicable**: Justified exclusion

### Shared Responsibility
- 🔄 **Shared Control**: Both Certogo and E-KYC provider responsible
- Example: A.5.19 (Supplier security) - Certogo assesses, Appman implements

---

## Evidence Collection

**Location**: `/evidence/` (separate from documentation)

**Required Evidence for Audit**:

### Policies (Signed PDFs)
- `/evidence/policies/POL-001-information-security-policy-signed.pdf` (CEO signature)
- `/evidence/policies/POL-003-pdpa-compliance-policy-signed.pdf` (CEO + DPO)
- `/evidence/policies/POL-004-supplier-security-policy-signed.pdf` (CEO + CISO)

### E-KYC Provider Documentation 🔴
- `/evidence/contracts/appman-dpa-signed.pdf` (Data Processing Agreement)
- `/evidence/contracts/appman-iso27001-certificate.pdf` (ISO 27001 cert)
- `/evidence/records/supplier-monitoring/ekyc-quarterly-reviews/` (Quarterly security reviews)

### PDPA Compliance
- `/evidence/records/ropa.xlsx` (Record of Processing Activities)
- `/evidence/records/dpia/ekyc-biometric-dpia.pdf` (DPIA for biometric data)
- `/evidence/records/data-subject-requests.xlsx` (Data subject rights requests)

### Operational Records
- `/evidence/records/risk-assessment-2024.xlsx` (Annual risk assessment)
- `/evidence/records/management-review-2024-Q1.pdf` (Management review minutes)
- `/evidence/records/internal-audit-2024.pdf` (Internal audit reports)
- `/evidence/records/supplier-register.xlsx` (All suppliers with risk classification)

---

## Common Mistakes to Avoid

1. **Don't hardcode "Appman"** - Always use "current E-KYC provider: Appman" or "E-KYC provider (Appman)"

2. **Don't forget bilingual format** - Every heading, term, and section needs Thai translation

3. **Don't miss E-KYC warnings** - Add ⚠️ **IMPORTANT**: Provider may change notice in relevant sections

4. **Don't create evidence files in `/standards/`** - Evidence goes in `/evidence/` (signed docs, records)

5. **Don't skip 🔴 markers** - Critical items (biometric data, E-KYC, PDPA) must be clearly marked

6. **Don't assume 30-day retention** - Always verify biometric data retention in DPA and mark as contractual requirement

7. **Don't reference specific provider features** - Use generic E-KYC requirements (facial recognition, liveness detection, OCR) not Appman-specific features

---

## Audit Preparation

**Primary Checklist**: `/standards/iso27001/06-templates/audit-preparation-checklist.md` (153 items)

**Critical Items for Auditors**:
1. Statement of Applicability (SoA) - All 93 controls
2. Signed Information Security Policy (CEO signature)
3. Risk Assessment (6 E-KYC risks documented)
4. Appman ISO 27001 certificate 🔴
5. Data Processing Agreement with Appman 🔴
6. Quarterly supplier reviews (last 4 quarters) 🔴
7. DPIA for biometric data processing 🔴
8. Training records (PDPA & biometric data handling) 🔴

**Interview Preparation**:
- CISO: E-KYC provider security assessment process, 20-week migration procedure
- DPO: PDPA compliance, data subject rights, biometric data retention verification
- CTO: Technical controls, encryption, data localization

---

## Task Tracking

**File**: `/TODO.md`

**4 Priority Levels**:
- 🔴 **Priority 1**: Immediate (Week 1-4) - E-KYC docs, policies, internal audit
- 🟠 **Priority 2**: High (Month 2-3) - Evidence collection, training
- 🟡 **Priority 3**: Medium (Month 3-6) - Remaining policies, management review
- 🟢 **Priority 4**: Low (Month 6-12) - Certification audit, optional guides

**Update TODO.md** when:
- Completing tasks (move to ✅ COMPLETED section)
- Identifying new tasks (add with priority, owner, due date)
- Blockers arise (document in task notes)

---

## Integration with CISO Assistant (Optional)

**Setup Guide**: `/standards/iso27001/07-ciso-assistant-integration/setup-guide.md`

**CISO Assistant** is an open-source GRC (Governance, Risk, Compliance) platform that can:
- Track compliance status for all 93 controls
- Manage risk assessment (6 E-KYC risks)
- Generate evidence reports for auditors
- Monitor supplier security (E-KYC provider)

**When to Use**:
- For teams with 5+ people (coordination benefits)
- If managing multiple frameworks (ISO 27001 + SOC 2, etc.)
- When tracking 100+ action items

**Installation**: Docker-based (self-hosted recommended for biometric data sensitivity)

---

## Questions to Ask When Unsure

1. **Does this involve biometric data?** → Mark 🔴, add PDPA considerations, 30-day retention
2. **Does this involve the E-KYC provider?** → Check if Appman-specific or provider-agnostic
3. **Is this a new policy?** → Use bilingual template, get CEO signature, move to `/evidence/policies/`
4. **Is this a shared control?** → Mark 🔄, clarify Certogo vs. Appman responsibilities
5. **Should this be in `/standards/` or `/evidence/`?** → Documentation = `/standards/`, signed/executed = `/evidence/`

---

## Current Project Status

**Phase 1 (Documentation)**: ✅ 100% Complete
- 3 policies created (8,000+ lines, bilingual)
- Statement of Applicability (93 controls)
- Risk assessment template (6 E-KYC risks)
- Audit checklist (153 items)

**Phase 2 (Evidence Collection)**: 🔄 20% In Progress
- Policies need CEO signatures
- E-KYC provider docs needed from Appman
- Risk assessment needs execution

**Overall Readiness**: 40% → **Target: 100% in 6-12 months**

---

## Next Priority Tasks

1. **Create ISMS context documents** (01-context/ - scope, issues, stakeholders)
2. **Create core procedures** (04-procedures/ - data deletion, incident response, backup)
3. **Sign policies** (convert to PDF, get CEO approval)
4. **Execute risk assessment** (use template, get CISO approval)
5. **Collect Appman documentation** (ISO cert, DPA, quarterly reviews)

See `/TODO.md` for complete task breakdown with owners and due dates.
