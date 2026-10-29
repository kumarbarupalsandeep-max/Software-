# 25. Standards, Compliance, Open Source & Software Supply-Chain Security

## 1. Standards vs frameworks vs laws
A standard defines agreed technical or process specifications; a framework organizes controls/practices; a law creates legal obligations within its jurisdiction. Certification, audit and compliance evidence are different activities. Which applies depends on industry, customer contract, geography, company role and data type.

## 2. Secure software supply chain
Modern software depends on packages, build tools, actions, base images, registries and deployment systems. Risk can enter through compromised dependencies, typo-squatting, malicious maintainers, stolen publishing credentials or poisoned build pipelines.

Useful controls: pin and review dependencies, use lockfiles, scan known vulnerabilities, review package provenance, minimize build permissions, protect CI secrets, use trusted registries, generate SBOMs where appropriate, sign artifacts and verify provenance. A scan is only a point-in-time signal; it cannot prove software is safe.

## 3. SBOM and provenance
A Software Bill of Materials lists software components and metadata. It helps answer “what is included?” Build provenance describes how an artifact was produced. Keep component versions and licenses accurate; tie attestations to the actual build artifact. A document alone is not useful if it is not maintained and linked to releases.

## 4. Vulnerability management
Track affected versions, exploitability, exposure, available fixes, business impact and compensating controls. Define severity and remediation deadlines; validate fixes and communicate residual risk. Coordinated disclosure programs should provide a safe reporting channel and clear expectations. Do not test systems without authorization.

## 5. Open-source governance
Before adding a dependency, assess maintenance health, license compatibility, security history, transitive dependencies, update cadence and exit alternatives. Preserve notices and meet license conditions. Establish approved patterns without blocking useful community software unnecessarily.

## 6. Compliance operations
Map control to owner, system scope, evidence source, frequency, exception and remediation. Evidence should be current, access-controlled and traceable. Avoid collecting excessive personal data in audit logs. Policies that are not implemented or tested do not create effective control.

## 7. Change and release evidence
For each release, retain appropriate version, build identifier, test results, approvals, artifact provenance, migration notes and rollback procedure. Access to production and signing credentials should be limited and audited. Emergency changes still need retrospective review.

## 8. Practical exercise
For a small web app:
1. Generate a dependency inventory.
2. Review license and known-vulnerability reports.
3. Protect CI credentials and reduce permissions.
4. Record build version and artifact checksum.
5. Create a vulnerability remediation process.
6. Write a release evidence checklist.
7. Document which legal/compliance questions require expert review.

## Questions
1. SBOM and vulnerability scan mein difference?
2. A clean scan prove karta hai ki app secure hai?
3. Why pin dependencies and protect CI credentials?
4. Standard, framework and law ka difference?
