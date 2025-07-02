# Data Integrity Violations & Findings – Prioritized

## Top 5 Findings (Highest Priority)

### 1. Missing Investor First and Last Names
- **84.16% missing** (~3,874 records).
- **Impact**: Blocks identity resolution, KYC compliance, schema design usefulness, and future integrations relying on names.
- **Source**: findings_first_pass_analysis.pdf, findings_data_consolidation_01.pdf

---

### 2. Transactions Referencing Non-Existent Funds
- **2,424 transactions** reference funds not present in managed funds data.
- **Impact**: Referential integrity failures may block migration or create invalid financial reporting.
- **Source**: findings_first_pass_analysis.pdf, findings_data_consolidation_01.pdf

---

### 3. Missing Fund for Account Association
- **98.04% missing Fund for Account** (~5.6 million records).
- **Impact**: Severe schema gaps; indicates systemic data quality issues or misunderstood join logic.
- **Source**: findings_first_pass_analysis.pdf, findings_data_consolidation_01.pdf

---

### 4. Duplicate Investor IDs
- **13 duplicate Investor IDs**.
- **Impact**: Violates primary key uniqueness, blocking clean migration to consolidated schema.
- **Source**: findings_first_pass_analysis.pdf, findings_data_consolidation_01.pdf

---

### 5. Accounts with Invalid Investor IDs
- **6,529 accounts** have invalid investor IDs.
- **Impact**: Breaks referential integrity; indicates orphaned or stale account records requiring urgent resolution.
- **Source**: findings_data_consolidation_01.pdf

---

## Remaining Findings (Important but Lower Immediate Priority)

### 6. Negative Fund Currency Amounts
- **~3.2 million negative amounts** across Unrealized Gain, Other Expense, Tax Prep Fee, etc.
- **Impact**: May reflect correct reversals or mis-posted data; requires business rule clarification.
- **Source**: findings_first_pass_analysis.pdf, findings_data_consolidation_01.pdf

---

### 7. Funds with Date Inconsistencies
- **10 funds** with inconsistent or illogical dates.
- **Impact**: Compromises reporting and financial analysis timelines.
- **Source**: findings_data_consolidation_01.pdf

---

### 8. Negative Debit and Credit Rows
- **55 negative debit rows**, **14 negative credit rows**.
- **Impact**: Potential data entry errors or anomalies requiring clarification.
- **Source**: findings_data_consolidation_01.pdf

---

### 9. Zero Debit and Credit Rows
- **204,695 zero debit rows**, **184,863 zero credit rows**.
- **Impact**: May indicate placeholder or incomplete transaction entries.
- **Source**: findings_data_consolidation_01.pdf

---

### 10. Missing Investor for Account
- **2.07% missing investor associations** (~135 records).
- **Impact**: Potential orphaned accounts impacting relational integrity.
- **Source**: findings_data_consolidation_01.pdf

---

### 11. Fully Duplicated Rows
- **738,321 fully duplicated rows** in fundopsdf out of ~5.7 million records.
- **Impact**: Data redundancy, bloated storage, risk of double-counting in analysis.
- **Source**: findings_data_consolidation_01.pdf

---

### 12. Unintended Data Leakage into Unnamed Columns
- **4 non-null entries** in placeholder Unnamed columns.
- **Impact**: Indicates data leakage or schema extraction issues requiring cleanup.
- **Source**: findings_data_consolidation_01.pdf

---

## Summary

Top 5 are critical blockers for schema consolidation, migration integrity, and operational readiness.

Remaining findings should be queued for remediation sequencing post-critical resolution or in parallel streams if resourcing allows.