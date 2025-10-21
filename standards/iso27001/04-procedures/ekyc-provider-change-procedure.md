# E-KYC Provider Change Procedure | ขั้นตอนการเปลี่ยนผู้ให้บริการ E-KYC

**Document Control | การควบคุมเอกสาร**

| Field | Value |
|-------|-------|
| **Document ID** | PROC-002 |
| **Version** | 1.0 |
| **Effective Date** | [To be filled - วันที่มีผลบังคับใช้] |
| **Review Date** | [Annual - ทบทวนทุกปี] |
| **Document Owner** | Chief Information Security Officer (CISO) |
| **Approved By** | Chief Executive Officer (CEO) |
| **Classification** | Internal Use Only - ใช้ภายในองค์กรเท่านั้น |
| **Related Standards** | ISO 27001:2022 A.5.22, PDPA Sections 26-28 |

---

## 1. Purpose | วัตถุประสงค์

This procedure defines the process for **changing the E-KYC (Electronic Know Your Customer) service provider** that processes **biometric data** (facial images, ID card scans) on behalf of Certogo.

**Why This Procedure is Critical** 🔴:
- E-KYC provider processes **PDPA Section 26 Sensitive Personal Data** (biometric data)
- Provider change must ensure **zero data loss and zero security incidents**
- Migration must maintain **business continuity** (E-KYC service remains available)
- Biometric data must be **deleted from old provider** (30-day maximum retention)
- **ISO 27001 documentation must be updated** (SoA, policies, risk assessment)

**Current E-KYC Provider**: Appman Co., Ltd.

**⚠️ IMPORTANT**: This procedure is provider-agnostic. It can be used to migrate from any E-KYC provider to any other provider.

**Thai | ไทย**: ขั้นตอนนี้กำหนดกระบวนการเปลี่ยนผู้ให้บริการ E-KYC ซึ่งประมวลผลข้อมูลไบโอเมตริกซ์แทน Certogo

---

## 2. Scope | ขอบเขต

### 2.1 In Scope | อยู่ในขอบเขต

- E-KYC service provider change (digital identity verification using biometric data)
- All phases: Planning → Integration → Testing → Migration → Decommissioning → Post-Migration
- Technical, security, legal, and compliance aspects
- Documentation updates (policies, SoA, risk assessment)

### 2.2 Out of Scope | นอกขอบเขต

- Other third-party supplier changes (cloud provider, payment gateway, etc.)
- Internal system changes (different procedure)

---

## 3. Triggers for Provider Change | เหตุการณ์ที่ทำให้เปลี่ยนผู้ให้บริการ

### 3.1 Mandatory Triggers 🔴 (MUST change provider)

| Trigger | Reason | Urgency |
|---------|--------|---------|
| **Loss of ISO 27001 certification** | Contractual requirement - Critical supplier must be ISO 27001 certified | **Immediate** (30-day notice to terminate) |
| **PDPA violation or data breach** | Biometric data compromised - PDPA Section 26 violation | **Immediate** (terminate contract, initiate emergency migration) |
| **Repeated SLA failures** | Availability < 95% for 2 consecutive months (contract allows termination) | **30 days** (termination for cause) |
| **Material breach of DPA** | E.g., cross-border data transfer without consent, retention > 30 days | **Immediate** |

### 3.2 Discretionary Triggers 🟠 (MAY change provider)

| Trigger | Reason | Urgency |
|---------|--------|---------|---------|
| **Better alternative available** | New provider offers better accuracy, lower cost, or more features | **90 days** (termination for convenience) |
| **Cost increases** | E-KYC provider raises prices beyond acceptable range | **90 days** (renegotiate or migrate) |
| **Strategic decision** | Certogo decides to in-source E-KYC capability or consolidate vendors | **90 days** |
| **Performance issues** | E-KYC accuracy declining, customer complaints increasing | **90 days** |

---

## 4. Roles and Responsibilities | บทบาทและความรับผิดชอบ

| Role | Responsibilities |
|------|------------------|
| **Chief Executive Officer (CEO)** | - Final approval for provider change (especially if discretionary)<br>- Budget approval (migration costs)<br>- Sign new DPA with new provider |
| **Chief Information Security Officer (CISO)** | - Lead provider change project<br>- Conduct security assessment of new provider<br>- Coordinate with old provider (Appman) for data deletion<br>- Update ISO 27001 documentation |
| **Data Protection Officer (DPO)** | - Ensure PDPA compliance throughout migration<br>- Review new provider's DPA<br>- Verify biometric data deletion from old provider 🔴<br>- Conduct DPIA for new provider |
| **Chief Technology Officer (CTO)** | - Lead technical integration (API development, testing)<br>- Coordinate with DevOps for deployment<br>- Business continuity planning (zero downtime migration) |
| **Procurement / Vendor Management** | - Negotiate contract with new provider<br>- Terminate contract with old provider<br>- Manage transition period (overlap if needed) |
| **Legal / Compliance** | - Review new provider's DPA and service agreement<br>- Terminate old provider's contract (legal process)<br>- Ensure contractual compliance |
| **Engineering Team** | - Develop API integration with new provider<br>- Conduct security testing<br>- Deploy migration in phases (10% → 50% → 100%) |
| **Customer Support** | - Communicate with B2C users (if E-KYC process changes)<br>- Handle customer inquiries during migration |

---

## 5. Migration Timeline Overview | ภาพรวมระยะเวลาการย้าย

**Total Duration**: **14-22 weeks** (3.5-5.5 months)

**Critical Path**: Provider selection (8 weeks) → Integration (6 weeks) → Migration (4 weeks) → Decommissioning (2 weeks) → Post-review (2 weeks)

```
PHASE 1: Pre-Change Planning (Weeks 1-8)
├─ New provider selection
├─ Security assessment
├─ Contract negotiation
└─ Go/No-Go decision

PHASE 2: Technical Integration (Weeks 9-14)
├─ API development
├─ Testing (functional, performance, security, compliance)
└─ Certogo staff training

PHASE 3: Parallel Run & Migration (Weeks 15-18)
├─ Week 15-16: 10% traffic to new provider
├─ Week 17: 50% traffic
├─ Week 18: 100% traffic (old provider on standby)
└─ Rollback criteria defined

PHASE 4: Old Provider Decommissioning (Week 18)
├─ Data deletion verification 🔴
├─ API keys revoked
├─ Network access removed
└─ Contract terminated

PHASE 5: Post-Migration Review (Weeks 19-20)
├─ Performance comparison
├─ Lessons learned
└─ Documentation updates
```

**NOTE**: For detailed 5-phase procedure, see `/standards/iso27001/05-annex-a-controls/A.5-organizational-controls.md` Section A.5.22

---

## 6. PHASE 1: Pre-Change Planning (Weeks 1-8)

### 6.1 Initiate Provider Change Project (Week 1)

**Actions**:
1. **CEO Approval**: Document business case, get CEO approval to proceed
2. **Project Team Formation**: Assign roles (CISO as project lead, CTO, DPO, Procurement, Legal)
3. **Kickoff Meeting**: Set timeline, budget, success criteria

**Deliverables**:
- Project charter (scope, objectives, timeline, budget, risks)
- Stakeholder communication plan

---

### 6.2 New Provider Selection (Weeks 2-4)

#### Step 1: Identify Candidate Providers (Week 2)

**Actions**:
1. Market research: Identify 3-5 E-KYC providers in Thailand/ASEAN
2. Pre-qualification:
   - ✅ ISO 27001 certified (mandatory)
   - ✅ Thailand data center (biometric data localization - PDPA requirement)
   - ✅ Facial recognition + liveness detection + ID card OCR capabilities
   - ✅ API-based integration (RESTful, OAuth 2.0)
3. Request proposals (RFP) from qualified providers

**Deliverables**: Shortlist of 2-3 providers

---

#### Step 2: Security Assessment (Week 3-4)

**Actions**:
1. **Security Questionnaire** (100+ questions) - See Supplier Security Policy (POL-004) Section 5.2
   - Categories: Data protection, access control, infrastructure, logging, incident response, business continuity, compliance
   - **Scoring**: Minimum 80/100 to proceed

2. **Document Review**:
   - ISO 27001 certificate (valid, not expired)
   - SOC 2 Type II report (if available)
   - Latest penetration test report (executive summary)
   - PDPA compliance documentation
   - Business continuity plan

3. **Reference Checks**:
   - Contact 2-3 existing customers
   - Ask about: Uptime, accuracy, support responsiveness, incidents

4. **On-Site or Virtual Audit** (if score 80-89%):
   - If score ≥ 90%, audit is optional
   - Audit checklist: Infrastructure, access controls, encryption, biometric data deletion process 🔴

**Deliverables**:
- Security assessment report for each provider (score, findings, risks)
- Recommendation: Which provider to select

---

#### Step 3: Scoring and Selection (Week 4)

**Scoring Criteria** (Total: 100 points):

| Category | Weight | Evaluation |
|----------|--------|------------|
| **Security Posture** | 30 points | ISO 27001 cert (10), Security assessment score (10), Incident history (10) |
| **Technical Capabilities** | 20 points | Accuracy (10), API quality (5), Features (5) |
| **PDPA Compliance** | 20 points | Data localization (10), Biometric retention ≤ 30 days (10) |
| **Availability and Performance** | 15 points | SLA (≥ 99% - 10 points), Response time < 5 sec (5) |
| **Cost** | 10 points | Competitive pricing (10) |
| **Support** | 5 points | 24/7 support (3), Account manager (2) |

**Decision**:
- **Minimum 80/100 to proceed** with provider
- CISO recommends top provider to CEO
- CEO approves selection

**Deliverables**: Provider selection decision document

---

### 6.3 Contract Negotiation (Weeks 5-7)

**Actions**:

1. **Data Processing Agreement (DPA)** 🔴 - Legal + DPO review
   - Use template in Supplier Security Policy (POL-004) Appendix A
   - **Key clauses**:
     - Purpose limitation (identity verification only)
     - **Biometric data retention: 30 days maximum** 🔴
     - **Data localization: Thailand only** 🔴
     - Sub-processor approval (written consent required)
     - Security measures (AES-256, TLS 1.3, MFA, audit logs)
     - Audit rights (Certogo may audit annually)
     - **Certificate of deletion** upon termination 🔴
     - Incident notification (24 hours for biometric breaches)
     - Indemnification (provider liable for negligence)

2. **Service Level Agreement (SLA)**:
   - Availability: ≥ 99% uptime (measured monthly)
   - Performance: Verification response time < 5 seconds (95th percentile)
   - Support: 24/7 for Critical incidents
   - Penalties: Service credits for SLA breaches

3. **Master Services Agreement**:
   - Pricing (per transaction or monthly fee)
   - Contract term (e.g., 1 year, auto-renew)
   - Termination clauses (for cause, for convenience)
   - Transition assistance (if Certogo changes providers in future)

**Deliverables**:
- Signed DPA (CEO + new provider's authorized signatory)
- Signed SLA
- Signed Master Services Agreement

---

### 6.4 Go/No-Go Decision (Week 8)

**Actions**:
1. **Risk Assessment**:
   - Update risk register (R-011: E-KYC provider change disruption)
   - Identify mitigation measures
2. **Readiness Review**:
   - Security assessment: PASS (score ≥ 80)
   - Contracts signed: YES
   - Budget approved: YES
   - Technical team ready: YES
3. **Go/No-Go Decision**:
   - If all criteria met → **GO** (proceed to Phase 2)
   - If not → **NO-GO** (address gaps, re-assess)

**Deliverables**: Go/No-Go decision memo (CEO approval)

---

## 7. PHASE 2: Technical Integration (Weeks 9-14)

### 7.1 API Development (Weeks 9-11)

**Actions**:
1. **API Integration Development**:
   - Study new provider's API documentation
   - Develop integration layer (wrapper service)
   - Implement authentication (OAuth 2.0 + JWT)
   - Implement request/response mapping
   - Implement error handling and retry logic

2. **Security Controls**:
   - API key management (secure storage, 90-day rotation)
   - Rate limiting (prevent abuse)
   - Request/response logging (exclude biometric data)
   - Monitoring and alerting

**Deliverables**:
- Integration code (reviewed and tested)
- API wrapper service deployed to staging environment

---

### 7.2 Testing (Weeks 12-14)

**Test Types**:

#### 7.2.1 Functional Testing (Week 12)
- **Happy path**: Submit ID card + selfie → Receive Pass/Fail result
- **Edge cases**: Blurry images, mismatched photos, expired ID cards
- **Error handling**: Timeout, network error, invalid response

**Pass Criteria**: 100% of test cases pass

---

#### 7.2.2 Performance Testing (Week 13)
- **Load test**: Simulate 1000 concurrent E-KYC requests
- **Response time**: Measure 95th percentile (target < 5 seconds)
- **Throughput**: Requests per second

**Pass Criteria**: Meets SLA (99% availability, < 5 sec response)

---

#### 7.2.3 Security Testing (Week 13)
- **Penetration test**: Attempt to bypass authentication, inject malicious data
- **Data encryption verification**: Confirm TLS 1.3 in transit
- **API key security**: Confirm not logged or exposed

**Pass Criteria**: No Critical or High vulnerabilities

---

#### 7.2.4 PDPA Compliance Testing (Week 14) 🔴
- **Biometric data handling**: Confirm Certogo does NOT store biometric data (only verification result)
- **Data localization**: Confirm new provider's Thailand data center is used
- **Consent verification**: Confirm user explicit consent is captured
- **Data deletion**: Test deletion request (confirm provider deletes within 30 days)

**Pass Criteria**: 100% PDPA compliant

---

**Deliverables**:
- Test reports (functional, performance, security, PDPA compliance)
- Issues log (all Critical/High issues resolved)

---

### 7.3 Staff Training (Week 14)

**Who**: Customer Support, DevOps, Engineering

**Topics**:
- New E-KYC provider name and capabilities
- User experience changes (if any)
- How to troubleshoot issues
- Incident escalation procedures

**Deliverables**: Training completion records (100% of relevant staff)

---

## 8. PHASE 3: Parallel Run & Migration (Weeks 15-18)

### 8.1 Migration Strategy | กลยุทธ์การย้าย

**Approach**: **Gradual traffic shift** (canary deployment)

**Rationale**:
- Minimize risk (if new provider has issues, rollback quickly)
- Monitor new provider's performance with real traffic
- Build confidence before full migration

---

### 8.2 Week 15-16: 10% Traffic to New Provider

**Actions**:
1. **Deploy Configuration**:
   - Route 10% of E-KYC requests to new provider
   - Route 90% to old provider (Appman)
   - Selection: Random or specific user segment (e.g., new users)

2. **Monitoring** (Real-time dashboards):
   - **Availability**: New provider uptime vs. old provider
   - **Response time**: New provider < 5 sec (95th percentile)
   - **Accuracy**: Verification Pass/Fail rates (compare to old provider baseline)
   - **Error rate**: API errors (target < 1%)
   - **User complaints**: Customer support tickets related to E-KYC

3. **Daily Review Meeting** (CISO, CTO, Engineering):
   - Review metrics from previous 24 hours
   - Identify issues (if any)
   - Decide: Continue, pause, or rollback

**Rollback Criteria** 🔴:
- ❌ Availability < 95% (new provider)
- ❌ Response time > 10 seconds (95th percentile)
- ❌ Error rate > 5%
- ❌ **Biometric data breach or PDPA violation** (immediate rollback)

**If Rollback Triggered**:
- Revert to 100% old provider (Appman)
- Investigate root cause with new provider
- Fix issues, re-test, restart migration (add 2-4 weeks)

**Deliverables**:
- Week 15-16 migration report (metrics, issues, decision)

---

### 8.3 Week 17: 50% Traffic to New Provider

**Condition**: Week 15-16 successful (all metrics met, no rollback)

**Actions**:
1. **Increase Traffic**: 50% new provider, 50% old provider
2. **Monitoring**: Same as Week 15-16 (real-time dashboards, daily reviews)
3. **Rollback Criteria**: Same as Week 15-16

**Deliverables**: Week 17 migration report

---

### 8.4 Week 18: 100% Traffic to New Provider

**Condition**: Week 17 successful

**Actions**:
1. **Full Migration**:
   - Route 100% traffic to new provider
   - **Keep old provider (Appman) API available for 7 days** (rollback buffer)
2. **Monitoring**: Continuous for first 72 hours, then daily for 7 days
3. **Final Rollback Window**: 7 days (if Critical issue discovered)

**Go-Live Decision** (End of Week 18):
- If no Critical issues in 7 days → **Proceed to decommissioning** (Phase 4)
- If Critical issue → Rollback to old provider, extend parallel run

**Deliverables**:
- Week 18 migration report
- Go-live decision (CEO approval)

---

## 9. PHASE 4: Old Provider Decommissioning (Week 18)

### 9.1 Data Deletion Verification 🔴 (Most Critical Step)

**Actions**:

1. **Request Deletion from Old Provider** (Appman):
   - DPO sends deletion request via email + API (if available):
   ```
   To: security@appman.co.th
   Subject: Biometric Data Deletion Request - Contract Termination

   Dear Appman Security Team,

   Certogo has migrated to a new E-KYC provider as of [Date]. Per our
   Data Processing Agreement (DPA) Section 10, we request deletion of
   ALL biometric data for ALL Certogo users within 30 days.

   Please confirm deletion and provide:
   1. Certificate of deletion (signed by Appman security manager)
   2. Audit log summary (number of records deleted, deletion date)

   Due date: [Date + 30 days]

   Best regards,
   [DPO Name]
   Data Protection Officer
   Certogo Co., Ltd.
   privacy@certogo.com
   ```

2. **Follow-Up**:
   - Day 7: If no response, send reminder email
   - Day 14: If no response, escalate to CEO (contact Appman CEO)
   - Day 21: If no response, legal demand letter (DPA breach)

3. **Receive Certificate of Deletion** 🔴:
   - Appman provides certificate: "All biometric data for Certogo users has been deleted on YYYY-MM-DD. Total records deleted: [Number]. Signed: [Appman Security Manager]."
   - DPO files certificate in `/evidence/records/data-deletion-certificates/appman-termination-deletion-[YYYY-MM-DD].pdf`

4. **Verification**:
   - DPO conducts final audit of Appman (if audit rights allow)
   - Or request third-party attestation

**SLA**: Certificate received within **30 days** of request (per DPA)

**CRITICAL** 🔴: Failure to obtain certificate = PDPA violation risk. If not received, legal action may be required.

---

### 9.2 API Decommissioning (Week 18)

**Actions**:
1. **Revoke API Keys**:
   - Delete Appman API keys from Certogo systems (secure key vault)
   - Rotate any shared secrets
2. **Remove Network Access**:
   - Remove firewall rules allowing Certogo → Appman traffic
   - Update VPN configurations (if applicable)
3. **Code Cleanup**:
   - Archive old integration code (Git branch: `archive/appman-integration`)
   - Remove from production codebase

**Deliverables**:
- API keys deleted (audit log)
- Network rules removed (firewall change log)

---

### 9.3 Contract Termination (Week 18)

**Actions**:
1. **Final Invoice**:
   - Pay final invoice from Appman
   - Reconcile service credits (if SLA breaches occurred)
2. **Termination Notice**:
   - Legal sends formal termination letter (per contract clause)
   - Confirm termination date
3. **Post-Termination Obligations**:
   - Review contract for post-termination clauses (confidentiality, data retention)
   - Ensure compliance

**Deliverables**:
- Termination letter sent and acknowledged
- Final payment completed

---

## 10. PHASE 5: Post-Migration Review (Weeks 19-20)

### 10.1 Performance Comparison (Week 19)

**Actions**:
1. **Collect Metrics** (first 30 days with new provider):
   - Availability (%)
   - Response time (95th percentile)
   - Accuracy (Pass/Fail rate)
   - Error rate (%)
   - User complaints (count)
   - Cost (per transaction or monthly)

2. **Compare to Old Provider** (baseline):
   - Better, same, or worse?
   - Document improvements or regressions

**Deliverables**: Performance comparison report

---

### 10.2 Lessons Learned (Week 19)

**Actions**:
1. **Retrospective Meeting** (Project team):
   - What went well?
   - What didn't go well?
   - What would we do differently next time?

2. **Document Lessons**:
   - Update this procedure (PROC-002) if improvements identified
   - Share with organization (all-hands meeting)

**Deliverables**: Lessons learned document

---

### 10.3 Documentation Updates 🔴 (Week 20)

**CRITICAL**: Update ISO 27001 documentation to reflect new E-KYC provider.

**Documents to Update**:

| Document | Update Required | Owner |
|----------|----------------|-------|
| **Information Security Policy** (POL-001) Section 6.1 | Change "Current E-KYC provider: Appman" to "Current E-KYC provider: [New Provider Name]" | CISO |
| **PDPA Compliance Policy** (POL-003) Section 8.2 | Update E-KYC provider name in table | DPO |
| **Supplier Security Policy** (POL-004) Section 3.1.5 | Update E-KYC provider details | CISO |
| **Statement of Applicability** (SoA) | Update provider name in controls: A.5.19, A.5.20, A.5.21, A.5.22, A.8.24 | CISO |
| **Risk Assessment** | Update risks R-001 to R-012 (E-KYC risks) with new provider name | CISO |
| **ISMS Scope Statement** Section 3.1.5 | Update E-KYC provider name | CISO |
| **Interested Parties** Section 3.3 | Update E-KYC provider name and details | CISO |
| **Supplier Register** | Mark Appman as "Inactive" (termination date), add new provider as "Active" | Procurement |
| **Data Processing Agreement** | File new provider's DPA, archive Appman's DPA | Legal |
| **DPIA** (Data Protection Impact Assessment) | Update DPIA for new E-KYC provider | DPO |

**Deliverables**:
- All documents updated (version incremented)
- Change log updated

---

### 10.4 Final Project Closure (Week 20)

**Actions**:
1. **Final Report to CEO**:
   - Project summary (timeline, budget, outcomes)
   - Performance comparison (new vs. old provider)
   - Lessons learned
   - Recommendations

2. **Project Closure**:
   - Archive project files
   - Celebrate success (team recognition)

**Deliverables**: Project closure report (CEO approval)

---

## 11. Emergency Migration (Fast-Track)

**Scenario**: Mandatory trigger (e.g., Appman data breach, loss of ISO 27001 cert) requires immediate migration.

**Timeline**: **6-10 weeks** (compressed from 20 weeks)

**Changes**:
- **Accelerate provider selection** (2 weeks instead of 4): Use pre-qualified providers from shortlist
- **Parallel planning and integration** (concurrent instead of sequential)
- **Higher risk tolerance**: 50% traffic immediately (skip 10% phase)
- **Expedited contracts**: Use template DPA (minimal negotiation)

**Risks**:
- Less thorough testing (may have bugs in production)
- Higher stress on team
- Potential service disruptions

**Mitigation**:
- Dedicated team (full-time for 6-10 weeks)
- External consultants (if needed)
- Enhanced monitoring (24/7 during migration)

---

## 12. Rollback Procedure | ขั้นตอนการย้อนกลับ

**Triggers**:
- Critical incident at new provider (data breach, prolonged outage)
- Unacceptable performance (< 95% availability, > 10 sec response time)
- PDPA violation discovered

**Procedure**:
1. **Immediate**: Revert traffic routing to old provider (100%)
2. **Within 1 hour**: Notify CEO, CISO, DPO, CTO
3. **Within 4 hours**: Root cause analysis (what went wrong?)
4. **Within 24 hours**: Decision - Fix and retry, or abandon migration
5. **Within 7 days**: If abandoning, terminate new provider contract, extend old provider contract

**Communications**:
- Internal: Email to all employees (explain rollback, no customer impact)
- External: If customers noticed issues, apologize and explain (service restored)

---

## 13. Success Criteria | เกณฑ์ความสำเร็จ

Migration is considered **successful** if:

| Criterion | Target | Measurement |
|-----------|--------|-------------|
| **Zero data loss** | 100% of E-KYC data migrated | Data integrity checks |
| **Zero security incidents** | 0 breaches, 0 PDPA violations | Incident logs |
| **Service availability** | ≥ 99% during migration | Uptime monitoring |
| **Performance maintained or improved** | Response time ≤ old provider | Performance metrics |
| **Biometric data deleted from old provider** 🔴 | Certificate of deletion received | DPO verification |
| **ISO 27001 documentation updated** | All docs updated within 30 days post-migration | CISO checklist |
| **Budget compliance** | Actual cost ≤ 110% of budget | Finance report |
| **Timeline compliance** | Completed within 22 weeks (or emergency timeline) | Project schedule |

**Overall Success**: 100% of criteria met

---

## 14. Continuous Improvement | การปรับปรุงอย่างต่อเนื่อง

### 14.1 Procedure Review | การทบทวนขั้นตอน

**Frequency**:
- **After each provider change** (update based on lessons learned)
- **Annually** (review even if no change, ensure still relevant)

**Owner**: CISO proposes updates, CEO approves

### 14.2 Provider Change Readiness | ความพร้อมในการเปลี่ยนผู้ให้บริการ

**Maintain Readiness**:
- Keep shortlist of 2-3 qualified E-KYC providers (update annually)
- Keep DPA template current (update if PDPA regulations change)
- Keep integration code modular (easy to swap providers)
- Conduct tabletop exercise every 2 years (simulate provider change)

**Benefit**: If forced to change quickly (emergency), readiness shortens timeline

---

## 15. Related Documents | เอกสารที่เกี่ยวข้อง

- **A.5.22 Organizational Controls** - Detailed 20-week procedure (this is summary version)
- **Supplier Security Policy** (POL-004) - Security assessment framework
- **PDPA Compliance Policy** (POL-003) - Biometric data requirements
- **Data Deletion Procedure** (PROC-001) - For old provider data deletion
- **Risk Assessment** - Risks R-001 to R-012 (E-KYC risks)
- **Data Processing Agreement Template** - Supplier Security Policy Appendix A

---

## 16. Approval | การอนุมัติ

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

**END OF PROCEDURE | สิ้นสุดขั้นตอน**

**Document Classification**: Internal Use Only
**Version**: 1.0
**Last Updated**: [Date]
**Next Review**: [Date + 1 year] or after each provider change
