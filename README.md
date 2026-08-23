# Supplier Evidence Access Authorization Renewal Platform
## The Problem
Evidence access authorizations are not permanent. Without a formal renewal process, teams cannot establish that continued access still has a defined purpose, received an independent assessment, was approved by authority, and was understood by the recipient.
## The Solution
This service governs authorization renewal from request through verification. The owner requests a scoped renewal, the reviewer assesses continued need, an authority approves, the recipient acknowledges, and the reviewer verifies the resulting control record.
## Live Demo and Tech Stack
Run `http://localhost:60000/health`. The stack uses Node.js 22, Express 5, atomic JSON persistence, Vitest, and GitHub Actions. The service binds to `0.0.0.0` for LAN operation.
## Local Setup and Run Instructions
```bash
npm install
npm test
env -u PORT node server.mjs
```
## System Documentation
### System Architecture Diagram
```mermaid
flowchart LR
  Owner-->API[Express API]
  Reviewer-->API
  Authority-->API
  Recipient-->API
  API-->Domain[Renewal service]-->Store[Atomic JSON]
```
### Entity Relationship Diagram
```mermaid
erDiagram
  AUTHORIZATION_RENEWAL ||--o{ RENEWAL_EVENT : records
```
### Data Flow Diagram
```mermaid
flowchart TD
  Request-->Assess-->Approve-->Acknowledge-->Verify
```
### Use Case Diagram
```mermaid
flowchart LR
  Owner-->Request[Request renewal]
  Reviewer-->Assess[Assess scope]
  Authority-->Approve[Approve renewal]
  Recipient-->Acknowledge[Acknowledge terms]
  Reviewer-->Verify[Verify renewal]
```
### Sequence Diagram
```mermaid
sequenceDiagram
  participant O as Owner
  participant A as API
  participant S as Renewal service
  O->>A: Request renewal
  A->>S: Validate scoped request
  S-->>A: Renewal request audit event
```
## Owner

Created and maintained by Kholipha Ahmmad Al-Amin.

Software Engineer and AI Specialist

Founder and CEO of EquiSaaS BD

Principal Consultant at AR IT Consultancy

Full Stack Developer and SaaS Product Builder

### Official links

Portfolio: https://kholipha-ahmmad-al-amin.equisaas-bd.com/

GitHub: https://github.com/kholipha-ahmmad-al-amin

LinkedIn: https://www.linkedin.com/in/kholipha-ahmmad-al-amin

X: https://x.com/al_amin5519

Facebook: https://www.facebook.com/kholipha.ahmmad.al.amin

Instagram: https://www.instagram.com/kholipha.ahmmad.al.amin

## Ownership

This project was created and is maintained by Kholipha Ahmmad Al-Amin.

