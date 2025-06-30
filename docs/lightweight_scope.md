# POC: Lightweight Focused Scope

## Objective
Deliver a **two-week Proof of Concept (POC)** demonstrating ingestion, validation, reconciliation, and correction of private credit data files with minimal tool ramp-up risk.

---

## Outline: Lightweight Focused Scope

### 1. Scope Focus
- ✅ **Select a single file type** for the POC (e.g. Investor Subscriptions).
- ✅ **Target 2-3 known data issues** for correction workflows, such as:
  - Missing Fund Codes.
  - Invalid date formats.
  - Calculation errors (e.g. missing total amounts).

---

### 2. Approach Simplification
- Replace heavy pipeline tools with **simple Python scripts + notebooks**.
- Ingest sample files locally or via direct upload, deferring Azure Data Factory setup.
- Use **pandas for transformation and validation logic**.
- Prepare outputs in a format resembling eFront import templates.

---

### 3. Demo Deliverables
- Working scripts demonstrating:
  - File ingestion.
  - Schema mapping.
  - Validation rule checks.
  - Automated corrections for known issues.
- A **summary CLI report or Streamlit dashboard** showing:
  - Total records processed.
  - Issues detected and auto-corrected.
  - Remaining unresolved issues.
- An **architecture diagram** outlining how these steps would scale using Azure tools.

---

## Proposed Azure Architecture

### ⚡ POC Implementation (Local / Lightweight)
