# Chapter 28 — End-to-End IT Industry Case Studies & Assessment

Is chapter ka goal alag-alag concepts ko ek real project mein jodna hai. Examples simplified learning scenarios hain, production architecture ki guarantee nahi.

## Case Study A: Small business appointment SaaS

### Business problem
Local service providers appointments, cancellations, reminders aur staff availability manually manage kar rahe hain. Goal: bookings ko easy banana aur double-booking reduce karna.

### Stakeholders and requirements
- Customer: slots dekhna, booking/cancel karna, confirmation paana.
- Staff: availability manage karna aur daily schedule dekhna.
- Admin: staff/accounts manage karna aur basic reports dekhna.
- Business owner: booking completion, cancellations aur support cost track karna.

Functional requirements:
1. Customer available slot select kar sake.
2. Server slot availability dobara verify kare before confirming.
3. Customer ko booking reference mile.
4. Cancellation policy ke mutabiq booking cancel ho.
5. Staff sirf authorized schedule manage kar sake.

Non-functional requirements ko measurable banao: peak request load, acceptable latency percentile, backup/restore objective, data retention, accessibility target aur service availability expectation stakeholders se agree karo.

### Suggested architecture
Browser/mobile web → HTTPS/API → booking service → relational database. Background queue/worker reminders send kar sakta hai. Logs/metrics/traces service health samajhne mein help karte hain. Small launch mein modular monolith simpler ho sakta hai; early microservices mandatory nahi.

### Critical failure cases
- Two customers same slot ko almost simultaneously book karte hain.
- Reminder provider unavailable hai.
- Customer double-click karta hai ya network timeout ke baad request retry karta hai.
- Staff member leave karta hai but account access active rehta hai.
- Backup exists, lekin restore kabhi test nahi hua.

### Expected design decisions
- Database-level constraints/transaction strategy se slot conflict prevent karo.
- Booking creation ke liye idempotency contract consider karo.
- Reminder failures retry with limits/backoff; booking confirmation aur reminder delivery ko separate statuses do.
- Role-based permissions aur leaver deprovisioning workflow rakho.
- Restore drill, monitoring dashboard aur incident runbook prepare karo.

## Case Study B: E-commerce checkout

### Workflow
Catalogue → cart → checkout → payment provider interaction → order state update → fulfilment → refund/return if needed.

### Must-handle cases
- Product price changes after cart creation.
- Inventory gets sold by another customer.
- Payment provider times out but may have processed the request.
- User submits checkout twice.
- Payment succeeds but order update fails.
- Refund is requested after partial fulfilment.

### Learning design
- Server authoritative price and inventory recheck kare.
- Payment status ko clearly model karo: pending, confirmed, failed, refund pending/refunded (actual states provider integration ke mutabiq).
- Idempotency and reconciliation use karo where provider supports it.
- Payment card data ko unnecessarily store/log na karo; applicable provider and security standards follow karo.
- Audit trail, alerting aur manual reconciliation procedure define karo.

**Assessment question:** Agar browser timeout dikha raha hai, kya user ko turant “payment failed” kehna safe hai?  
**Expected answer:** Not necessarily. Provider-side status verify/reconcile karna pad sakta hai; UI should show an honest pending/verification state.

## Case Study C: Internal employee management portal

### Modules
Members/roles, departments, tasks, attendance, leave, reports and admin settings.

### Access design
- Employee apne permitted records dekhe.
- Manager sirf assigned team ke records access kare.
- HR permissions business policy ke mutabiq define hon.
- Admin access highly restricted, audited and reviewed ho.
- Employee exit/role change par access promptly update ho.

### Data and privacy design
- Har field ka business purpose define karo.
- Salary/health/identity details ko broad dashboard access mein expose na karo.
- Reports mein only required fields dikhayein.
- Retention, export and deletion policies applicable law ke hisaab se define karo.
- Demo screenshots mein real personal data na use karo.

### Acceptance tests
1. Employee doosre employee ki private record ID change karke access nahi kar sakta.
2. Manager team boundary ke bahar records access nahi kar sakta.
3. Unauthorized API call server-side reject hoti hai.
4. Leave approval status audit trail mein record hota hai.
5. Employee deactivation ke baad active sessions/tokens policy ke mutabiq revoke ya expire hote hain.

## Case Study D: IT support and incident operations

### Scenario
Users report karte hain ki employee portal slow hai; some requests timeout ho rahi hain.

### Triage workflow
1. Impact, start time, affected users and endpoints identify karo.
2. Recent deployments/configuration changes check karo.
3. Latency/error metrics aur logs ko request/correlation IDs se relate karo.
4. Database saturation, dependency failure, network issues and traffic spike jaise hypotheses test karo.
5. Safe mitigation choose karo; e.g. rollback, disable optional feature, reduce noncritical load.
6. Recovery confirm karo, users ko update do, then post-incident review karo.

### Good incident record
- Summary and impact
- Timeline with timestamps
- Detection source
- Actions/decisions and owners
- Root/contributing factors (evidence-based)
- Recovery verification
- Follow-up actions with owner and due date

## End-to-end deliverable

Ek case choose karke ye artifacts banao:
1. One-page problem statement and scope/non-goals.
2. Stakeholder map and 8–12 requirements.
3. At least 5 measurable acceptance criteria.
4. System/context diagram and request/data-flow diagram.
5. Data model/API contract or workflow specification.
6. Threat/risk register with mitigation and residual risk.
7. Test plan covering happy paths, boundary cases, permissions and failures.
8. Deployment/release plan, rollback/mitigation criteria and monitoring.
9. Cost drivers and a basic operating-cost estimate with assumptions.
10. Runbook, incident communication template and known limitations.

## Scoring rubric (100 points)

| Area | Points | Evidence |
|---|---:|---|
| Problem and scope | 10 | Clear user, problem, assumptions and non-goals |
| Requirements | 10 | Testable functional/non-functional criteria |
| Architecture/data flow | 15 | Components and responsibilities explained |
| Data/API correctness | 10 | Validation, state transitions and error behaviour |
| Security/privacy/accessibility | 15 | Threats, permissions and inclusive user flows |
| Testing | 10 | Positive, negative, boundary and failure tests |
| Operations/recovery | 10 | Monitoring, rollback/mitigation, backup/restore |
| Business/cost reasoning | 5 | Cost drivers and value metric |
| Documentation/communication | 5 | Clear diagram, runbook and limitations |
| Evidence and reflection | 10 | Tests performed, findings and improvements |
| **Total** | **100** | |

A score is a learning aid, not a professional certification. Any critical security/privacy/safety gap should be treated as a blocker even if the numeric score is high.

## Self-review answer prompts

Before calling the project complete, answer:
- What exact user problem is solved?
- What assumptions have not been validated?
- What happens when the database/API/provider is unavailable?
- Can a user bypass frontend controls by calling the API directly?
- How do we prevent duplicate or conflicting actions?
- How will we know the system is healthy?
- How do we restore service/data and prove recovery works?
- What data do we collect, who can access it and how long do we retain it?
- What are the top three cost drivers?
- What evidence supports each “done” claim?

## Review status
- Content milestone: end-to-end case-study pack and assessment rubric.
- Verification status: educational scenarios; not a production design review.
- Last content expansion: 2026-10-30.
- Next review: validate case studies against chapters 02–25, add runnable code labs in relevant chapters, and check external references.
