# 07 — DevOps & Reliability

[← Learning index](../README.md)

## DevOps
DevOps development aur operations ke beech collaboration, automation aur feedback improve karne wali practices hain. Goal reliable software ko safely deliver karna hai.

## Git and version control
Git code history rakhta hai. Branches parallel work mein help karti hain; pull requests review aur discussion ka path deti hain. Typical workflow: branch → changes → tests → review → merge → deploy.

## Containers
Container app aur dependencies ko portable package mein run karta hai. Virtual machines apna guest operating system run karti hain; common Linux containers host kernel share karte hain.

## CI/CD
Pipeline code build, lint, tests, security checks aur deployment automate kar sakti hai. Secrets ko logs mein expose na hone do aur production permissions restrict karo.

## Metrics, logs, traces
- Metrics: numeric signals, jaise latency, CPU aur error rate.
- Logs: events aur details.
- Traces: request ka path multiple services mein.
Alerts actionable hon, owner aur runbook ke saath.

## Backup and recovery
Backup data ki copy hai; disaster recovery service restore plan hai. RPO acceptable data-loss window aur RTO target restore time describe karte hain. Backup ko restore karke test bhi karo.

## Incident response
Detect → assess → communicate → mitigate → restore → learn. Postmortem ka focus systems/processes improve karna hona chahiye, blame karna nahi.

## Practice
1. Metrics, logs aur traces compare karo.
2. Backup hone par bhi restore test kyun zaroori hai?
3. Production incident ke first steps likho.