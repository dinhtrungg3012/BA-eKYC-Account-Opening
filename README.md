# Online Account Opening with eKYC

**Business Analyst portfolio · Individual training project**

A case study exploring how a new customer can open a bank account remotely through phone verification, CCCD capture, facial verification, and eBanking setup. The work covers requirements analysis, process modeling, UI prototyping, and API/data specifications.

**Author:** Đào Đình Trung

**Target role:** Business Analyst Intern / Fresher

**Duration:** Approximately four months of guided coursework

**Contact:** [dinhtrungg3012@gmail.com](mailto:dinhtrungg3012@gmail.com)

## Start here

| What you want to review | Open |
| --- | --- |
| Project overview and BA deliverables | [Portfolio presentation — PPTX](5.%20Portfolio/Portfolio_BA_Mo_TK_eKYC.pptx) |
| Customer journey and UI | [Prototype screens](4.%20Prototype/) · [Interactive Figma prototype](https://www.figma.com/proto/zj0eHJI9i0ked7dSZaLMmR/%C4%90%C3%ACnh-Trung-K29?page-id=0%3A1&node-id=21-5&scaling=scale-down&content-scaling=fixed&starting-point-node-id=21%3A5) |
| Business problem, objectives, and scope | [BRD — PDF](1.%20Requirements/T%C3%A0i%20li%E1%BB%87u%20BRD.pdf) |
| Use cases and detailed requirements | [SRS — PDF](1.%20Requirements/T%C3%A0i%20li%E1%BB%87u%20SRS.pdf) |
| Process and system models | [Diagram images](2.%20Process%26Design/) |
| API and data design | [Technical specifications](3.%20Technical_Specification/) |

For a quick review, start with the presentation and prototype screens. PPTX and XLSX files may need to be downloaded. The exported screens are available if Figma cannot be opened.

## Business problem

The case study assumes a branch-based account-opening process involving manual data entry and repeated information checks. The proposed journey lets customers submit identity information remotely, review extracted information, and receive feedback during onboarding.

Reducing branch visits, repeated data entry, and onboarding friction are design objectives; no production results have been measured.

## My role and deliverables

As the BA on this individual project, I translated the simulated business problem into the following artifacts:

| BA activity | Deliverable |
| --- | --- |
| Explore stakeholder needs through a simulated Q&A | [Q&A log](1.%20Requirements/Q%26A.xlsx) |
| Define business objectives and scope | [BRD](1.%20Requirements/T%C3%A0i%20li%E1%BB%87u%20BRD.pdf) |
| Specify use cases, rules, and system behavior | [SRS](1.%20Requirements/T%C3%A0i%20li%E1%BB%87u%20SRS.pdf) |
| Model processes and interactions | [BFD, BPMN, UML, and ERD](2.%20Process%26Design/) |
| Organize user activities and MVP scope | User Story Map in the [Draw.io source](2.%20Process%26Design/M%E1%BB%9F_TK_eKYC.drawio) |
| Describe integration and data requirements | [API and database specifications](3.%20Technical_Specification/) |
| Visualize the proposed experience | [Figma and screen gallery](4.%20Prototype/) |

## Target MVP

**Customer:** A new individual customer with a valid CCCD and no existing CIF. Opening additional accounts for existing customers is outside this MVP.

The main journey covers:

1. Verify the phone number using OTP.
2. Capture both sides of the CCCD and extract information using OCR.
3. Review extracted identity information.
4. Record a facial video for Face Matching and Liveness checks.
5. Provide optional referral information and complete the application details and consent.
6. Check for an existing customer and create the customer/account records when eligible.
7. Notify the customer through the app and SMS.
8. Set up eBanking credentials and a PIN, with confirmation of successful setup.

### Key scope decisions

- **OCR only:** The prototype uses photos of the CCCD; NFC chip reading is not included. OCR extracts information and does not by itself prove identity.
- **Failed verification:** Allow retries according to the specified rules; when online verification cannot be completed, stop the online flow and guide the customer to support or a branch. A manual-review queue is outside the target MVP.
- **Customer identifiers:** Local `MaKH` and Core Banking `MaCIF` are separate identifiers.
- **Account and eBanking:** An opened bank account and completed eBanking setup are separate outcomes.
- **PIN:** This project covers PIN setup during onboarding; transfer execution is outside scope.
- **Integrations:** Core Banking, eKYC, and SMS interactions are modeled in the documents. No live integration or backend implementation is included.

## Repository guide

| Folder | Contents |
| --- | --- |
| [1. Requirements](1.%20Requirements/) | BRD, SRS, simulated Q&A |
| [2. Process&Design](2.%20Process%26Design/) | Diagram images and editable Draw.io source |
| [3. Technical_Specification](3.%20Technical_Specification/) | API and database specifications |
| [4. Prototype](4.%20Prototype/) | Figma link and 17 exported screens |
| [5. Portfolio](5.%20Portfolio/) | Project presentation |

## Tools and skills demonstrated

**Tools:** Word, Excel, PowerPoint, Draw.io, Figma; SQL Server data modeling in the database specification.

**BA skills:** Simulated requirements elicitation, scope definition, business rules, use-case specification, BPMN/UML modeling, user story mapping, UI prototyping, API requirements, and data modeling.

## Current document status

This repository contains the analysis and design deliverables of an individual BA training project. Prototype screens illustrate the customer journey; detailed business rules and validation requirements are documented in the BRD and SRS. No live banking integration or production deployment is included.
