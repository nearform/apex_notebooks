# Data Validation Findings – First Pass Review

## Top 5 Items of Concern

### 1. High Missing Investor First/Last Name Data
- **Finding:** 84.16% of investor records missing first and last names.
- **Concern:** Impacts identity resolution, KYC compliance, schema usefulness, and future integrations relying on names.

### 2. Transactions Referencing Funds Not in Managed Funds Data
- **Finding:** 2,424 transactions reference non-existent funds.
- **Concern:** Referential integrity failure may block migration or create invalid financial reporting.

### 3. Massive Missing Fund for Account in fund_ops_df
- **Finding:** 98.04% of rows missing Fund for Account association (~5.6 million records).
- **Concern:** Indicates either systemic data quality issues or a misunderstood join logic.

### 4. High Volume of Negative Fund Currency Amounts in fund_ops_df
- **Finding:** ~3.2 million negative amounts across Unrealized Gain, Other Expense, Tax Prep Fee.
- **Concern:** May reflect correct accounting entries or mis-posted data; needs clarification for transformation rules.

### 5. Duplicate Investor IDs
- **Finding:** 13 duplicate Investor IDs.
- **Concern:** Violates primary key uniqueness, blocking clean migration to the consolidated schema.

---

## Insights

- Data completeness issues (e.g. missing names, missing fund associations) will directly affect reporting, operational integrations, and client-facing features.
- Referential integrity failures (transactions referencing missing funds) may indicate stale or unlinked master data.
- Negative values require business rule clarification – whether they represent reversals, accrual adjustments, or entry errors.
- Duplicate keys (Investor IDs) need root cause analysis to determine if caused by upstream system issues or data entry duplication.

---

## Draft Questions for Customer Clarification

1. **Investor Data Completeness**  
   Are first and last names mandatory fields in the source systems, or is legal name sufficient for identification and KYC purposes?

2. **Fund Associations in Transactions**  
   Why do 2,424 transactions reference funds not listed in the managed funds data? Is there an external or legacy fund master not included here?

3. **Fund for Account Missing in fund_ops_df**  
   Is the missing Fund for Account (98%) expected due to upstream system design, or are these incomplete records needing remediation?

4. **Negative Fund Currency Amounts**  
   Should negative amounts be treated as reversals, adjustments, or errors? Is there a consistent rule across Unrealized Gain, Other Expense, and Tax Prep Fee?

5. **Duplicate Investor IDs**  
   What is the process to resolve duplicate Investor IDs? Should these be merged, de-duplicated, or assigned new unique identifiers?

---