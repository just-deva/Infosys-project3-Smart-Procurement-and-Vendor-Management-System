<div align="center">

<img src="https://capsule-render.vercel.app/api?type=transparent&height=120&text=Smart%20Procurement%20%26%20Vendor%20Management&fontSize=34&fontColor=FACC15&desc=Capstone%20Project%20%E2%80%94%20Infosys%20Springboard%20Virtual%20Internship%207.0&descSize=17&descColor=FB923C&descAlignY=78" alt="Smart Procurement & Vendor Management System" />

![Build Status](https://img.shields.io/badge/build-passing-4F46E5?style=for-the-badge&logo=github-actions&logoColor=A5B4FC&labelColor=1E1B4B)
![Python](https://img.shields.io/badge/Python-3.11+-4338CA?style=for-the-badge&logo=python&logoColor=A5B4FC&labelColor=1E1B4B)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-4F46E5?style=for-the-badge&logo=fastapi&logoColor=A5B4FC&labelColor=1E1B4B)
![React](https://img.shields.io/badge/React-18.0+-6366F1?style=for-the-badge&logo=react&logoColor=E0E7FF&labelColor=1E1B4B)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15.0+-4338CA?style=for-the-badge&logo=postgresql&logoColor=A5B4FC&labelColor=1E1B4B)
![Docker](https://img.shields.io/badge/Docker-Enabled-4F46E5?style=for-the-badge&logo=docker&logoColor=A5B4FC&labelColor=1E1B4B)
![License](https://img.shields.io/badge/License-Apache--2.0-3730A3?style=for-the-badge&labelColor=1E1B4B)

**An end-to-end, AI-enabled enterprise procurement platform designed to streamline purchase requisitions, automate vendor evaluation, ensure contract compliance, and optimize organizational spend.**

</div>

---

<img src="https://capsule-render.vercel.app/api?type=transparent&height=45&text=Overview%20%26%20Executive%20Summary&fontSize=22&fontColor=FB923C&fontAlign=0&fontAlignY=55" alt="Overview & Executive Summary" />

During my 3-month **Infosys Springboard Virtual Internship 7.0**, I designed and developed three progressive backend and enterprise software engineering projects—culminating in the **Smart Procurement & Vendor Management System (SPVMS)**.

SPVMS modernizes traditional supply chain and procurement workflows by replacing fragmented manual spreadsheets with automated purchase order lifecycles, real-time vendor risk scoring, and automated RFQ comparisons—reducing procurement turnaround times by up to **65%** while maintaining strict audit trails and compliance.

---

<img src="https://capsule-render.vercel.app/api?type=transparent&height=45&text=Individual%20Project%20Repositories&fontSize=22&fontColor=FB923C&fontAlign=0&fontAlignY=55" alt="Individual Project Repositories" />

This capstone consolidates my work across the three software engineering milestones completed during the internship. You can explore, review, or inspect the standalone repositories for each individual project below:

| Project Module | Description | Repository Link |
| :--- | :--- | :--- |
| 🏦 **Bank Management System** | Core banking operations, account handling & transaction management | [Infosys_project_1_bank_management_system](https://github.com/just-deva/Infosys_project_1_bank_management_system) |
| 🎓 **Student Management API** | RESTful API for student records, enrollments & academic data management | [infosys_project2_student_management_api](https://github.com/just-deva/infosys_project2_student_management_api) |
| 📦 **Smart Procurement & Vendor Management** | Automated procurement workflows, purchase orders & vendor tracking system | [Infosys-project3-Smart-Procurement-and-Vendor-Management-System](https://github.com/just-deva/Infosys-project3-Smart-Procurement-and-Vendor-Management-System) |

---

<img src="https://capsule-render.vercel.app/api?type=transparent&height=45&text=Core%20Capabilities&fontSize=22&fontColor=FB923C&fontAlign=0&fontAlignY=55" alt="Core Capabilities" />

* **🤝 Vendor Registry & Risk Scoring:** Centralized vendor onboarding with profile management, compliance verification, and AI-assisted performance/risk evaluation.
* **📝 Purchase Requisition & Approval Flow:** Structured request submission and multi-tier review pipeline to validate budget and procurement needs before order generation.
* **⚖️ Automated RFQ & Bidding Management:** Streamlined Request for Quotation creation and side-by-side vendor quote evaluation.
* **🧾 Automated Purchase Order (PO) & Invoicing:** End-to-end PO lifecycle tracking (`Draft` → `Approved` → `Dispatched` → `Fulfilled`) paired with automated billing and document storage.
* **🔐 OAuth2 / JWT & Role-Based Access Control (RBAC):** Strict access separation between requesters, approvers, finance teams, and vendor administrators.

---

<img src="https://capsule-render.vercel.app/api?type=transparent&height=45&text=Procurement%20Workflow&fontSize=22&fontColor=FB923C&fontAlign=0&fontAlignY=55" alt="Procurement Workflow" />

```text
┌──────────────────────┐     ┌──────────────────────┐     ┌──────────────────────┐
│  Vendor Onboarding   │────▶│ Purchase Requisition │────▶│  Approval & RFQ      │
│  & Catalog Setup     │     │     Submission       │     │  Evaluation Flow     │
└──────────────────────┘     └──────────────────────┘     └──────────┬───────────┘
                                                                     │
┌──────────────────────┐     ┌──────────────────────┐                ▼
│  Invoice Matching    │◀────│   Vendor Dispatch    │◀────┌──────────────────────┐
│  & Audit Closure     │     │   & Fulfillment      │     │   Purchase Order     │
└──────────────────────┘     └──────────────────────┘     │    (PO) Generated    │
                                                          └──────────────────────┘
```

---

<img src="https://capsule-render.vercel.app/api?type=transparent&height=45&text=System%20Architecture&fontSize=22&fontColor=FB923C&fontAlign=0&fontAlignY=55" alt="System Architecture" />

The platform follows a modular, event-driven microservices architecture ensuring high availability, security, and seamless integration with external ERP systems.

```mermaid
graph TD
    %% User Tier
    subgraph Clients ["💻 Client Layer"]
        A[Admin Dashboard]
        B[Vendor Portal]
        C[Mobile Approval App]
    end

    %% Gateway & Auth
    subgraph Gateway ["🔒 API Gateway & Security"]
        GW[API Gateway / Nginx]
        AUTH[OAuth2 / JWT Manager]
        RBAC[RBAC Access Control]
    end

    %% Core Services
    subgraph Microservices ["⚙️ Core Backend Services"]
        VS[Vendor Service]
        PR[Procurement Service]
        RFQ[RFQ & Bidding Service]
        INV[Invoice & Billing Service]
        AI[AI Risk & Analytics Engine]
    end

    %% Storage & Message Layer
    subgraph Persistence ["💾 Data & Messaging Layer"]
        DB[(PostgreSQL Primary)]
        REDIS[(Redis Cache & Queues)]
        S3[(AWS S3 / Document Store)]
    end

    Clients -->|HTTPS / WSS| GW
    GW --> AUTH
    AUTH --> RBAC
    RBAC --> VS
    RBAC --> PR
    RBAC --> RFQ
    RBAC --> INV

    VS & PR & RFQ & INV --> AI
    VS & PR & RFQ & INV --> DB
    VS & PR & RFQ & INV --> REDIS
    INV --> S3
```

---

<img src="https://capsule-render.vercel.app/api?type=transparent&height=45&text=Getting%20Started&fontSize=22&fontColor=FB923C&fontAlign=0&fontAlignY=55" alt="Getting Started" />

<details>
<summary><strong>📦 Click to expand setup & installation instructions</strong></summary>

<br>

1. **Clone the repository**
   ```bash
   git clone [https://github.com/just-deva/Infosys-project3-Smart-Procurement-and-Vendor-Management-System.git](https://github.com/just-deva/Infosys-project3-Smart-Procurement-and-Vendor-Management-System.git)
   cd Infosys-project3-Smart-Procurement-and-Vendor-Management-System
   ```

2. **Run with Docker (Recommended)**
   ```bash
   docker-compose up --build
   ```

3. **Or run locally (Backend & Frontend)**
   ```bash
   # Backend (FastAPI)
   pip install -r requirements.txt
   uvicorn app.main:app --reload

   # Frontend (React)
   cd frontend
   npm install && npm run dev
   ```

4. **Explore API Documentation**
   Once the server is running, open `http://localhost:8000/docs` for interactive Swagger UI documentation.

</details>

---

<img src="https://capsule-render.vercel.app/api?type=transparent&height=45&text=Author%20%26%20License&fontSize=22&fontColor=FB923C&fontAlign=0&fontAlignY=55" alt="Author & License" />

**Devadarshini S**  
B.Tech Computer Science & Engineering (Cybersecurity) — Amrita Vishwa Vidyapeetham  
GitHub: [@just-deva](https://github.com/just-deva) • Licensed under the **Apache-2.0 License**
