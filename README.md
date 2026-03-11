QSP – Stage210
Claim → Test → Evidence Mapping

QSP (Quantum Security Protocol) is an experimental protocol architecture exploring how Quantum Key Distribution (QKD) and Post-Quantum Cryptography (PQC) can be integrated into a verifiable and auditable session protocol.

Stage210 introduces traceable security claims, linking security reasoning to executable verification.

Assumption
↓
Claim
↓
Test
↓
Evidence

This structure enables reviewers to clearly evaluate:

What evidence supports each security claim?

How to Review in 5 Minutes

Researchers reviewing this repository can follow this quick path:

1️⃣ Protocol structure
protocol_v1.0.md

Minimal protocol design and session structure.

2️⃣ Security model
docs/security_model.md

Threat assumptions and security boundaries.

3️⃣ Security claims
docs/claim_matrix.md

Structured list of protocol guarantees.

4️⃣ Claim → Evidence mapping
docs/claim_evidence_mapping.md

Each claim is linked to executable tests and evidence logs.

5️⃣ Executable tests
tests/

Security behaviour is validated through automated tests.

6️⃣ Evidence logs
evidence/

Evidence produced by running the tests.

Project Context

This repository is part of the QSP staged development process, where each stage introduces a specific architectural step.

Stage	Focus
Stage206	Minimal protocol demonstration
Stage207	Cryptographic integration
Stage208	Security model
Stage209	Claim matrix
Stage210	Claim → Test → Evidence mapping

Stage210 transforms the claim structure into traceable security engineering.

Traceable Security Claims

Traditional protocol descriptions often include security claims without executable verification.

Stage210 introduces explicit mapping:

Claim
↓
Executable Test
↓
Evidence

This approach improves:

auditability

reproducibility

external reviewability

Claim → Evidence Mapping

Detailed mapping:

docs/claim_evidence_mapping.md

Example structure:

Claim	Test	Evidence
Replay attack resistance	tests/test_replay.py	evidence/replay_attack.log
Downgrade protection	tests/test_downgrade.py	evidence/downgrade_attack.log
Fail-closed behaviour	tests/test_fail_closed.py	evidence/fail_closed.log
Session integrity	tests/test_session_integrity.py	evidence/session_integrity.log
Repository Structure
stage210
│
├── docs/
│   ├── claim_matrix.md
│   ├── claim_evidence_mapping.md
│   └── security_model.md
│
├── evidence/
│   ├── replay_attack.log
│   ├── downgrade_attack.log
│   ├── fail_closed.log
│   └── session_integrity.log
│
├── tests/
│
├── qspcrypto/
│
├── qsp_demo/
│
├── scripts/
│
├── protocol_v1.0.md
│
└── README.md
Design Philosophy

QSP follows a fail-closed security model.

If any security assumption fails, the protocol must terminate safely.

Examples include:

entropy source failure

cryptographic downgrade attempts

replay attempts

protocol state inconsistencies

QKD Position in QSP

QKD is treated as:

Optional entropy source
not
automatic security upgrade

Security guarantees are defined independently of QKD availability.

This design avoids implicit security assumptions.

Security Engineering Goal

The goal of QSP is not to introduce a new QKD security proof.

Instead, the focus is:

explicit security assumptions

traceable protocol claims

executable validation

reproducible security reasoning

Status

This repository is an experimental research prototype.

It explores protocol architecture and verifiable security reasoning.

Future Work

Potential future improvements include:

CI-bound claim verification

automatic evidence generation

formal verification integration

reproducible security reports

external interoperability experiments

License

MIT License

Copyright (c) 2025 Motohiro Suzuki

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files to deal in the Software
without restriction.