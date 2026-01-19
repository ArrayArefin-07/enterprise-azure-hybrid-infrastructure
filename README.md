# 🏛️ Project : Enterprise Hybrid Cloud Asset Pipeline
## Secure Infrastructure Integration: Vercel PaaS + Microsoft Azure IaaS

This project demonstrates a production-grade **Hybrid Cloud Architecture** implemented for the **AI Job-Assistant Pro**. By decoupling the frontend application from mission-critical system documentation, the architecture ensures high scalability, optimized performance, and enterprise-level security.

---

### 🚀 Architecture Overview
The system follows a "Compute-at-Edge, Store-at-Cloud" strategy:
- **Frontend (Vercel):** Globally distributed UI layer for sub-100ms latency.
- **Security Layer (Azure):** Private object storage with time-bound access control.
- **Automation (n8n):** Backend logic for AI processing and delivery.

![Vercel Frontend Hero](./screenshots/vercel-frontend-hero.png)
*Figure 1: Live Frontend Application Interface hosted on Vercel.*

![Hybrid Flow Diagram](./screenshots/hybrid-flow-diagram.png)
*Figure 2: Cross-cloud data flow and security architecture.*

---

### 🛠️ Technical Implementation (Azure Operations)

#### 1. Secure Asset Management
System documentations are isolated in a private Azure Blob Storage container (`project-assets-private`). Access is strictly denied to anonymous users, fulfilling enterprise data privacy standards.

![Azure Portal Assets](./screenshots/azure-portal-assets.png)
*Figure 3: Isolated storage container in Microsoft Azure.*

#### 2. Zero-Trust Access with SAS
Instead of public links, I implemented **Shared Access Signatures (SAS)**. This provides:
- **Time-Bound Access:** Links automatically expire after a set duration.
- **Protocol Enforcement:** Restricted to HTTPS-only transit.
- **Granular Permissions:** Read-only access to prevent data tampering.

![Azure SAS Settings](./screenshots/azure-sas-settings.png)
*Figure 4: Configuration of time-bound security tokens.*

#### 3. Frontend Integration
The Vercel-hosted frontend dynamically requests these signed assets. A dedicated security section in the footer allows authorized users to view the technical specifications.

![Footer Security Link](./screenshots/footer-security-link.png)
*Figure 5: Secure gateway link integrated into the UI footer.*

---

### 🔗 Live Artifacts
- **Live Application:** [https://ai-job-assistant-seven.vercel.app/](https://ai-job-assistant-seven.vercel.app/)
- **Secure System Documentation (Azure-Protected):** [Access via SAS Link](https://mobashervault17099.blob.core.windows.net/project-assets-private/system-documentation.pdf?sp=r&st=2026-01-19T18:16:03Z&se=2026-02-05T17:59:03Z&spr=https&sv=2024-11-04&sr=b&sig=bXO41kBYj1A%2BSvHytySpBRgok%2Bpdu1y8%2B5XCpGprEtI%3D)

---

### 🛡️ Verified Output
When the SAS link is accessed, the browser securely fetches the document directly from Azure's backbone network, bypassing public web vulnerabilities.

![Secure PDF View](./screenshots/secure-pdf-view.png)
*Figure 6: Successfully rendered system documentation via encrypted SAS tunnel.*

---
**Engineered by Mobasher Arefin**
*Focused on Microsoft Azure Infrastructure & Hybrid Cloud Operations.*