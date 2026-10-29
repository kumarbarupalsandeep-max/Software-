# Research Methodology & Primary Source Index

## How to research a technical topic deeply
For each topic, answer: (1) definition and purpose, (2) problem it solves, (3) how it works, (4) architecture/data flow, (5) alternatives, (6) strengths and limitations, (7) security/privacy risks, (8) reliability and scaling, (9) cost and operations, (10) practical example, (11) failure modes, (12) interview/revision questions.

## Source quality hierarchy
1. Standards and official specifications for protocol/behavior.
2. Official product documentation for product-specific implementation.
3. Reputable books, peer-reviewed research and well-maintained engineering publications.
4. Community discussion for real-world experience, cross-check before treating as fact.
5. Marketing claims and unsourced social posts: leads to investigate, not final proof.

## Primary sources worth bookmarking
- MDN Web Docs: https://developer.mozilla.org/ — web platform, HTML, CSS, JavaScript, HTTP, accessibility.
- WHATWG HTML Standard: https://html.spec.whatwg.org/
- W3C: https://www.w3.org/ — web standards and accessibility guidance.
- IETF RFC index: https://www.rfc-editor.org/ — internet protocol standards.
- OWASP: https://owasp.org/ — application security projects and guidance.
- NIST: https://www.nist.gov/cybersecurity — cybersecurity frameworks and publications.
- CISA: https://www.cisa.gov/ — practical security guidance and alerts.
- Git documentation: https://git-scm.com/doc
- Linux man-pages: https://man7.org/linux/man-pages/
- Kubernetes docs: https://kubernetes.io/docs/
- Docker docs: https://docs.docker.com/
- AWS documentation: https://docs.aws.amazon.com/
- Microsoft Learn: https://learn.microsoft.com/
- Google Cloud documentation: https://cloud.google.com/docs
- PostgreSQL documentation: https://www.postgresql.org/docs/
- MySQL documentation: https://dev.mysql.com/doc/
- MongoDB documentation: https://www.mongodb.com/docs/
- Python documentation: https://docs.python.org/3/
- Java documentation: https://docs.oracle.com/en/java/
- TypeScript handbook: https://www.typescriptlang.org/docs/
- React documentation: https://react.dev/learn
- Node.js documentation: https://nodejs.org/docs/latest/api/
- OpenAPI specification: https://spec.openapis.org/oas/latest.html
- GraphQL specification: https://spec.graphql.org/
- Unicode: https://www.unicode.org/
- WCAG overview: https://www.w3.org/WAI/standards-guidelines/wcag/
- Google SRE books: https://sre.google/books/
- CNCF: https://www.cncf.io/ — cloud-native ecosystem.
- FinOps Foundation: https://www.finops.org/framework/
- Scrum Guide: https://scrumguides.org/
- Agile Manifesto: https://agilemanifesto.org/
- GitHub Docs: https://docs.github.com/
- Python Packaging User Guide: https://packaging.python.org/

## Keep the notes accurate
- Write the date checked when facts are version-sensitive.
- Label provider-specific features as provider-specific.
- Avoid copying long passages; explain concepts in original words and cite sources.
- For laws, finance, health, security and regulated industries, verify current official requirements and get qualified professional review where appropriate.
- Mark uncertain claims and test assumptions.


## Visual example (diagram)

**Research validation** — is simplified flow ko real system ke example ki tarah dekhein.

```mermaid
flowchart TD
Q[Question] --> P[Primary source]
P --> V[Verify version and date]
V --> X[Compare alternatives]
X --> N[Write notes and citations]
```
