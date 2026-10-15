# Digital Account Opening with eKYC — Business Analysis Project

A Business Analyst training project focused on requirements elicitation, business process analysis, system requirements, and solution design for an online bank account-opening system with electronic identity verification (eKYC).

> **Project note:** This is an individual training project. The bank and system are fictional, and all sample data and business rules are defined for demonstration purposes. This project does not represent a production banking system.

**Author:** Dao Dinh Trung  
**Target role:** Business Analyst Intern  
**Contact:** dinhtrungg3012@gmail.com

---

## 1. Project Overview

Traditional bank account opening may require customers to visit a branch for identity verification, increasing processing time and operational effort.

This project proposes an online account-opening flow that allows individual customers to submit their identity information and verify their identity electronically using their Citizen Identity Card (CCCD) and facial verification.

The system includes automated verification and a manual review path for cases that cannot be verified successfully.

## 2. Objectives and Scope

### Objectives

- Analyze the existing account-opening process and propose a digital alternative.
- Define business requirements and functional requirements.
- Model business processes and user interactions.
- Specify API behavior, data structures, validation rules, and error handling.
- Organize requirements into a User Story Map to support MVP planning.

### In Scope

- Phone number and OTP verification.
- CCCD information extraction using OCR.
- Face matching and liveness detection.
- Automated verification decisions.
- Manual review for unsuccessful verification cases.
- Duplicate CCCD detection and rejection.

### Out of Scope

- Physical card issuance.
- Core banking integration.
- Mobile application implementation.
- Production deployment and integration with real banking services.

## 3. My Role and Contributions

I performed the Business Analyst activities throughout the analysis and design stages:

- Analyzed the AS-IS process and designed the TO-BE process.
- Simulated requirement elicitation through a Q&A log.
- Documented business requirements in the BRD and system requirements in the SRS.
- Developed use cases, business process diagrams, activity diagrams, and sequence diagrams.
- Designed the data model and documented API specifications.
- Created a User Story Map to organize user activities, tasks, and release scope.

## 4. eKYC Verification Flow

The proposed verification flow consists of the following stages:

1. **OTP Verification:** Verify the customer's phone number.
2. **OCR:** Extract identity information from the CCCD.
3. **Face Matching:** Compare the customer's selfie with the identity document portrait.
4. **Liveness Detection:** Check whether the submitted face capture represents a live person.
5. **Verification Decision:** Determine whether the case can proceed or requires manual review.
6. **Final Outcome:** Continue account opening, route the case for review, or reject it when a defined rejection rule applies.

The detailed conditions and transitions are documented in the project deliverables.

## 5. Key Business Rules

The following are sample business rules defined for this training project, not verified regulatory requirements.

| Area | Proposed rule |
|---|---|
| Verification threshold | A confidence score threshold of 85% |
| Verification failures | A maximum of three combined failures across OCR and face matching |
| Failure handling | Route the case to manual review after the defined failure limit |
| Duplicate identity | Reject a duplicate CCCD according to the defined business rule |
| Security | Specify encryption and password-hashing requirements in the technical documentation |
| Audit | Define audit-log retention requirements for the proposed system |

**Important:** Numerical thresholds, security controls, retention periods, and regulatory references must be validated against the relevant requirements before being treated as production or compliance requirements.

## 6. Project Deliverables

| Category | Deliverable | Description |
|---|---|---|
| Analysis | [Q&A Log](01_Requirements/QA-Log.xlsx) | Requirement elicitation questions and answers |
| Requirements | [Business Requirements Document (BRD)](01_Requirements/BRD.pdf) | Business objectives, scope, stakeholders, and requirements |
| Requirements | [Software Requirements Specification (SRS)](01_Requirements/SRS.pdf) | Functional requirements and use cases |
| Requirements | [User Story Map](02_Process_and_Design/User_Story_Map.png) | User activities, tasks, and release planning |
| Process & Design | [Process and Design Diagrams](02_Process_and_Design/) | BPMN, BFD, Use Case, Activity, Sequence, and ERD diagrams |
| Technical Specification | [API Specification](03_Technical_Specification/API_Specification.pdf) | API endpoints, validation, request/response structures, and error handling |
| Technical Specification | [Database Specification](03_Technical_Specification/Database_Specification.pdf) | Database schema and data structure documentation |
| Prototype | [UI Prototype](04_Prototype/) | Prototype link and supporting screen designs, if available |
| Presentation | [Project Portfolio](05_Presentation/Portfolio_BA_Mo_TK_eKYC.pdf) | Summary of the project, scope, and BA deliverables |

### Editable Source Files

Editable source files, including draw.io diagrams and original Office documents, are maintained separately where applicable.

## 7. Tools

- **Draw.io:** BPMN, UML, ERD, and User Story Map.
- **Microsoft Word:** BRD, SRS, and technical documentation.
- **Microsoft Excel:** Requirement elicitation log.
- **Microsoft PowerPoint:** Project presentation.
- **SQL Server:** Database schema design.

## 8. Key Learnings

- Business rules must be consistent across requirements, process flows, sequence diagrams, and API specifications.
- Requirement elicitation helps clarify assumptions and identify missing business decisions.
- Data modeling and API specification can expose gaps in functional requirements.
- A User Story Map helps connect user activities with backlog items and MVP scope.
- Technical and regulatory assumptions should be explicitly documented and validated rather than presented as confirmed facts.

---

*This repository is a learning portfolio demonstrating Business Analysis documentation and modeling skills. It is not a production banking application.*
