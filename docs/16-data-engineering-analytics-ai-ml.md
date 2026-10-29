# 16. Data Engineering, Analytics, AI & Machine Learning

## 1. Data lifecycle
Source systems → ingestion → validation → storage → transformation → analytics/model → decision/action → monitoring. Data quality, lineage, access controls and retention har stage par matter karte hain.

## 2. Data categories and storage
- Structured: rows/columns, e.g. orders.
- Semi-structured: JSON/events.
- Unstructured: documents, images, audio.
- OLTP database: operational reads/writes.
- OLAP warehouse: analytical queries across large datasets.
- Data lake: varied raw/processed data; lakehouse approaches combine lake flexibility with table/transaction capabilities.
Choose based on query patterns, consistency, latency, governance and cost—not hype.

## 3. ETL vs ELT
ETL: extract, transform, load. ELT: extract, load into target platform, then transform. Batch handles scheduled groups; streaming processes events continuously or near-real-time. Exactly-once claims depend on system semantics; practical pipelines often use idempotency, deduplication and replay.

## 4. Data modeling
Entities, primary/foreign keys, constraints, normalization, dimensional models, facts/dimensions, slowly changing dimensions and event schemas. Track event time vs processing time, timezone, currency, units and schema versions. Poor definitions produce misleading dashboards.

## 5. Analytics maturity
- Descriptive: kya hua?
- Diagnostic: kyun hua?
- Predictive: kya ho sakta hai?
- Prescriptive: kya action lena chahiye?
Metrics need clear owner, formula, grain, time window and source of truth. Correlation causation ka proof nahi hai; experiments and causal methods help.

## 6. AI vs ML vs deep learning vs generative AI
AI broad field hai; ML data se patterns learn karta hai; deep learning neural networks ka family hai; generative AI new text/image/audio/code produce kar sakta hai. A language model next-token probabilities se text generate karta hai; fluent answer automatically verified fact nahi hota.

## 7. ML lifecycle
Problem definition → representative data → split train/validation/test → baseline → train → evaluate → deployment → monitor drift, quality, fairness, latency and cost. Data leakage evaluation ko unrealistically good bana sakta hai. Production models require versioning, reproducibility and rollback.

## 8. Generative AI applications and risks
Use cases: search assistance, summarization, drafting, classification, support triage, coding help. Risks: hallucination, prompt injection, sensitive-data exposure, copyright/IP uncertainty, biased output, overreliance and variable cost. Human review and constrained tool permissions matter for high-impact actions.

## 9. Retrieval-Augmented Generation (RAG)
RAG flow: documents → chunking → embeddings/index → query retrieval → context assembly → model response with source grounding. Evaluate retrieval relevance and answer faithfulness separately. Secure document-level authorization; retrieval must not expose content the user cannot access.

## 10. Vector search and embeddings
Embedding numeric vector representation hoti hai jo semantic similarity approximate kar sakti hai. Similarity metric, chunk size, overlap, metadata filters, multilingual quality and index refresh affect results. Vector DB traditional database ka universal replacement nahi.

## 11. MLOps and LLMOps
Dataset/model/prompt/version tracking, evaluation sets, offline and online metrics, guardrails, latency/cost monitoring, drift detection, feedback loops, rollback and incident response. Test adversarial prompts and retrieval permissions.

## Practical project
CSV sales data clean karein, schema/quality checks likhein, SQL aggregation se dashboard metrics banayein, phir optional FAQ RAG prototype with citations and permission filtering. Sensitive real data use na karein.

## Questions
1. ETL aur ELT ka difference?
2. Training/test split kyun?
3. RAG hallucination ko completely eliminate karta hai?
4. Data leakage kya hota hai?
5. Model accuracy ke alawa kya monitor karna chahiye?
