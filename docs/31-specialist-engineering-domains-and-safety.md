# Chapter 31 — Specialist Engineering Domains & Safety Considerations

This chapter expands specialist branches listed in the master coverage map. These are introductions, not substitutes for domain-specific engineering training, certification or safety review.

## 1. Compilers and programming language tools

A compiler translates source code into another representation, often machine code or bytecode. A simplified pipeline is:
1. **Lexing:** characters become tokens.
2. **Parsing:** tokens are checked against language grammar and turned into syntax structure.
3. **Semantic analysis:** names, types and rules are checked.
4. **Intermediate representation:** program is represented in a form suitable for analysis/optimization.
5. **Optimization:** transformations aim to improve code while preserving required behaviour.
6. **Code generation:** target instructions or bytecode are produced.
7. **Linking/runtime:** dependencies and execution environment complete the program.

Interpreters, JIT compilers and ahead-of-time compilers use different strategies; real runtimes often combine techniques.

**Practice:** draw this pipeline for a tiny expression such as total = price * quantity, then explain where a syntax error and a type error might be detected.

## 2. Formal methods and high-assurance software

Formal methods use mathematical models/specifications to reason about system behaviour. Techniques include invariants, model checking, theorem proving and formal specification. They can find subtle state/logic errors, but require suitable models, expertise and careful assumptions.

Use risk-based assurance: a small internal content page and a safety-critical control system do not need the same evidence burden. Testing and formal reasoning complement rather than automatically replace each other.

**Practice:** specify an invariant for a bank-like demo ledger: a transfer must not create or destroy value except for explicitly modelled fees. Use a toy model only; do not connect it to real accounts.

## 3. Telecom and distributed connectivity

Telecom systems combine radio/access networks, transport, routing, signalling/control, service platforms, monitoring and billing. Important concerns include latency, coverage, handover, capacity, resilience and regulation. A web developer may consume telecom APIs without needing to design radio systems, but should understand latency, disconnections and retry behaviour.

**Practice:** map how a mobile app behaves when a device switches between Wi-Fi and cellular service during an upload. Include resumability, duplicate requests, timeout handling and user feedback.

## 4. High-performance and scientific computing

HPC workloads use parallel computation across cores, GPUs or multiple nodes. Scientific computing also depends on numerical methods, units, precision, reproducibility and validation against known results.

- Parallel speedup is limited by serial work, communication and coordination overhead.
- Floating-point arithmetic has finite precision; mathematically equivalent operations may produce slightly different results.
- Reproducibility may require recording code version, inputs, configuration, random seeds and hardware/software environment.

**Practice:** compare a serial and parallel version of a toy computation; record correctness, runtime and environment. Do not assume more cores always means proportionally faster execution.

## 5. GPUs and hardware accelerators

GPUs and other accelerators can improve suitable parallel workloads, but data transfer, memory limits, kernel launch overhead, precision requirements and device availability matter. Benchmark representative workloads before choosing hardware.

**Practice:** list whether a sample workload is compute-bound, memory-bound or dominated by data movement. Propose a measurement that could distinguish the cases.

## 6. Industrial/OT and embedded safety

Operational technology (OT) monitors or controls physical processes. Availability, predictable timing, equipment safety and recovery may be more important than fast feature delivery. IT security controls must be adapted to physical process risks and legacy equipment constraints.

Principles:
- Map assets and trust boundaries.
- Separate networks where appropriate and document permitted flows.
- Test changes in a safe environment before operational rollout.
- Define manual/safe operating mode and recovery.
- Coordinate with system owners and safety specialists.
- Never perform unauthorized scanning or experiments on live industrial systems.

**Practice:** for a fictional water-level monitoring system, identify sensor failure, network loss, false reading and unauthorized command risks; define safe detection and escalation actions.

## 7. Digital forensics and authorized security testing

Digital forensics aims to preserve and analyze evidence. Evidence handling may require authorization, chain of custody, timestamp integrity, controlled access and reproducible procedures. Security testing must stay within a written authorized scope.

For learning, use intentionally vulnerable labs or systems you own. Do not test third-party systems without explicit authorization. Avoid modifying evidence or exposing personal data.

**Practice:** write an evidence-handling checklist for a fictional compromised test server: who authorizes collection, how timestamps are recorded, where copies are stored, who can access them and how integrity is checked.

## 8. Sustainability and responsible operations

Software affects energy use through compute, storage, network transfer, hardware lifecycle and user-device workload. Optimization should consider useful work delivered, not only raw resource consumption. Deleting data may conflict with retention/legal needs, so define governance before cleanup.

**Practice:** estimate which components dominate a sample service's resource use; propose one measurable efficiency improvement and a guardrail to ensure quality/security do not regress.

## Specialist-domain selection checklist

Before deepening a specialist branch, identify:
1. The actual role or product need.
2. Domain standards/regulations and their jurisdiction.
3. Consequences of failure, including physical, financial or privacy impact.
4. Required specialist expertise and review.
5. Safe test/simulation environment.
6. Evidence needed to claim correctness or readiness.
7. Lifecycle, maintenance and end-of-support plan.

## Quick answer guide
1. **Does compilation always mean direct translation to machine code?** No; bytecode, intermediate representations and JIT strategies are common.
2. **Do formal methods remove all bugs?** No. Results depend on model correctness, assumptions and scope.
3. **Does parallel computing guarantee speedup?** No; serial work, data movement and coordination can dominate.
4. **Can IT security changes be applied to OT without testing?** No. Physical safety and process availability must be considered.
5. **Can a security researcher test any public service?** No. Testing needs explicit authorization and scope.
6. **Is lower compute usage always better?** Not if it breaks correctness, reliability, security or user needs; measure useful outcomes.

## Further learning
- [LLVM documentation](https://llvm.org/docs/)
- [NASA Systems Engineering Handbook](https://www.nasa.gov/reference/systems-engineering-handbook/)
- [NIST Operational Technology Security](https://csrc.nist.gov/pubs/sp/800/82/r3/final)
- [Green Software Foundation](https://greensoftware.foundation/)
- [NIST Computer Forensics Tool Testing Program](https://www.nist.gov/itl/ssd/software-quality-group/computer-forensics-tool-testing-program-cftt)

## Review status
- Content milestone: specialist-domain introductions with risk-aware practice prompts.
- Verification status: introductory; individual standards and domain requirements require focused review.
- Last content expansion: 2026-10-30.
- Next review: add domain-specific worked cases, verify current standards and seek specialist review for safety-critical topics.
