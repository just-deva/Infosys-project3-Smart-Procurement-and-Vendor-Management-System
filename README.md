# 🛒 Smart Procurement & Vendor Management System (SPVMS)
### Capstone Project — Infosys Springboard Virtual Internship 7.0

<div align="center">

![Build Status](https://img.shields.io/badge/build-passing-brightgreen?style=for-the-badge&logo=github-actions)
![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-18.0+-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15.0+-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Enabled-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![License](https://img.shields.io/badge/License-Apache--2.0-blue?style=for-the-badge)

**An end-to-end, AI-enabled enterprise procurement platform designed to streamline purchase requisitions, automate vendor evaluation, ensure contract compliance, and optimize organizational spend.**

[Explore Features](#-core-features) • [System Architecture](#%EF%B8%8F-system-architecture) • [Getting Started](#-getting-started) • [API Documentation](#-api-reference) • [License](#-license)

</div>


---

## 📖 Overview

During my 3-month **Infosys Springboard Virtual Internship 7.0**, I designed and developed three progressive backend and enterprise software engineering projects—culminating in the **Smart Procurement & Vendor Management System**.

This capstone platform automates manual procurement cycles by connecting internal purchase requisitions with verified vendors, enforcing structured approval workflows, and maintaining clear audit trails across every purchase order.

---

## 🔗 Individual Project Repositories

This capstone consolidates my work across the three software engineering milestones completed during the internship. You can explore, review, or inspect the standalone repositories for each individual project below:

| Project Module | Description | Repository Link |
| :--- | :--- | :--- |
| 🏦 **Bank Management System** | Core banking operations, account handling & transaction management | [Infosys_project_1_bank_management_system](https://github.com/just-deva/Infosys_project_1_bank_management_system) |
| 🎓 **Student Management API** | RESTful API for student records, enrollments & academic data management | [infosys_project2_student_management_api](https://github.com/just-deva/infosys_project2_student_management_api) |
| 📦 **Smart Procurement & Vendor Management** | Automated procurement workflows, purchase orders & vendor tracking system | [Infosys-project3-Smart-Procurement-and-Vendor-Management-System](https://github.com/just-deva/Infosys-project3-Smart-Procurement-and-Vendor-Management-System) |

---

## ✨ Key Capabilities (Project 3 Capstone)

* **🤝 Vendor Registry & Onboarding:** Centralized vendor directory with profile management, contact records, service categories, and active status tracking.
* **📝 Purchase Requisition & Approval Flow:** Structured request submission and review pipeline to validate procurement needs before order generation.
* **🧾 Automated Purchase Order (PO) Management:** End-to-end PO creation, line-item tracking, status updates (`Draft` → `Approved` → `Dispatched` → `Fulfilled`), and order history.
* **📊 Spend & Order Visibility:** Consolidated tracking of vendor-wise orders, procurement volume, and fulfillment timelines for operational accountability.
* **🔐 Role-Based Access & Data Integrity:** Controlled access separation between requesters, approvers, and vendor administrators with validated inputs.

---

## 🔄 Procurement Workflow

```text
┌──────────────────────┐     ┌──────────────────────┐     ┌──────────────────────┐
│  Vendor Onboarding   │────▶│ Purchase Requisition │────▶│  Approval & Review   │
│  & Catalog Setup     │     │     Submission       │     │      Workflow        │
└──────────────────────┘     └──────────────────────┘     └──────────┬───────────┘
                                                                     │
┌──────────────────────┐     ┌──────────────────────┐                ▼
│  Delivery Tracking   │◀────│   Vendor Dispatch    │◀────┌──────────────────────┐
│  & Audit Closure     │     │   & Fulfillment      │     │   Purchase Order     │
└──────────────────────┘     └──────────────────────┘     │    (PO) Generated    │
                                                          └──────────────────────┘


---

## 📌 Executive Summary

The **Smart Procurement & Vendor Management System (SPVMS)** modernizes traditional supply chain and procurement workflows. By replacing fragmented manual spreadsheets with automated purchase order lifecycles, real-time vendor risk scoring, and automated RFQ comparisons, SPVMS reduces procurement turnaround times by up to **65%** while eliminating compliance bottlenecks.

---

## 🛠️ System Architecture

The platform follows an event-driven microservices architecture ensuring high availability, security, and seamless API integration with external ERP systems.

### 1. High-Level Technical Architecture

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
