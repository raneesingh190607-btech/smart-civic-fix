# Technical Design Document: Smart CivicFix 🏛️

This document outlines the architectural framework, data pipeline, and system workflows for **Smart CivicFix**, a citizen-focused platform for reporting and tracking localized public issues.

---

## 🏗️ System Architecture Overview

Smart CivicFix uses a decoupled architecture designed for high availability, zero-maintenance scaling, and instant synchronization between citizens and administrative personnel.

```text
  [ Citizen Client ]       [ Admin Web Console ]
   (HTML5/CSS3/JS)           (HTML5/CSS3/JS)
          │                         │
          ▼                         ▼
  ┌──────────────────────────────────────────────┐
  │         Firebase Application Layer           │
  ├───────────────┬───────────────┬──────────────┤
  │  Firebase     │  Cloud        │  Cloud       │
  │  Auth         │  Firestore    │  Storage     │
  │ (User Login)  │ (JSON NoSQL)  │ (Images/JPG) │
  └───────────────┴───────────────┴──────────────┘
```

### 1. Presentation Layer (Frontend Client)
* **Citizen Portal (`index.html`):** Lightweight web application optimized for desktop and mobile viewports. Utilizes browser API modules for form handling and state mutations.
* **Admin Dashboard (`admin.html`):** Analytical dashboard providing layout tables, data filtration, and direct data-binding to backend state streams.

### 2. Service & Managed Infrastructure Layer (Backend)
* **Authentication:** Managed provider validating secure local storage sessions.
* **Database (Cloud Firestore):** A schemaless NoSQL document store delivering real-time reactive event listeners to connected web nodes.
* **Object Storage:** Unstructured media storage repository configured with access policies to protect uploaded images.

---

## 🔄 Core Workflows & Data Pipelines

### A. Issue Reporting Pipeline
1. **Input Capture:** User inputs complaint specifics (category, textual description) and appends a photo file attachment.
2. **Geographical Resolution:** Local coordinate metadata is bound alongside data payload properties.
3. **Payload Dispatch:** The client transforms data properties into a secure JSON-like object document, streaming it directly to the remote repository collection state.

### B. Administrative Resolution Loop
1. **Live Aggregation:** The administrative console reads incoming collection data blocks ordered sequentially by operational priority weightings.
2. **State Updates:** Staff interact with visual control triggers to switch issue tracking states (`Pending Review` ➡️ `In Progress` ➡️ `Resolved`).
3. **Reactive Re-indexing:** Mutation updates automatically write changes back down to active client interfaces instantly.
