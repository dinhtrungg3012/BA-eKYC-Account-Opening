# Digital Account Opening with eKYC — Business Analysis Project

A Business Analyst training project: requirements and design documentation for an **online bank account-opening system with electronic identity verification (eKYC)**.

> **Note:** This is an individual training project. The bank and system are fictional, and all data is sample data. Documents are written in Vietnamese; diagrams use English/Vietnamese labels.

**Author:** Dao Dinh Trung — Business Analyst Intern candidate | dinhtrungg3012@gmail.com

---

## 1. Problem

Customers who want a bank account must visit a branch to prove their identity, which is slow and costly for both sides. This project defines a fully online flow where the customer verifies their identity with a national ID card (CCCD) and a selfie, and the bank decides automatically or routes the case to manual review.

## 2. My role and scope

I acted as the Business Analyst for the whole analysis-to-design chain:

- Analyzed the AS-IS process and designed the TO-BE process.
- Elicited requirements through a Q&A simulation and wrote the BRD and SRS.
- Designed use cases, process flows, data model and API specifications.
- Mapped the backlog into a User Story Map.

**In scope:** online account opening, OTP verification, eKYC (OCR, face matching, liveness detection), manual review of failed cases, duplicate-CCCD rejection.
**Out of scope:** card issuance, core banking integration, mobile app implementation.

## 3. eKYC flow

```
OCR (read CCCD)  →  Face Matching  →  Liveness Detection  →  Decision
```

![TO-BE process](03-design/diagrams/bpmn-to-be.png)

## 4. Key business rules

| Rule | Decision |
|---|---|
| Confidence score | Pass threshold of 85% |
| Failure handling | Max 3 failures, counted across OCR and face matching combined |
| After failures | Case goes to **Manual Review** (not rejected) |
| Rejection | Only for a duplicate CCCD |
| Transaction limit | 100M VND/month per Circular 16/2020/TT-NHNN |
| Security | AES-256 for biometric data, bcrypt for passwords |
| Audit | Logs retained for at least 5 years |

## 5. Deliverables

| Area | Document | Summary |
|---|---|---|
| Analysis | [Q&A Log](01-analysis/QA-Log.xlsx) | Requirement elicitation questions and answers |
| Analysis | [Business process (BPMN)](01-analysis/) | AS-IS and TO-BE |
| Requirements | [BRD](02-requirements/BRD.pdf) | Business requirements |
| Requirements | [SRS](02-requirements/SRS.pdf) | 9 use cases with functional requirements |
| Requirements | [User Story Map](02-requirements/User-Story-Map.png) | Backlog across 3 releases |
| Design | [Diagrams](03-design/diagrams/) | Use Case, Activity, Sequence, ERD |
| Design | [Database description](03-design/Database-Description.pdf) | SQL Server schema, 7 tables |
| API | [API specification](04-api/API-Specification.pdf) | 8 backend APIs + 2 vendor eKYC APIs, with validation and error handling |
| Prototype | [Prototype](05-prototype/) | Screen designs |
| Summary | [Presentation](Portfolio_BA_Mo_TK_eKYC.pdf) | Project overview slides |

Editable sources (draw.io, Word, PowerPoint) are in [`source/`](source/).

## 6. Tools

Draw.io (BPMN, UML, ERD, story map) · SQL Server (schema) · Microsoft Word / Excel / PowerPoint (documentation)

## 7. What I learned

- Business rules need one clear owner: shared failure counters and error codes must be consistent between the process, sequence diagram and API spec.
- Writing the data model and API spec early exposes gaps in the requirements.
