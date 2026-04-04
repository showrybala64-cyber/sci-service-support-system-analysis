# 🖥️ SCI Computer Service Support System (CSSS)

### *Enterprise operations running on pings and spreadsheets. This system changes that.*

> A full enterprise-level service operations system designed using structured **Systems Analysis & Design (SDLC)** methodology — unifying Service Requests, Technician Scheduling, Inventory Management, RMA Tracking, and Billing into a single, coherent architecture.

[![Methodology](https://img.shields.io/badge/Methodology-SDLC%20%7C%20Structured%20Analysis-blueviolet?style=for-the-badge)]()
[![Modeling](https://img.shields.io/badge/Modeling-DFD%20%7C%20ERD%20%7C%20Context%20Diagram-blue?style=for-the-badge)]()
[![Type](https://img.shields.io/badge/Type-Systems%20Design%20%7C%20Data%20Architecture-orange?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Design%20Complete-brightgreen?style=for-the-badge)]()

---

## 📌 The Business Problem

SCI Computer Services was operating at scale with **zero enterprise-grade tooling**. Their operations relied on:

| Pain Point | Impact |
|-----------|--------|
| 💬 Informal "ping"-based task tracking | Service requests missed or forgotten entirely |
| 📋 Manual FIFO inventory counting | Overstocking, stockouts, no real-time accuracy |
| 🧾 Disconnected RMA and billing workflows | Manual reconciliation between field work and accounting |
| 👁️ No technician workload visibility | Uneven assignment, burnout, no utilization metrics |
| ⏱️ No SLA monitoring | No accountability on response or resolution times |
| 📊 Minimal operational reporting | Management flying blind on capacity and performance |

**This system was designed to eliminate every one of those gaps.**

---

## 🏗️ System Architecture Overview

The system was fully logically modeled before implementation using structured analysis techniques — from context boundary through data flow decomposition to full relational data design.

---

### 📐 Context Diagram

Defines the system boundary and all external entities that interact with CSSS:

- 👤 **Customers** — submit service requests, receive invoices
- 🔧 **Technicians** — receive work orders, log time and parts
- 📦 **Vendors** — supply inventory, receive and process RMAs
- 💼 **Accounting** — receive invoice drafts, manage billing
- 📊 **Management** — consume operational dashboards and reports

---

### 🔄 Level-0 Data Flow Diagram (DFD)

Four core process bubbles decomposed from the context diagram:

```
1. Intake & Schedule Service Request   →  Customer intake → technician assignment → SLA clock starts
2. Perform Service                     →  Work order execution → time logging → parts consumption
3. Invoice & Notify                    →  Completed work → auto-drafted invoice → customer notification
4. Manage Inventory & RMAs             →  Stock tracking → FIFO costing → vendor RMA lifecycle
```

**Logical Data Stores modeled:**
- D1 — Service Requests
- D2 — Schedules & Time Entries
- D3 — Inventory
- D4 — Billing / Invoices
- D5 — RMA Records

---

### 🗄️ Entity Relationship Diagram (ERD)

**13 entities fully modeled** with cardinality, primary/foreign keys, and normalization:

| Entity | Role |
|--------|------|
| Customer | Source of all service demand |
| ServiceRequest | Core lifecycle record |
| WorkOrder | Execution unit tied to service requests |
| Technician | Resource assigned to work orders |
| TechAssignment | Junction table (many-to-many Technician ↔ WorkOrder) |
| TimeEntry | Granular labor tracking per technician per work order |
| InventoryItem | Parts tracked with FIFO costing |
| Vendor | Supplier linked to inventory and RMAs |
| RMA | Return lifecycle record linked to work orders and inventory |
| Invoice | Billing document auto-generated from completed work |
| InvoicePartLine | Itemized parts charges per invoice |
| InvoiceLaborLine | Itemized labor charges per invoice |
| PartUsage | Parts consumed per work order — bridges inventory and billing |

**Design highlights:**
- ✅ Full normalization through 3NF
- ✅ FIFO inventory costing structure
- ✅ RMA traceability linked to Work Orders and Inventory
- ✅ Separate labor and parts invoice line modeling
- ✅ Many-to-many Technician ↔ WorkOrder via TechAssignment
- ✅ Complete cardinality definitions across all relationships

---

## ✅ Functional Requirements Delivered

**34 structured functional requirements** covering the full system scope:

- 📋 Centralized Service Request lifecycle (open → assigned → in-progress → closed)
- 🔧 Technician assignment and work queue management
- ⏱️ SLA response time and completion time monitoring
- 📦 Perpetual inventory with FIFO costing logic
- 🔢 Lot and serial number traceability
- 🔄 RMA lifecycle management with full vendor linkage
- 🧾 Automated invoice draft generation from completed work orders
- 🔐 Role-based access control
- 📝 Audit logging for all system changes
- 📊 Operational dashboards for workload, SLA health, and inventory status

---

## 📁 Project Structure

```
sci-service-support-system-analysis/
│
├── docs/
│   ├── 01_Requirements_Definition.pdf
│   ├── 02_Context_Diagram.pdf
│   ├── 03_Level0_DFD.pdf
│   └── 04_ERD_Data_Model.pdf
│
├── diagrams/
│   ├── context_diagram.jpg
│   ├── level0_dfd.jpg
│   └── erd_data_model.jpg
│
└── README.md
```

---

## 📈 Business Impact (If Implemented)

| Outcome | Mechanism |
|---------|-----------|
| 🚫 Eliminated missed service requests | Structured intake and SLA monitoring |
| 📊 Real-time technician utilization | Work queue visibility and time entry logging |
| 📦 Accurate inventory at all times | Perpetual inventory with FIFO costing |
| 💰 Automated billing handoff | Invoice auto-draft from completed work orders |
| 📉 Reduced stockouts and overstock | Min/max thresholds with real-time tracking |
| 🔄 Full RMA recovery tracking | Vendor-linked RMA lifecycle with status monitoring |
| 📋 Measurable SLA performance | Response and resolution time KPIs |

---

## 🛠️ Skills Demonstrated

```
Systems Analysis & Design     →  Full SDLC methodology from problem definition to logical design
Business Process Modeling     →  Gane-Sarson DFD notation, context and Level-0 decomposition
Data Modeling                 →  ERD design, cardinality definition, full normalization (3NF)
Requirements Engineering      →  34 structured functional requirements with acceptance criteria
Inventory Systems Design      →  FIFO costing logic, lot/serial traceability, perpetual tracking
SLA & KPI Framework Design    →  Response time, resolution time, and utilization metrics
Enterprise Documentation      →  Production-grade system documentation standards
Workflow Architecture         →  End-to-end process decomposition across 4 core system domains
```

---

## 👤 About the Author

**Lourdu Bala Showry Kata**
M.S. Information Systems (Data Analytics) — Central Michigan University | GPA: 3.98
3+ years of data analytics experience at Amazon | OPT | Available Immediately

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/lourdu-bala-showry-k)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/showrybala64-cyber)

---

*This project demonstrates production-level systems thinking applied to service operations, inventory management, and financial integration workflows — the kind of structured analysis that separates data professionals who can build systems from those who only use them.*
