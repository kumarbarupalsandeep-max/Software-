# 09 — Cybersecurity & Privacy

[← Learning index](../README.md)

## CIA triad
- Confidentiality: data sirf authorized users ko mile.
- Integrity: unauthorized changes se protection.
- Availability: service zaroorat par accessible ho.
Example: payroll permissions confidentiality, audit trails integrity aur tested backups recovery support karte hain.

## Authentication, authorization, least privilege
Authentication identity verify karti hai. Authorization permissions enforce karti hai. Least privilege ka matlab sirf required access dena hai. Admin accounts aur production access tightly control karo.

## Encryption and secrets
Encryption data in transit/at rest protect kar sakti hai. API keys, passwords aur tokens ko source code ya public repositories mein hardcode mat karo. Approved secret manager use karo aur access/rotation review karo.

## Secure coding
- Input validate aur output appropriately encode karo.
- Parameterized database queries use karo.
- Access control server-side enforce karo.
- Dependencies update/scan karo.
- Errors mein secrets/internal details expose mat karo.
- Backups aur recovery test rakho.

## Common web risks
Injection, broken access control, authentication failures, security misconfiguration aur vulnerable dependencies common risks hain. Security tests ko development/release process ka part banao.

## Privacy
Sirf necessary personal data collect karo; purpose, access, retention aur deletion define karo. Applicable laws/policies follow karo. Sensitive data ko logs ya analytics mein unnecessary include na karo.

## Practice
1. CIA triad ke office examples do.
2. API key repository mein rakhna unsafe kyun hai?
3. Least privilege ka example likho.